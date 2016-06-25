require 'json'
require 'date'

desc 'compile blog files into json data and craete index.html from index.tmpl'
task :compile do
  result = []
  Dir.glob('./blogs/*.md').each do|f|
    result << {
      key:result.size+1,
      date:Date.parse(File.basename(f)[0..7]).strftime("%Y.%m.%d"),
      slug:File.basename(f)[9..-4],
      title:File.open(f).to_a[0].chomp,
      text:File.open(f).to_a[1..-1].join
    }
    File.symlink "index.html", result.last[:slug] if !File.exists?(result.last[:slug])
  end 
  File.write("index.html", File.open("index.tmpl").read.gsub(/###___REPLACE_HERE___/, result.reverse.map{|a| a.to_json}.join(",")))
end

