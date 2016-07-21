require 'json'
require 'date'
require 'uglifier'
require 'sitemap_generator'
require 'byebug'

Encoding.default_external = "utf-8"

desc 'compile blog files into json data and craete *.html from index.tmpl'
task :compile do
  js = ["jquery.min", "jquery.easing.1.3.min", "skel.min", "util", "marked.min", "react.min", "react-dom.min", "main"]
  File.write("./assets/js/uglified.js", Uglifier.new.compile(js.map{|e| File.read("./assets/js/#{e}.js")}.join))
  result = []
  Dir.glob('./blogs/*.md').each do |f|
    result << {
      key:result.size+1,
      date:Date.parse(File.basename(f)[0..7]).strftime("%Y.%m.%d"),
      slug:File.basename(f)[9..-4],
      title:File.open(f).to_a[0].chomp,
      text:File.open(f).to_a[1..-1].join
    }
    File.write("#{result.last[:slug]}.html", {
      :title => result.last[:title] + " | NIJIBOX ENGINEER BLOG",
      :url => "http://tech.nijibox.jp/#{result.last[:slug]}",
      :image => "http://tech.nijibox.jp/" + (Dir.glob("blogs/#{File.basename(f)[0..-4]}/*.jpg").first || ""),
      :version => Time.now.to_i.to_s
    }.inject(File.open("index.tmpl").read){ |html, replacement| html.gsub!(/\{###___#{replacement[0].to_s.upcase}___###\}/, replacement[1])})
  end 
  File.write("./assets/js/blog.js", File.open("./assets/js/blog.js.tmpl").read.gsub(/\{###___BLOG_ENTRIES___###\}/, result.reverse.map{|a| a.to_json}.join(",")))
  SitemapGenerator::Sitemap.default_host = 'http://tech.nijibox.jp'
  SitemapGenerator::Sitemap.create do
    add "/", :changefreq => 'always'
    result.each do |page|
      add "/#{page[:slug]}", :changefreq => 'daily'
    end
  end
end

