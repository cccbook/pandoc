# MarkdownPaper

本專案衍生自以下的 gist 專案

* https://gist.github.com/maxogden/97190db73ac19fc6c1d9beee1a6e4fc8

經我研究後，發現以下指令可以讓上述方法運用在中文論文上！

```
$ pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s cpaper.md -o cpaper.pdf --pdf-engine=xelatex -V mainfont='SimSun'
```

於是我決定將該專案延伸後成為一個正式的 github 專案！


## 安裝

* pandoc : choco install pandoc
    * windows 版的 pandoc-citeproc 預設就會安裝 (內文有引用才會出現在文獻區！)
* Windows : 
    * MikTex (TexLive)

## pandoc 使用

* https://pandoc.org/MANUAL.html#general-writer-options
    * 注意看 General writer options

## bat 失敗

```
D:\ccc\paper\markdownPaper\cpaper>pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s cpaper.md -o cpaper.pdf --pdf-engine=xelatex -V mainfont='SimSun'
xelatex: warning: running with administrator privileges
miktex-maketfm: warning: running with administrator privileges
miktex-makemf: warning: running with administrator privileges

Sorry, but miktex-makemf did not succeed.

The log file hopefully contains the information to get MiKTeX going again:

  C:\Users\user\AppData\Local\MiKTeX\2.9\miktex\log\miktex-makemf.log
miktex-hbf2gf: warning: running with administrator privileges
Couldn't open `'SimSu.cfg'
```


## 執行方法 (沒中文)

```
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s paper.md -o paper2.pdf
pdflatex: warning: running with administrator privileges
pdflatex: warning: running with administrator privileges
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s paper.md -o paper2.pdf
pdflatex: warning: running with administrator privileges
pdflatex: warning: running with administrator privileges
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s paper.md -o paper2.html
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=onecolumn --variable papersize=a4paper -s paper.md -o paperOneColumn.html
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=onecolumn --variable papersize=a4paper -s paper.md -o paperOneColumn.pdf
pdflatex: warning: running with administrator privileges
pdflatex: warning: running with administrator privileges
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=onecolumn --variable papersize=a4paper -s paper.md -o paperOneColumn.odt
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s paper.md -o paperTwoColumn.odt
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s cpaper.md -o cpaper.odt
```

## 執行方法 (有中文) -- 參考 https://github.com/jgm/pandoc/wiki/Pandoc-with-Chinese

```
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s cpaper.md -o cpaper.pdf  --latex-engine=xelatex -V mainfont='WenQuanYi Micro Hei Mono'
--latex-engine has been removed.  Use --pdf-engine instead.
Try pandoc.exe --help for more information.
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s cpaper.md -o cpaper.pdf --pdf-engine=xelatex -V mainfont='WenQuanYi Micro Hei Mono'
PS D:\ccc\paper\pandoc\scipdf2> pandoc --filter pandoc-citeproc --bibliography=paper.bib --variable classoption=twocolumn --variable papersize=a4paper -s cpaper.md -o cpaper.pdf --pdf-engine=xelatex -V mainfont='SimSun'
xelatex: warning: running with administrator privileges
miktex-dvipdfmx: warning: running with administrator privileges
xelatex: warning: running with administrator privileges
miktex-dvipdfmx: warning: running with administrator privileges
```
