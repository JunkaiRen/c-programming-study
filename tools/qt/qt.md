<div id="article_content" class="article_content tracking-ad" data-mod="popu_307" data-dsm="post">
        <div class="markdown_views"><h1 id="简介"><a name="t0" target="_blank"></a>简介</h1>

<p>Qt Creator是使用Qt开发的IDE。Qt支持Windows、Linux/Unix、Mac OS X、Android、BlackBerry、QNX等多种平台，Qt Creator为不同平台提供了统一的开发环境。</p>

<p>Qt Creator集成了Qt Designer、Qt Assistant、Help等工具。因此，在开发过程中可以很快的通过Designer来设计界面。如果想从Qt API中获得更详细的信息，只需要将光标定位到相应的类或函数并按下F1即可。</p>

<p></p><div class="toc"><div class="toc">
<ul>
<li><a href="#简介" target="">简介</a></li>
<li><a href="#欢迎模式" target="">欢迎模式</a><ul>
<li><a href="#工程" target="">工程</a></li>
<li><a href="#示例" target="">示例</a></li>
<li><a href="#教程" target="">教程</a></li>
</ul>
</li>
<li><a href="#编辑模式" target="">编辑模式</a><ul>
<li><a href="#编写代码" target="">编写代码</a></li>
<li><a href="#查找" target="">查找</a></li>
<li><a href="#重构" target="">重构</a></li>
<li><a href="#配置编辑器" target="">配置编辑器</a></li>
<li><a href="#字体和颜色" target="">字体和颜色</a></li>
<li><a href="#行为" target="">行为</a></li>
</ul>
</li>
<li><a href="#设计模式" target="">设计模式</a></li>
<li><a href="#调试模式" target="">调试模式</a><ul>
<li><a href="#调试c程序" target="">调试C程序</a></li>
</ul>
</li>
<li><a href="#帮助模式" target="">帮助模式</a><ul>
<li><a href="#使用帮助模式" target="">使用帮助模式</a></li>
<li><a href="#查看功能提示" target="">查看功能提示</a></li>
<li><a href="#在文档中查找信息" target="">在文档中查找信息</a></li>
<li><a href="#添加书签到帮助页" target="">添加书签到帮助页</a></li>
</ul>
</li>
</ul>
</div>
</div>
<p></p>



<h1 id="欢迎模式"><a name="t1" target="_blank"></a>欢迎模式</h1>

<p>进入Qt Creator后，会默认进入欢迎模式，默认选择的是”Project”选项。当然，通过它我们可以很容易对工程进行操作。</p>

<p><img src="http://img.blog.csdn.net/20151123213412114" alt="这里写图片描述" title=""></p>



<h2 id="工程"><a name="t2" target="_blank"></a>工程</h2>

<p><strong>New Project：</strong> <br>
新建工程。可以使Qt工程、Creator插件、C++库、其他项目。</p>

<p><strong>Open Project：</strong> <br>
打开工程</p>

<p><strong>Seeeions：</strong> <br>
会话。可以对会话进行管理，包括Clone。如果没打开工程，则显示的是最后一次打开的（会话）工程，否则，显示当前的会话（工程）。</p>

<p><strong>Recent Projects：</strong> <br>
列出最近打开的项目，通过它可以迅速打开指定项目。</p>

<p><strong>New to Qt：</strong> <br>
可以帮助你学习开发Qt项目和浏览Qt Creator。</p>

<p>Qt Account：Qt账户 <br>
Qt Cloud Services：Qt云服务 <br>
Online Community：网络社区 <br>
Blogs：博客 <br>
User Guide：用户手册</p>



<h2 id="示例"><a name="t3" target="_blank"></a>示例</h2>

<p>列出了所有的Qt Examples（Qt Widgets、QML相关的），选择任意一个你想到学习的示例打开，然后编译、运行。</p>

<p><img src="http://img.blog.csdn.net/20151123214522069" alt="这里写图片描述" title=""></p>

<p><img src="http://img.blog.csdn.net/20151123215744261" alt="这里写图片描述" title=""></p>

<p>建议大家一定要把”示例”用好，这绝对是熟悉Qt的一条捷径，里面有成为高手的必杀技。</p>



<h2 id="教程"><a name="t4" target="_blank"></a>教程</h2>

<p>里面包含大量的Qt讲解视频及文档。</p>

<p><img src="http://img.blog.csdn.net/20151123220311341" alt="这里写图片描述" title=""></p>



<h1 id="编辑模式"><a name="t5" target="_blank"></a>编辑模式</h1>

<p>当打开一个项目或者创建一个新的项目后，Qt Creator将会切换到编辑模式下。可以在左边看到项目文件，在中央区域看到代码编辑器。左边选中的文件将会被编辑器打开。</p>

<p>编辑器提供了语法高亮，代码补全和智能纠错的功能，也提供各种代码重构的命令。当使用编辑器工作时，你会觉得它的响应异常迅速。这感谢Qt Creaotor的开发者将这个工具做的如此杰出。</p>

<p><strong>在编辑模式工作</strong></p>

<p>可以编辑当前文件，添加新文件或者现有文件，添加库，还可以进行搜索结果的查找。</p>

<p><img src="http://img.blog.csdn.net/20151123221139420" alt="这里写图片描述" title=""></p>

<p>可以在编辑器工具栏中打开的文件和符号之间进行导航。也可以拆分视图同时对多个文件进行操作，添加书签，切换头文件/源文件、以及函数声明/定义等。</p>

<p><img src="http://img.blog.csdn.net/20151123221817759" alt="这里写图片描述" title=""></p>

<h2 id="编写代码"><a name="t6" target="_blank"></a>编写代码</h2>

<p><strong>语法高亮</strong></p>

<p>可以通过突出显示代码元素和块来编写格式良好的代码。使用语法高亮也可用于其他类型的文件，比如C++或QML。</p>

<p><strong>检查代码语法</strong></p>

<p>当写代码时，Qt Creator会检查错误并显示内嵌错误和警告消息。同样，可以检查一个JSON数据结构。此外，可以在项目中运行QML和JavaScript代码的静态检查，以找到共同的问题。</p>

<p><strong>完成代码</strong></p>

<p>Qt Creator可以预计你将写什么，并且为元素、属性和标识完成代码和代码段。</p>

<p><strong>缩进文本或代码</strong></p>

<p>Qt Creator根据C++、QML代码文件和其它文本文件指定的规则，进行缩进文本和代码。</p>

<p><strong>使用Qt Quick的工具栏</strong></p>

<p>当编辑QML代码时，可以指定QML组件的属性。对于某些属性并不简单，如颜色和字体。例如，很少有人能想象颜色＃18793f。如果要轻松编辑这些属性，可以使用Qt Quick工具栏。</p>

<p><strong>粘贴和提取代码段</strong></p>

<p>可以与其他开发人员合作通过从服务器粘贴和获取代码片段。例如，你可能会让同事来审查你计划提交到版本控制系统中的变化。</p>

<p><strong>使用文本编辑宏</strong></p>

<p>当你在代码编辑器中打开一个文件，可以记录键盘序列作为宏。然后，你可以运行重复序列的宏。可以保存最新的宏并分配快捷键运行，或从定位器运行。</p>



<h2 id="查找"><a name="t7" target="_blank"></a>查找</h2>

<p><strong>查找和替换</strong></p>

<p>当输入的时候，增量搜索会匹配窗口中高亮的字符串，同时输入高级搜索能够在文件系统中从当前打开的项目或文件中搜索。可以同时进行增量搜索和高级搜索。</p>

<p><strong>用定位器搜索</strong></p>

<p>定位器提供了Qt Creator中最简单的方法之一来浏览项目、文件、类、函数、文档和文件系统。</p>



<h2 id="重构"><a name="t8" target="_blank"></a>重构</h2>

<p><strong>重构代码</strong></p>

<ul>
<li>提高应用程序的内部质量</li>
<li>提高性能和可扩展</li>
<li>提高代码的可读性和可维护性</li>
<li>简化代码结构 </li>
</ul>

<p><strong>查找符号</strong></p>

<p>为了查找Qt C++或Qt Quick项目中特定符号或者QML组件的引用：</p>

<p>1、在编辑器中，将光标放在符号或组件上，然后选择：</p>

<ul>
<li>Tools -&gt; C++ &gt; Find Usages</li>
<li>Tools &gt; QML/JS -&gt; Find Usages</li>
<li>Ctrl+Shift+U</li>
</ul>

<p>Qt Creator在以下位置查找符号：</p>

<ol>
<li>列为项目的一部分文件</li>
<li>文件直接被项目文件所使用（例如，生成的文件）</li>
<li>使用框架和库的头文件</li>
</ol>

<p>注意：也可选择：Edit-&gt;Find/Replace-&gt;Advanced Find-&gt;C++ Symbols，以便搜索类、函数、枚举、和声明无论是项目的一部分文件或被代码使用的所有文件，如include文件。</p>

<p><img src="http://img.blog.csdn.net/20151123231606632" alt="这里写图片描述" title=""></p>

<p>2、”搜索结果”窗口打开并显示当前项目中符号的位置和数量。</p>

<p><img src="http://img.blog.csdn.net/20151123231837636" alt="这里写图片描述" title=""></p>

<p>可以通过以下方式浏览搜索结果： <br>
要直接进入到一个实例，双击搜索结果窗口中的实例。 <br>
要在实例之间移动，单击搜索结果窗口中的<img src="http://img.blog.csdn.net/20151123232617189" alt="这里写图片描述" title="">和<img src="http://img.blog.csdn.net/20151123232637073" alt="这里写图片描述" title="">。 <br>
要展开和折叠所有实例的列表，单击<img src="http://img.blog.csdn.net/20151123232734095" alt="这里写图片描述" title="">。 <br>
要清除搜索结果，请单击<img src="http://img.blog.csdn.net/20151123232744547" alt="这里写图片描述" title="">。</p>

<p><strong>应用重构操作</strong></p>

<p>Qt Creator允许快速、方便地重构代码。重构的操作是否可用取决于光标在代码编辑器的位置以及你是否写的是C++或者QML代码。</p>

<p>要使用重构，以C++代码为例，鼠标右键一个操作数、条件语句、字符串或名称打开上下文菜单。在QML代码，可以点击某个项目的ID或名称，在上下文菜单中选择重构，然后选择一个重构操作。也可以按Alt+Enter键打开包含在当前光标位置可重构行为的上下文菜单。</p>

<p><strong>重构C++代码</strong> </p>

<ul>
<li>参考：<a href="http://doc.qt.io/qtcreator/creator-editor-refactoring.html" title="重构" target="_blank">重构</a></li>
</ul>



<h2 id="配置编辑器"><a name="t9" target="_blank"></a>配置编辑器</h2>

<p>Qt Creator允许配置文本编辑器，以满足特定的需求。要配置编辑器，选择：工具-&gt;选项-&gt;文本编辑器。</p>

<p><img src="http://img.blog.csdn.net/20151124204756855" alt="这里写图片描述" title=""></p>

<p>这些设置适用于所有项目（全局设置），若要配置当前项目的文本编辑行为：</p>

<ol>
<li>选择：项目-&gt;编辑器。</li>
<li>编辑器设置选择”自定义设置”。</li>
<li>为项目指定文本编辑器设置。</li>
</ol>

<p><img src="http://img.blog.csdn.net/20151124205541761" alt="这里写图片描述" title=""></p>



<h2 id="字体和颜色"><a name="t10" target="_blank"></a>字体和颜色</h2>

<p><strong>配置字体</strong></p>

<p>你可以选择字体和字号，可以查看文本指定百分比的缩放设置。也可以按Ctrl++或Ctrl+- 放大或缩小，或者按住Ctrl键向上或向下滚动鼠标滚轮。要禁用鼠标滚轮的功能，选择：工具-&gt;选项-&gt;文本编辑器-&gt;行为，并取消选中”开启鼠标滚轮缩放”复选框。</p>

<p>抗锯齿默认情况下启用，以使屏幕上的文本看起来更平滑更易读。取消”抗锯齿”复选框以关闭抗锯齿。 </p>

<p><strong>定义配色方案</strong></p>

<p>可以选择语法高亮预定义的颜色方案中的一种或创建自定义配色方案。该配色方案适用于突出C++和QML文件和通用文件。</p>

<p>要创建一个颜色方案：</p>

<ol>
<li>选择工具-&gt;选项-&gt;文本编辑器-&gt;字体和颜色-&gt;复制。</li>
<li>输入颜色方案的名称（自定义），然后确定。</li>
<li>选择前景色。</li>
<li>选择背景色。</li>
</ol>

<p><img src="http://img.blog.csdn.net/20151124212846815" alt="这里写图片描述" title=""></p>

<p><img src="http://img.blog.csdn.net/20151124213036704" alt="这里写图片描述" title=""></p>

<p>这里是让大家了解如何自定义配色方案。当然，一般我不会去自己设置，我会使用”配色方案”中的默认选项”Dark”、然后”字号”改为12，其他均默认。这样，编辑器看起来就没有那么亮了，而且字体也变得比较大，看起来很舒服。</p>



<h2 id="行为"><a name="t11" target="_blank"></a>行为</h2>

<p>这里主要介绍缩进、文件编码格式</p>

<p><img src="http://img.blog.csdn.net/20151124220315574" alt="这里写图片描述" title=""></p>

<p><strong>制表符和缩进</strong></p>

<p>当键入文字或代码时，会根据所选择的文本编辑器或代码样式选项自动缩进。当你按下Tab键，选择一个块缩进。按Shift+Tab键来减少缩进。也可以禁用自动缩进。</p>

<p>可以为以下文件指定缩进：</p>

<ol>
<li>C++文件</li>
<li>QML文件</li>
<li>其他文本文件</li>
</ol>

<p>也可以分别为每个项目指定缩进。可以指定多套代码风格设置，并在它们之间轻松切换。此外，你可以导入和导出代码样式设置。</p>

<p>更多参考：</p>

<ul>
<li><a href="http://doc.qt.io/qtcreator/creator-indenting-code.html" title="缩进文件或代码" target="_blank">缩进文件或代码</a></li>
</ul>

<p><strong>文件编码</strong></p>

<p>Qt5需要UTF-8编码的源文件，因此在Qt Creator2.6版本默认编码从”System”改为”UTF-8”。尽管系统默认的编码设置为UTF-8，然而，默认编码字段仍然显示系统值。</p>

<p>检测正确的编码比较棘手，所以Qt Creator中不会尝试这样做。相反，当尝试编辑一个非UTF-8编码的文件，会显示错误信息：Error: Could not decode “filename” with “UTF-8”-encoding. Editing not possible.</p>

<p>要解决此问题，可以使用文件转换工具，如重新将文件编码转换为UTF-8。否则，正如预期一样，可能无法正常工作。</p>



<h1 id="设计模式"><a name="t12" target="_blank"></a>设计模式</h1>

<p>打开Qt Creator后，你会发现”设计”压根是不可用的，Why？呵呵哒。。。因为你没有编辑ui文件。</p>

<p>当我们双击工程中的一个ui文件时，默认会进入设计模式。</p>

<p><img src="http://img.blog.csdn.net/20151202214311373" alt="这里写图片描述" title=""></p>

<p>这里主要分为5个区域：</p>

<p><strong>窗口部件盒：</strong> <br>
主要包含布局、拉伸、按钮、视图（基于Model）、视图（基于Item）、容器、输入控件、显示控件等。</p>

<p><strong>窗口编辑器：</strong> <br>
可以利用控件区的部件来对窗口进行布局，达到想要的效果。</p>

<p><strong>对象查看器：</strong> <br>
将窗体编辑区的控件按照父子关系以树形结构显示出来。与窗体编辑区的共同特点是：可以改变对象名称、样式表、信号和槽等。</p>

<p><strong>属性值编辑器：</strong> <br>
可以编辑相应控件的属性值，例如：名称、大小、文本、样式等。</p>

<p><strong>动作、信号/槽编辑器：</strong> <br>
可以指定编辑动作及相应控件的信号与槽。</p>

<p>这里先做简单的一些了解，后面会对Designer做详细的介绍，更多精彩待续。。。</p>



<h1 id="调试模式"><a name="t13" target="_blank"></a>调试模式</h1>



<h2 id="调试c程序"><a name="t14" target="_blank"></a>调试C++程序</h2>

<p>要查看类及存储的数据，需要为程序设置断点。</p>

<p>如下所示：</p>

<p>1、为需要调试的代码设置断点。</p>

<p><img src="http://img.blog.csdn.net/20151202215332741" alt="这里写图片描述" title=""></p>

<p>2、开始”调试”。</p>

<p>或按下F5（调试-&gt;开始调试-&gt;开始调试）。</p>

<p>3、选择”Locals and Expressions”，查看类及数据成员信息。</p>

<p>也可以将鼠标滑过进行查看。</p>

<p><img src="http://img.blog.csdn.net/20151202215916298" alt="这里写图片描述" title=""></p>

<p>4、选择”Breakpoints”，查看断点信息。</p>

<p>包含：编号、函数、文件、行号等信息</p>

<p><img src="http://img.blog.csdn.net/20151202215712705" alt="这里写图片描述" title=""></p>

<p>5、选择”Stack”，查看堆栈信息。</p>

<p>包括：级别、函数、文件、行号等信息</p>

<p><img src="http://img.blog.csdn.net/20151202220022884" alt="这里写图片描述" title=""></p>



<h1 id="帮助模式"><a name="t15" target="_blank"></a>帮助模式</h1>



<h2 id="使用帮助模式"><a name="t16" target="_blank"></a>使用帮助模式</h2>

<p>Qt Creator完全集成Qt文档和Qt示例使用帮助插件。你可以为帮助模式添加外部文档，并且过滤文件显示更快地找到相关信息。此外，还可以为帮助页面添加书签。</p>

<ul>
<li><p>要查看文档，切换到帮助模式。</p></li>
<li><p>要查看Qt类或函数的提示（ToolTip）上下文敏感帮助，移动鼠标至类或函数上即可，如果帮助不可用，则提示显示符号的类型信息。</p></li>
<li><p>要显示一个Qt类或函数的全部信息，按F1。文档显示在代码编辑旁边的一个窗口，如果没有足够的垂直空间，则全屏显示帮助模式。</p></li>
<li><p>要选择和配置文档在帮助模式下的显示方式，选择：工具-&gt;选项-&gt;帮助。</p></li>
</ul>

<p><img src="http://img.blog.csdn.net/20151202223935179" alt="这里写图片描述" title=""></p>



<h2 id="查看功能提示"><a name="t17" target="_blank"></a>查看功能提示</h2>

<p>若要隐藏默认的提示功能，选择：工具-&gt;选项-&gt;文本编辑器-&gt;行为，”鼠标和键盘”选项中”Show help tooltips using the mouse”选择”Shift+鼠标悬停时” 。这样就可以通过按住Shift键来查看提示。要使用键盘快捷键来查看帮助提示，选择”Show help tooltips using keyboard  shortcut(Alt)”。</p>



<h2 id="在文档中查找信息"><a name="t18" target="_blank"></a>在文档中查找信息</h2>

<p>Qt Creator、Qt和其他Qt交付的产品包含了如.qch文件的文档。所有的文件是在帮助模式下访问。</p>

<p>要查找文档中的信息，请选择：</p>

<ul>
<li><p>书签：查看添加至书签的页面列表。</p></li>
<li><p>内容：查找安装在开发电脑中的所有文档，来浏览文档内容。</p></li>
<li><p>索引：基于所有已安装的文档中的关键字列表查找。</p></li>
<li><p>打开页面，以查看当前打开的文档页面的列表。</p></li>
<li><p>查找：在所有已安装的文档中进行查找。</p></li>
</ul>



<h2 id="添加书签到帮助页"><a name="t19" target="_blank"></a>添加书签到帮助页</h2>

<p>可以将书签添加到有用的帮助页面，之后在”书签”视图就可以轻松地找到它们。可以用页面标题作为书签，也可以将其更改为任何文本。可以在视图文件夹里组织书签。</p>

<p><img src="http://img.blog.csdn.net/20151202231205332" alt="这里写图片描述" title=""></p>

<p>要将书签添加到打开的帮助页面：</p>

<ol>
<li><p>单击工具栏上的<img src="http://img.blog.csdn.net/20151202231601631" alt="（添加书签）" title="">按钮。</p></li>
<li><p>在”添加书签”对话框中，单击确定，在选中的文件夹中保存书签。</p></li>
</ol>

<p>要导入和导出书签，选择：工具-&gt;选项-&gt;帮助-&gt;概要-&gt;导入或导出。</p></div>
        <script type="text/javascript">
            $(function () {
                $('pre.prettyprint code').each(function () {
                    var lines = $(this).text().split('\n').length;
                    var $numbering = $('<ul/>').addClass('pre-numbering').hide();
                    $(this).addClass('has-numbering').parent().append($numbering);
                    for (i = 1; i <= lines; i++) {
                        $numbering.append($('<li/>').text(i));
                    };
                    $numbering.fadeIn(1700);
                });
            });
        </script>
   
</div>


转发自http://blog.csdn.net/liang19890820/article/details/50004001
作者：一去丶二三里 博客地址：http://blog.csdn.net/liang19890820
