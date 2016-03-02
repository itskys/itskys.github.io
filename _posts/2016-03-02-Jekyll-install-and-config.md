---
layout: post
title: Jekyll安装与配置
---
{{title.page}}

***
####1. Install GCC
```
	gcc -v
	yum install gcc
```
####2. install rvm
```
	cd /home/
	curl -L get.rvm.io | bash -s stable
	vi .bashrc
	  source /etc/profile.d/rvm.sh
	rvm -v
```
####3. install ruby
```
	rvm install 
	rvm list
	rvm use
	ruby -v
	gem -v
	gem update --system
	gem -v
```

####4. install jekyll
```
	gem install ruby-devel
	gem install jekyll
	jekyll -v
```

####5. install others
```
	gem install RedCloth
	gem install rdiscount
	jekyll --rdiscount
	markdown: rdiscount
	yum install python-pyments
```

####6. Run jekyll
```
	jekyll build
	jekyll --server
```

####7. Fork a jekyll repo

####8. modify

####9. addtions


***
##Links
* [markdown](http://www.itskys.com/2016/02/28/markdown.html)
* [git](http://www.itskys.com/2016/03/02/git.html)
* [vi/vim](http://www.itskys.com/2016/03/02/vi-vim.html)
***


 	
