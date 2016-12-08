RubyConfとRubyConf Taiwanに参加してきました

このブログは[NIJIBOX Advent Calendar 2016](http://qiita.com/advent-calendar/2016/nijibox)の8日目の投稿です。

![A sight at CVG](blogs/20161208-rubyconf-recommended-talks/airport.jpg)

開発室室長の@remoreです。11月10日〜12日の3日間でオハイオ州シンシナティで開催されていたRubyConf 2016と、12月2日〜3日の2日間で台湾で開催されたRubyConf Taiwan 2016に、主にSpeakerとして参加してきました。どちらのカンファレンスも会社の業務として出張で行ってきたものです。このブログでは2つのカンファレンスの中で最も興味を引いたTalkをいくつか紹介したいと思います。

なお、生活の記録的な内容は個人のブログの方で紹介していますので、興味のある方がいればこちらもどうぞ。

- [RubyConf 2016に参加しています | 48JIGEN *Reloaded](http://rimuru.lunanet.gr.jp/notes/post/rubyconf-2016-day-0/)
- [RubyConf 2016に参加しました | 48JIGEN *Reloaded](http://rimuru.lunanet.gr.jp/notes/post/attended-rubyconf-2016/)
- [RubyConf Taiwanが良い感じだった | 48JIGEN *Reloaded](http://rimuru.lunanet.gr.jp/notes/post/rubyconf-taiwan-2016/)

## Methods of Memory Management in MRI

<iframe width="560" height="315" src="https://www.youtube.com/embed/r0UjXixkBV8?list=PLE7tQUdRKcyaMUYwB6tTX5p2Z6fOCdGRE" frameborder="0" allowfullscreen></iframe>

日本のKaigiでもおなじみのAaron Patterson(@tendorlove)のTalk。CRubyでのメモリ確保やGCの動作について初心者にも分かりやすく、面白く深く紹介してくれます。内容も当然オススメですが、動画序盤10分くらいで展開されるIcebreakingでの@tenderlove節が最高過ぎて至福でした。内容も解説が丁寧で勉強になるのですが、個人的には特にTagged Pointerの考え方が勉強になりました。[Fixnumのobject_idが常に奇数であり演算可能ですぐにそれと分かる](http://www.sarahmei.com/blog/2009/04/21/object-ids-and-fixnums/)などは聞いたことがあったのですが、RVALUEが40bytesであることの意味についても知りHeap領域への理解が少し深まりました。

Speaker Deckでの資料は[こちら](https://speakerdeck.com/tenderlove/methods-of-memory-management-in-mri)

## From no OSS experience to the core team in 15 minutes a day

<iframe width="560" height="315" src="https://www.youtube.com/embed/6jUe-9Y__KM?list=PLE7tQUdRKcyaMUYwB6tTX5p2Z6fOCdGRE" frameborder="0" allowfullscreen></iframe>

BundlerのリードデベロッパーのAndré Arko(@indirect)のTalk。OSS関係の活動を始めるにあたって、その前に整理しておいた方が良いゴール設定についての考え方から、実際にプロジェクトに参加してまずやるべきことや続けるべきこと、参加度を深めて効果的に貢献していくために気をつけるべきポイントなどについて、初心者がよく陥りがちなケースにも触れながら紹介していました。Talkの中で@indirect自身が強調していたのが（大事なことなので2回言うって言ってた）、"Only work for free if you can and if you want to"という部分で、この言葉が最も印象に残っています。GitHubはレジュメではないとか、OSSやる以外にも時間の使い方を考えた方がよいことだってあるとか、OSSの活動と人生における時間の使い方についても具体的かつ平易にアドバイスがあるなど、参考になるポイントが多いTalkでしたので、ぜひこれも紹介しておきたいと思います。

ちなみに、オススメされていたOSS活動への参加の仕方をかいつまむと、以下のような流れで参加していくとよいとのことでした。これらのような内容が気になる人にはTalkの視聴をオススメします。

- 1日15分と決めて活動する
- 時間の枠内で、プロジェクトの全部のドキュメンテーションを読む
- 読み終わったら、Issueとかで上がってる質問のうち答えられる部分について答えていく
- そうしてるうちにドキュメンテーションを改良したら良いとことかエラーメッセージを改良したら良いところが見つかっていくので、それらを提案していく
- そのうちバグの再現もできるようになってくるので、再現してあげて再現手段を明確にしてあげたり、結果が違わないことを確認していくと、テストコードの改良にも寄与していくことになる
- このあたりでpatchを書けるようになっているはず

本Talkに関する本人のBlog記事は[こちら](http://andre.arko.net/2016/11/12/how-to-contribute-to-open-source/)

## Am I Senior Yet

<iframe width="560" height="315" src="https://www.youtube.com/embed/jcTmoOHhG9A?list=PLE7tQUdRKcyaMUYwB6tTX5p2Z6fOCdGRE" frameborder="0" allowfullscreen></iframe>

その他にも良かったTalkがたくさんあったのですが、最後にシニアエンジニアになるとはどういうことかについて語っている"Am I Senior Yet"というTalkを紹介して本稿を終えたいと思います。内容としては、シニアエンジニアになるといった場合に技術的に優れたエンジニアになるという側面はよく紹介されるが、それはシニアエンジニアに求められることの一つの側面でしかなく、他の部分 - チームをリードする場合に必要となる、チームのパフォーマンスを最大化するためのTeachingという側面についても取り上げたいといった内容です。

内容としては、SpeakerであるKatlynがこの5年間の業務経験を通して学んだ、シニアエンジニアとして振る舞う際に気をつけるべき8つのlessonsについて紹介しています。目次と意訳を下記に記載します。特に"2. Learn to tailor your reponse to your audience"で紹介されていた[この図](https://speakerdeck.com/katlyn333/am-i-senior-yet-grow-your-career-by-teaching-your-peers?slide=26)の整理が自分の経験的にも腹落ちしましたし、良い整理がされていると感じました。

1. A question is an opportunity for growth(メンバーから質問が来た時に何を答えるべきか)
2. Learn to tailor your reponse to your audience(相手を意識した応答のコツ)
3. Resist the urge to teach by doing(背中を見せるスタイルだけだと伝わらないことがある)
4. Keep an eye out for mimicry(コピペコード(偶発的プログラミング)の発生に目を光らせる)
5. Teaching is about communicating effectively(コミュニケーションスキルを常に磨き続ける)
6. Have realistic expectations(Teachingは時間のかかる作業であり、現実主義で考える)
7. Teaching also benefits the teacher(教えることは学ぶこと)
8. Talk to your manager about how you can learn more effectively(自分がより学び成長するためにできることを上司と話す)

Speaker Deckでの資料は[こちら](https://speakerdeck.com/katlyn333/am-i-senior-yet-grow-your-career-by-teaching-your-peers)

## まとめ

RubyConfは日本のKaigiとは違い、技術的なTalk以外にもバリエーションに富んだTalkが聞けるConferenceで、このようにキャリア開発に関するTalkも聞けたのは面白かったです。実際に現場で開発業務を担当した場合に取り組むべき課題が技術的な問題だけではないことも多々あるかと思うので、こういったTalkも聞けるというのはRubyConfに行ってみてわかった海外のConferenceならではの良さだなと感じました。

NIJIBOXでは今年4月以降PHP Conference関西やRubyConf, RubyConf Taiwanなど、Speakerとして登壇する場合に業務（出張）扱いで行くことを推進・推奨しています。来年も様々なConferenceでの報告が本ブログに投稿されることだろうと思いますので、私も一読者として配信を楽しみにしています。

