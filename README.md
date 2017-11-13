# sublime-setting
### 工欲善其事必先利其器(配置sublime前端开发环境)

## 下载:
直接到官网下载安装sublime
[官网直达](http://www.sublimetext.com/)

## 安装插件
新版的sublime已经默认安装了package control，我们可以通过package control 安装适合自己的插件。如果没有安装package control，直接按command + shift + p 唤出命令列表，(windows用户把command键改为crtl键)输入install，点击install package control，耐心等待安装好package control会有弹框提示。
### 以下三步为安装插件的方法：

* 在sublime界面中，mac用户使用command + shift + p 唤出package control 命令列表，windows用户使用crtl + shift + p,为了方便本文中所有提到command键都是指windows中的crtl键。

* 在输入框中输入install，点击列表中的第一项（Package control:install package）,点击后列表会消失然后等待片刻，等sublime去加载完列表，会又弹出列表。

* 等插件列表加载出来后，输入想要安装的插件，会加载相应的插件，点击就会自动下载安装了，然后重复以上3步下载其它插件。

* 如果安装了一个插件，但是配置文件修改错了并且无法恢复，可以删除这个插件然后重新安装。删除的步骤：command + shift + p => 输入remove => 点击列表中要卸载的插件，稍等即可


## 常用插件和使用方法

### 1. Emmet
在package control 中输入emmet，选中第一个Emmet,Emmet前身是大名鼎鼎的Zen Coding,主要使用到它的两大功能：

* 自定义代码片段

	在窗口顶栏中找到 perferences -> Package Settings -> Emmet -> setting-user
	在文件中可以配置自定义模板，比如：
	
	```
	{
	    "snippets": {
	        "html": {
	        		"snippets": {
	                "hkhtml": "<!DOCTYPE html>\n<html>\n\n<head>\n    <meta http-equiv=\"Content-Type\" content=\"text/html; charset=UTF-8\" />\n    <title>todo-title</title>\n    <!-- 使用chrome和最新版ie渲染 -->\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge,chrome=1\" />\n    <!-- SEO页面关键词 -->\n    <meta name=\"keywords\" content=\"todo-content\" />\n    <!-- SEO页面描述 -->\n    <meta name=\"description\" content=\"todo-des\" />\n    <!-- 作者 -->\n    <meta name=\"author\" content=\"hekui\" />\n    <!-- 图标 -->\n    <link rel=\"shortcut icon\" type=\"image/ico\" href=\"/todo.ico\" />\n     <!-- 移动端 -->\n     <!--     <meta name=\"viewport\" content=\"width=device-width,initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no\" /> -->\n\n    <!-- 引入js-cdn,修改vue可引入其它库(cdn地址类式) -->\n    <script src=\"https://unpkg.com/vue\"></script>\n    <!-- 样式重置 -->\n    <link rel=\"stylesheet\" type=\"text/css\" href=\"https://cdn.bootcss.com/meyer-reset/2.0/reset.min.css\">\n</head>\n<body>\n</body>\n</html>"
	        		},
	            "abbreviations": {
	
	
	            }
	        }
	    }
	}
	```
	
	
	以上配置了hkhtml这个代码块，只要在sublime中输入hkhtml然后按tab键，就会自动生成后面的代码，效果如下：
	
	
	```
	<!DOCTYPE html>
	<html>
	
	<head>
	    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
	    <title>todo-title</title>
	    <!-- 使用chrome和最新版ie渲染 -->
	    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
	    <!-- SEO页面关键词 -->
	    <meta name="keywords" content="todo-content" />
	    <!-- SEO页面描述 -->
	    <meta name="description" content="todo-des" />
	    <!-- 作者 -->
	    <meta name="author" content="hekui" />
	    <!-- 图标 -->
	    <link rel="shortcut icon" type="image/ico" href="/todo.ico" />
	     <!-- 移动端 -->
	     <!--     <meta name="viewport" content="width=device-width,initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no" /> -->
	
	    <!-- 引入js-cdn,修改vue可引入其它库(cdn地址类式) -->
	    <script src="https://unpkg.com/vue"></script>
	    <!-- 样式重置 -->
	    <link rel="stylesheet" type="text/css" href="https://cdn.bootcss.com/meyer-reset/2.0/reset.min.css">
	</head>
	<body>
	</body>
	
	</html>
	```
	
	你可以把经常使用的代码设置成代码块，然后用快捷键来代替，这对于平时写个小demo或者写个练手项目还是很方便的，我会维护一个全面的常用代码块，需要请关注本文[github地址](https://github.com/hekui-github/sublime-setting)
	
* 	除了可以自定义代码片段，emmet还自带了代码片段功能，Emmet提供了很多快捷生成代码的规则，个人觉得只需要记住最常用的几个就够了，例如：
 
	div>(header>ul>li*2>a)+footer>p 	会生成代码 =>>
	
	```
	<div>
	    <header>
	        <ul>
	            <li><a href=""></a></li>
	            <li><a href=""></a></li>
	        </ul>
	    </header>
	    <footer>
	        <p></p>
	    </footer>
	</div>

	```
	上面例子中，> 表示父子关系，+ 表示兄弟关系 ，（）表示优先级，* 表示标签有几个
	
	有比如：
	div#header.wide>p.class1.class2 会生成代码 =>>
	
	```
		<div id = "header" class = "wide">
			<p class = "class1 class2"></p>
		</div>
	```
	上面例子中，在标签后面加上#表示id值，加上.表示class值，多个class和id可以混写在一起
	
	
	

	最后，如果你安装Emmet不成功，可能是没有翻墙，请戳 -> [一枝红杏 vpn](http://client.yizhihongxing.hk/aff.php?aff=1527)


### 2. SideBarEnhancements
>	SideBarEnhancements 插件大大增强了侧边栏的功能，比如可以移动文件、重命名文件、删除文件、备份文件、在磁盘中打开文件目录、双栏编辑文件、在浏览器中预览文件等，功能很简单只需要一个个尝试下就好了，是一个好用而简单的插件。

>其中在浏览器中打开的功能，可以代替view in browser这个插件，你可以指定它打开网页的浏览器，这样就不会担心360浏览器等浏览器捣乱了。(就算默认浏览器是360，只要你在sublime中指定了浏览器，会用指定的浏览器打开)。

指定浏览器配置如下：

perferences -> Package Settings -> Side Bar -> setting-user

```
{
	"default_browser": "chrome" //one of this list: firefox, aurora, chrome, canary, chromium, opera, safari
}
```


### 3. HTML-CSS-JS Prettify
	
> HTML-CSS-JS Prettify 是一款格式化代码的工具，安装好后，只需要command + shift + h 快捷键就可以格式化代码，或者 右键 -> HTML-CSS-JS Prettify -> prettify code 也可以格式化代码。

> prettify的安装需要依赖node.js，你需要安装node.js，如果还没有安装请戳 => [node.js官网](https://nodejs.org/en/) 

> 如果你已经安装了node.js 但是还是提示缺失node.js，或者提示路径不对， 你需要在prettify中配置node.js的路径. 

> perferences -> Package Settings -> HTML-CSS-JS Prettify -> set node path  把文件中的node.js路径设置成正确的就ok了，顺便提一句，只要把format_on_save 设置为 true，在每次保存文件的时候，它就会自动格式化代码了。




### 4. Doc​Blockr
> DocBlockr 可以跟js方法加上注释，虽然是不需要跟每个js方法加上注释的，但是在一些重要的、难懂的方法上加上注释是很必要的。
> 
> 安装好DocBlockr 在js方法前输入/**然后按下tab键就会生成注释的格式，如果你需要在注释里加上作者和日期等信息，就需要去配置下。下面配置加上了作者和日期。
> 
> perferences -> Package Settings -> DocBlockr -> setting-user 
 
 ```
  {
     "jsdocs_extra_tags": [
         "@Author hekui",
         "@DateTime {{date}}",
     ],
     "jsdocs_function_description": true
 }
 ```

### 5. SublimeLinter

> SublimeLinter 是一个语法检查器插件，安装它以后就可以很容易就提示出一些低级错误
> 
> 要想SublimeLinter 生效，你还得安装对应的语法检查器，SublimeLinter-csslint和SublimeLinter-jshint，安装方法和安装普通sublime插件一样，它们分别检查js代码和css代码
> 
>安装完这两个插件，还需要通过npm安装对应的eslint 和 csslint，最后才能生效。
>
>在命令行输入npm install -g csslint 安装csslint，输入npm install -g jshint 安装jshint，到最后这个css和js语法检查插件就装好了。如果你需要配置sublimelinter只需要右键=>sublimelinter就可以设置了，当然如果你想通过配置文件更详细的配置也是可以的。


### 6. LiveReload

> 修改过代码后，网页会自动刷新，这是会让很多人都心动的功能，而LiveReload就实现了这个功能。
> 
> 首先得安装LiveReload插件，正常通过package control安装就可以了，然后配置一下
> 
> Preference>Package Settings>LiveReload>Settings User
 ```
{
    "enabled_plugins": [
        "SimpleReloadPlugin",
        "SimpleRefresh"
    ]
}
 ```
 
> 最后在浏览器中安装LiveReload插件，我一般使用的是chrome，所以直接在chrome商店中直接下载安装就好了，安装好后在右上角插件列表中右键LiveReload点击管理扩展程序，进入liveReload设置界面，把允许访问文件网址勾选上就ok了。
> 
> 然后在浏览器中打开需要实时刷新的网页，在右上角把liveReload这个插件点击一下，图标会变成实心的就ok了。
> 
> 最后一步，是需要打开sublime中liveReload服务(前面步骤只是安装了，并没有打开服务)，command + shift + p => 输入liveReload然后选择LiveReload:Enable/disable plug-ins => 输入simple 选择 Enable - simple Reload，到这里网页实时刷新的功能就实现了。
> 
> 以后需要自动刷新网页的时候，就只需要3部，首先在浏览器中打开网页然后在右上角点击liveReload插件打开浏览端liveReload功能，然后在sublime中打开liveReload服务(sublime在第一次打开的时候需要重新打开liveReload服务，如果没关闭过不需要重新打开liveReload服务)。
> 
> 当然，访问chrome应用商店需要翻墙，请戳 -> [一枝红杏 vpn](http://client.yizhihongxing.hk/aff.php?aff=1527)

### 7. SublimeTmpl
> 通过SublimeTmpl可以新建一个文件的时候自定义模板，安装好后在file栏目中会有new file (SublimeTmpl)这一项，选择要新建的文件就可以新建自定义模板的文件。
> 
> > 通过配置这个文件可以修改new file(sublimeTpl)的子目录列表:
> > Preference>Package Settings> SublimeTmpl>menu default 

>你写的模板文件需要存放在/Packages/SublimeTmpl/templates这个目录下，如果你配置的vue文件，文件名应该为vue.tmpl，文件内容就是新建vue文件的默认模板。


### 8. FileDiffs

> fileDiffs 提供了对比文件对比功能，通过package control安装后，通过diff with previous 和前一个文件对比，diff with clipboard 就是和剪切板代码对比，对比后会生成一个对比之后的文件，这在拷贝代码和学习代码的时候非常有用。

### 9. AutoFileName
>	AutoFileName 提供了文件路径提示功能，比如你要选择images文件夹下的一个图片，输入images/后会提示出图片列表给你选择，安装方法还是通过package control安装。在输入文件路径的时候会自动提示。



### 10. ColorPicker
> ColorPicker提供了颜色面板选择的功能，写个demo啥的还是很方便的，通过package control 安装即可。commond + shift + c 会唤出调色面板

### 11.Autoprefixer
> Autoprefixer可以帮你加上css3前缀，减少工作量，直接通过package control安装即可。如果你使用构建工具，其实可以不使用它哦。



## 总结

> 一共凑了十个插件，应该来说都是通用的并且可以大大提高生产效率的插件，当然你还可以安装一些个性化的插件，比如你以vue作为技术栈就可能需要安装vue相关的插件，用sass写模块化css就需要安装sass bulid插件。
> 
> 如果是在过去，我肯定不会花这么大精力来装sublime插件和写对应的博客，在写完后还是感觉有蛮大的帮助的。
> 
> 每天进步一点点，愿学前端能改变你我以后的生活。


