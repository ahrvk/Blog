## NodeJS的依赖配置
#### nodejs的依赖包信息全部都在package.json文件里
```
{
    "name": "wblearn-blog",   //项目名称
    "title": "Wblearn Blog",  //项目标题
    "author": "Wblearn <1275660493@qq.com>",  //作者
    "version": "1.7.0",  //项目版本号
    "homepage": "https://wblearn.github.io",  //项目主页
    "repository": {
        "type": "git",
        "url": "https://github.com/wblearn/wblearn.github.io"
    },
    "bugs": "https://github.com/wblearn/wblearn.github.io/issues",
    "devDependencies": {
        "grunt": "~0.4.5",
        "grunt-contrib-less": "~0.11.4",
        "grunt-contrib-watch": "~0.6.1",
        "grunt-banner": "~0.2.3",
        "grunt-contrib-uglify": "~0.5.1"
    },
    "scripts": {
        "preview": "cd _site; python -m SimpleHTTPServer 8020",
        "py3view": "cd _site; python3 -m http.server 8020",
        "watch"  : "grunt watch & npm run preview & jekyll serve -w",
        "py3wa"  : "grunt watch & npm run py3view & jekyll serve -w",
        "boil"   : "git push boilerplate boilerplate:master",
        "push"   : "git push origin master --tag",
        "cafe"   : "git co gitcafe-pages; git merge master; git push gitcafe gitcafe-pages:gitcafe-pages --tag; git co master;"
    }
}
```
