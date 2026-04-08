当前目录是包含众多唱片的目录，每个唱片目录有跟该唱片相关的图片或音频等所有文件，需要你手动（不要写自动化脚本！）按照字母顺序依次进入每个唱片目录，在每个目录下用subagent生成该唱片信息的以下几个文档（即使某个目录以及有以下文档，也必须重复以下步骤进行更新，不能跳过）：
1. "专辑基本信息.md"。至少包含以下信息，如果有遗漏需要补齐（可以通过读取专辑封底或内页的图片识别文字）：
  * （1）专辑名称
  * （2）艺术家/演奏家
  * （3）厂牌
  * （4）发行时间/出版时间(release date)
  * （5）曲目
  * （6）专辑网页（用于证实专辑存在的真实性），来自MusicBrainz、Presto Music、Discogs、Last.fm、iTunes、Deezer、Spotify、AllMusic、Amazon、Ebay等网站上该专辑的页面。）例如你使用了 Fetch(url:
"https://www.amazon.com/Portrait-2-GIACOMO-LAURI-VOLPI/dp/B001QMHOCS") 就可以把这个url记录下来。
2. "Booklet完整原文.md"。扫描该目录**所有图片**（其是图片在scans子目录，这一般是Booklet的扫描图片），整理Booklet**完整**原文（必须通过将本地图片传给你所用的大模型做ocr，注意ocr结果生成后需要检查文章内容准确度、完整度和语法错误。）
3. "Booklet完整中文翻译.md"。Booklet**完整原文****一字不落**的中文翻译。

# 注意

1. 遇到"Request too large (max 20MB). Double press esc to go back and try with a smaller file."就执行`/compact` 再继续
1. 每次生成"专辑基本信息.md"后，用subagent检查md文档的barcode/EAN是否与唱片封底的barcode相符，如果有错误需要纠正。
1. 每次生成"Booklet完整原文.md"后，用subagent再次扫描所有图片信息做ocr，检查是否有内容遗漏！
1. 每次生成"Booklet完整原文.md"后，用subagent检查文章内容准确度、完整度和语法错误，及时纠正。
1. 每次生成"Booklet完整中文翻译.md"后，用subagent对比"Booklet完整原文.md"和"Booklet完整中文翻译.md"的内容，检查文章内容准确度、完整度和语法错误，及时纠正。
1. 我们要求结果绝对完整和准确！不需要省token！没有处理完所有目录绝对不能停下来！
