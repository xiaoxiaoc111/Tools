# Gitbook  notes

> GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书。 

## Reference

* [Gitbook官网](https://www.gitbook.com)
* [Gitbook_in_github](https://github.com/GitbookIO/gitbook)
* [Gitbook安装使用](https://www.liuchungui.com/blog/2015/12/26/gitbookan-zhuang-shi-yong/)



## Point

* 推荐使用[typora](https://typora.io/)编辑md文档,支持[gfm](https://guides.github.com/features/mastering-markdown/) 



## Command

* ```bash
	#根据 SUMARRY.md 文件的内容生成相应的目录和文件
	gitbook init [source_dir]      
	
	#安装 GitBook 插件
	gitbook install [options] [source_dir] 
	
	#根据文档目录构建书籍
	gitbook build [options] [source_dir] 
	
	#构建并且提供书籍的 web 托管
	gitbook serve [options] [source_dir] 
	
	#构建 pdf epub mobi 格式的电子书
	gitbook pdf  [options] [source_dir] 
	gitbook epub [options] [source_dir] 
	gitbook mobi [options] [source_dir] 
	
	#如果已绑定 GitBook.io，该命令可以直接发布书籍
	gitbook publish [source_dir]   
	
	#输出命令的使用说明
	-h, --help     
	#输出程序的版本号
	-V, --version 
	```



##  1.Install

* [Downloads node.js npm](http://nodejs.cn)

* Install

  ```bash
   npm install -g gitbook-cli 
  ```

## 2. Init gitbook

* Init gitbook

  ```bash
  mkdir test
  gitbook init
  ```

* Edit Summary.md 

  ```markdown
  # Summary
  
  This is the summary of my book.
  
  * [section 1](section1/README.md)
      * [example 1](section1/example1.md)
      * [example 2](section1/example2.md)
  * [section 2](section2/README.md)
      * [example 1](section2/example1.md)
  ```

* Init  gitbook

  ```bash
  gitbook init
  ```

## 3.Edit and look

* Local Web  Preview 

  ```bash
  gitbook serve
  ```

* Internet  Web  Preview 

  ```bash
  gitbook build
  ```

## 4.Push book to gitbook

*  Omitted 

## 5.Export book

*  Omitted 