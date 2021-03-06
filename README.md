 <!doctype html>
<html><head><title>图解Circos快速入门（Windows）</title><meta charset="UTF-8"><link href="http://fonts.googleapis.com/css?family=Crimson+Text:400,400italic,700,700italic|Roboto:400,700,700italic,400italic" type="text/css" rel="stylesheet"><style>/*
 * Copyright 2014 Quip
 *
 * Licensed under the Apache License, Version 2.0 (the "License"); you may
 * not use this file except in compliance with the License. You may obtain
 * a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
 * License for the specific language governing permissions and limitations
 * under the License.
 */

body {
    font-size: 15px;
    color: #333;
    background: #fff;
    padding: 60px 95px;
    max-width: 900px;
    margin: 0 auto;
    text-rendering: optimizeLegibility;
    font-feature-settings: "kern";
    font-kerning: normal;
    -moz-font-feature-settings: "kern";
    -webkit-font-feature-settings: "kern";
}

/* Headings */
h1, h2, h3, th {
    font-family: Roboto, sans-serif;
    font-weight: 700;
    margin: 0;
    margin-top: 1.25em;
    margin-bottom: 0.75em;
}

h1 {
    font-size: 35px;
    line-height: 42px;
}

h1:first-child {
    margin-top: 0;
}

h2 {
    font-size: 18px;
    line-height: 22px;
}

h3 {
    text-transform: uppercase;
    font-size: 13px;
    line-height: 16px;
}

/* Body text */
body, p, ul, ol, td {
    font-family: 'Crimson Text', serif;
    font-size: 16px;
    line-height: 20px;
}

blockquote, q {
    display: block;
    margin: 1em 0;
    font-style: italic;
}

blockquote a, q a {
    text-decoration: underline;
}

blockquote {
    padding-left: 10px;
    border-left: 4px solid #a6a6a6;
}

q {
    color: #a6a6a6;
    line-height: 40px;
    font-size: 24px;
    text-align: center;
    quotes: none;
}

q a {
    color: #a6a6a6;
}

code, pre {
    font-family: Consolas, "Liberation Mono", Menlo, "Courier Prime Web", Courier, monospace;
    background: #f3f3f3;
}

code {
    padding: 1px;
    margin: 0 -1px;
    border-radius: 3px;
}

pre {
    display: block;
    line-height: 20px;
    text-shadow: 0 1px white;
    padding: 5px 5px 5px 30px;
    white-space: nowrap;
    position: relative;
    margin: 1em 0;
}

pre:before {
    content: "";
    position: absolute;
    top: 0;
    bottom: 0;
    left: 15px;
    border-left: solid 1px #dadada;
}

/* Lists */
div[data-section-style="5"],
div[data-section-style="6"],
div[data-section-style="7"] {
    margin: 12px 0;
}

ul {
    padding: 0 0 0 40px;
}

ul li {
    margin-bottom: 0.4em;
}

/* Bulleted list */
div[data-section-style="5"] ul {
    list-style-type: disc;
}
div[data-section-style="5"] ul ul {
    list-style-type: circle;
}
div[data-section-style="5"] ul ul ul {
    list-style-type: square;
}
div[data-section-style="5"] ul ul ul ul {
    list-style-type: disc;
}
div[data-section-style="5"] ul ul ul ul ul {
    list-style-type: circle;
}
div[data-section-style="5"] ul ul ul ul ul ul {
    list-style-type: square;
}

/* Numbered list */
div[data-section-style="6"] ul {
    list-style-type: decimal;
}
div[data-section-style="6"] ul ul {
    list-style-type: lower-alpha;
}
div[data-section-style="6"] ul ul ul {
    list-style-type: lower-roman;
}
div[data-section-style="6"] ul ul ul ul {
    list-style-type: decimal;
}
div[data-section-style="6"] ul ul ul ul ul {
    list-style-type: lower-alpha;
}
div[data-section-style="6"] ul ul ul ul ul ul {
    list-style-type: lower-roman;
}

/* Checklist */
div[data-section-style="7"] ul {
    list-style-type: none;
}

div[data-section-style="7"] ul li:before {
    content: "\2610";
    position: absolute;
    display: inline;
    margin-right: 1.2em;
    margin-left: -1.2em;
}

div[data-section-style="7"] ul li.parent:before {
    content: "";
}

div[data-section-style="7"] ul li.parent {
    font-weight: bold;
}

div[data-section-style="7"] ul li.checked {
    text-decoration: line-through;
}

div[data-section-style="7"] ul li.checked:before {
    content: "\2611";
    text-decoration: none;
}

/* Tables */
div[data-section-style="8"] {
    margin: 12px 0;
}

table {
    border-spacing: 0;
    border-collapse: separate;
    border: solid 1px #7c7c7c;
    box-shadow: 0 1px 2px rgba(0, 0, 0, .25);
    table-layout: fixed;
    position: relative;
}

table th, table td {
    padding: 2px 2px 0;
    min-width: 1.5em;
    word-wrap: break-word;
}

table th {
    border-bottom: 1px solid #ccc;
    background: #f0f0f0;
    font-weight: bold;
    vertical-align: bottom;
    color: #3a4449;
    text-align: center;
}

table td {
    padding-top: 0;
    border-left: 1px solid #e1e1e1;
    border-top: 1px solid #e1e1e1;
    vertical-align: top;
}

table td.bold {
    font-weight: bold;
}

table td.italic {
    font-style: italic;
}

table td.underline {
    text-decoration: underline;
}

table td.strikethrough {
    text-decoration: line-through;
}

table td.underline.strikethrough {
    text-decoration: underline line-through;
}

table td:first-child {
    border-left: hidden;
}

table tr:first-child td {
    border-top: hidden;
}

/* Images */
div[data-section-style="11"] {
    margin-top: 20px;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
}

div[data-section-style="11"][data-section-float="0"] {
    clear: both;
    text-align: center;
}

div[data-section-style="11"][data-section-float="1"] {
    float: left;
    clear: left;
    margin-right: 20px;
}

div[data-section-style="11"][data-section-float="2"] {
    float: right;
    clear: right;
    margin-left: 20px;
}

div[data-section-style="11"] img {
    display: block;
    max-width: 100%;
    height: auto;
    margin: auto;
}

hr {
    width: 70px;
    margin: 20px auto;
}
</style></head><body><h1 id='fWRACAbnU6D'>图解Circos快速入门（Windows）</h1>

0. 前言<br/>

Circos是环形图绘制工具，组学数据展示常用工具，基因组文章必备图绘制工具。在三大操作系统均可使用，因为是用Perl写的，Perl能用的环境，Circos都work。官网：<a href="http://circos.ca">http://circos.ca</a><br/>

优点：方便，强大<br/>

缺点：依赖较多Perl模块，增加了入手难度；<br/>

基础：perl 5、ActivePerl<br/>

<h2 id='fWRACA4G8Y8'>1. 查看perl版本</h2>

打开cmd，输入命令：<br/>

<pre id='fWRACA9a83z'>perl -v</pre>

显示：<br/>

<div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/HVdQKn10LfwRMmZbXDGTDA?a=HixDa1fJvB3HEM6RX7mbsGZfW3qXDHEaZdGUxwkdP0Ea' id='fWRACA5Ze56' alt='' width='675' height='304'></img></div><br/>

表明我的perl版本是5.16.2，可用。<br/>

如果没有安装perl。Windows推荐安装ActivePerl和StrawberryPerl，ActivePerl的Perl Package Manager比较好用，StrawberryPerl的环境配置更容易。我是都安了。<br/>

<h2 id='fWRACAEwHm8'>2. 安装模块</h2>

打开Perl Package Manager，在搜索框依次搜索以下模块。（使用CPAN也好，原理都一样）<br/>

<blockquote id='fWRACA6KQXZ'>Config::General (v2.50 or later)、Font::TTF、GD、List::MoreUtils、Math::Bezier、Math::Round、Math::VecStat、Params::Validate、Readonly、Regexp::Common、Set::IntSpan (v1.16 or later)、Text::Format</blockquote>

<div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/trbvF8Zj7FmFCElHXEaQEQ?a=UjXsc9s8YmKUIJMKvFwN3H709WcgkCZxLDfZagaLW48a' id='fWRACAMAIIY' alt='' width='585' height='596'></img></div>以Config::General 为例：<br/>

<div data-section-style='5'><ul id='fWRACABk4wI'><li id='fWRACAFSD0p' class='' value='1'>搜索Config-General，选择标记按钮Mark for install

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/Lw6wPzOLkLNFJnmCDvuMYA?a=w1bqKWGwmJkAr75fm9GkG6GYqJjdCELQvsRMOgsJMAIa' id='fWRACAsSolQ' alt='' width='569' height='595'></img></div><div data-section-style='5'><ul id='fWRACAiWlOA'><li id='fWRACAnx695' class='' value='1'>依次搜索剩余模块，并标记，如果已安装最新版包无需标记

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/MbWAWMnWuQ2xrBiTtfEtYw?a=6mzzHaMPiSIOwFOMVmhM4M80zHIqkVG6ferf4EjBnv8a' id='fWRACAfjq8D' alt='' width='566' height='595'></img></div><div data-section-style='5'><ul id='fWRACAjmwZR'><li id='fWRACAGdnv4' class='' value='1'>完成后选择查看待安装/移除包按钮（快捷键Ctrl-4），并清除搜索栏内容，可见已标记的所有包，核对

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/MbWAWMnWuQ2xrBiTtfEtYw?a=6mzzHaMPiSIOwFOMVmhM4M80zHIqkVG6ferf4EjBnv8a' id='fWRACAPf8uO' alt='' width='566' height='595'></img></div><div data-section-style='5'><ul id='fWRACA8Bu1N'><li id='fWRACAu1LDr' class='' value='1'>点击运行按钮

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/mk9y4uB49Pdd7RDNt8Ev-A?a=lW9AolmDlkWwEWaC4atsVraamRKvKvfaWtnwu7HW5V4a' id='fWRACAJ6sK9' alt='' width='569' height='596'></img></div><div data-section-style='5'><ul id='fWRACAZoUia'><li id='fWRACA7ziOZ' class='' value='1'>询问是否准备好安装，提示有依赖的包需要安装。选择确定

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/DQ7g5-Zo9KMS3P_eNGISRQ?a=xCaMIKj7zAuEVCSCPdKNzz0NuJLY4i1LPmzApC4EFWga' id='fWRACAHdBZY' alt='' width='568' height='596'></img></div><div data-section-style='5'><ul id='fWRACAckXC2'><li id='fWRACA6acw4' class='' value='1'>开始执行下载及安装，等待5分钟，安装完成

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/WjDXmKqNg9LEz5HBz3XoLQ?a=8NIul5LHato7OTHd2Ih2U6Z0hdtbn67sb9ftaVaX6o8a' id='fWRACAYSsGb' alt='' width='581' height='596'></img></div><h2 id='fWRACAKhQU8'>3. Circos下载</h2>

<div data-section-style='5'><ul id='fWRACAkEtDc'><li id='fWRACAb0rKJ' class='' value='1'>进入Circos下载页面：<a href="http://www.circos.ca/software/download/circos/">http://www.circos.ca/software/download/circos/</a>

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/y3SSkBrZoPyrBUPD-Btvcw?a=IsPb8Csl9Yb5acLiELcO4O5QovUP7Tf3RV4xzXPaMaAa' id='fWRACADhole' alt='' width='800' height='432'></img></div><div data-section-style='5'><ul id='fWRACA764Gz'><li id='fWRACA8Rmax' class='' value='1'>选择最新版本circos-0.69-5.tgz，下载

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/AzDtPGY3CsDIALqvJWa5nA?a=PfB1a7Cms2z6rDEDhWk1VGxxyrWJu2cWpKofThtCQd4a' id='fWRACAQKLdC' alt='' width='448' height='337'></img></div><div data-section-style='5'><ul id='fWRACAInYng'><li id='fWRACAHIMPX' class='' value='1'>解压

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/NA-IKN5pBkoL-lxSXYKWjw?a=9aQ5nEXzpSageLriswKjyApcg5s7Fd7OiuOJS7vqpWoa' id='fWRACA168Ut' alt='' width='379' height='365'></img></div><div data-section-style='5'><ul id='fWRACA9Tvn8'><li id='fWRACAetgJO' class='' value='1'>文件夹内容：

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/v5tPQhCERLlkgcL3tKK7WA?a=uZzhNKHCePxpLZyDpzDjIeSfXW59Ro7vnh6R4COcOa0a' id='fWRACAjcM7g' alt='' width='668' height='495'></img></div><h2 id='fWRACA1iQVL'>4. 示例下载</h2>

<div data-section-style='5'><ul id='fWRACAvRlpL'><li id='fWRACAn4DM7' class='' value='1'>下载示例数据：<a href="http://www.circos.ca/software/download/tutorials/">http://www.circos.ca/software/download/tutorials/</a>

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/XZIjOyfbVbbwBwNmnWlbfw?a=TwaXe9YkzKcXnU4I5f0eyGDeE1SMwI6UX9aG9iKbUfsa' id='fWRACAePZpM' alt='' width='800' height='444'></img></div><div data-section-style='5'><ul id='fWRACApoIlU'><li id='fWRACA4ardZ' class='' value='1'>选择最新版：circos-tutorials-0.67.tgz，下载

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/9lb0Bk11SirEM4RlhXANXA?a=uvrv5JkpSMMiJuLjKCHQi3EeFm6yuz9pdsNbOaY4Hksa' id='fWRACA5SU1i' alt='' width='446' height='339'></img></div><div data-section-style='5'><ul id='fWRACAbFT3n'><li id='fWRACAjv2p3' class='' value='1'>解压

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/splabPG-1akQg_rAV3aR5A?a=bDAAZuOsCJvzsUj90PgNA0MVTnpbe4rdHLW2sHupxska' id='fWRACAfVpWk' alt='' width='377' height='364'></img></div><div data-section-style='5'><ul id='fWRACAt9UWO'><li id='fWRACAAAyev' class='' value='1'>文件夹内容：

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/jihFQtHsgFy_W-BcAvdX2A?a=AJr9ILeEH8YhEJf0jy7aUjQHtIRLqka56Y2rba3lyO8a' id='fWRACA723W3' alt='' width='654' height='148'></img></div><br/>

<h2 id='fWRACAdqe4Q'>5. 运行Circos</h2>

<div data-section-style='5'><ul id='fWRACAOakQQ'><li id='fWRACACVRxE' class='' value='1'>进入工作目录

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/tVrr2egyiq7PP1KXsXZrfA?a=hyP0mQ5YUxrIcsQUse6KSda8bhaQaMcB7fLiv6zqUJMa' id='fWRACAIk1aZ' alt='' width='676' height='43'></img></div><div data-section-style='5'><ul id='fWRACApqZlK'><li id='fWRACA2KzUE' class='' value='1'>运行示例程序

<br/></li></ul></div><pre id='fWRACAGO7Io'>perl bin\circos -conf ..\..\circos-tutorials-0.67\circos-tutorials-0.67\tutorials\2\2\circos.conf -outputdir . -outputfile tutorial_image.png</pre>

<div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/G0ynPeWDBdrLNv56_p7-Ew?a=4xqerv4sfjj7raSDEiupsaQm7F81XVBwu3DosUY9oKwa' id='fWRACATlvhX' alt='' width='676' height='90'></img></div><div data-section-style='5'><ul id='fWRACAT0qjN'><li id='fWRACALkS5i' class='' value='1'>报错缺失包 Statistics::Basic

<br/></li></ul></div><h2 id='fWRACAZ5Wnz'>6. debug</h2>

<div data-section-style='5'><ul id='fWRACAZQWeG'><li id='fWRACASQdst' class='' value='1'>用PPM（Perl Package Manager）按之前的方法下载并安装包

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/eg57oLWAMDOm351TeB8-uw?a=dm6Wf1Io4HXEpGmLdAYVOC9ubt9a0dUI0ACRW1wgpSYa' id='fWRACAOEEiv' alt='' width='568' height='596'></img></div><div data-section-style='5'><ul id='fWRACAPTssL'><li id='fWRACAu2kjU' class='' value='1'>重新运行程序

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/m470q5ofnLCJAPtwiPZ0pA?a=LpZTC0JvFi7gmOXgAPlpaWnoJNdX7Zf0SRd2GM2D8h4a' id='fWRACAh9HjP' alt='' width='668' height='754'></img></div><div data-section-style='5'><ul id='fWRACAczzbb'><li id='fWRACAXrIyb' class='' value='1'>成功

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/EoJ7YjYxBuZgKqK_HalElg?a=yVS0uicqD8BDxE8GDbZFMknlGCbjIWRi3TtPpdcEpYoa' id='fWRACAvUUs7' alt='' width='633' height='503'></img></div><div data-section-style='5'><ul id='fWRACALlWsj'><li id='fWRACAb3HLM' class='' value='1'>矢量图：

<br/></li></ul></div><div data-section-style='11' style='max-width:100%'><img src='https://quip.com/blob/fWRAAAsICaC/bGiHd-kHj4PHeYmdPSLdAg?a=NvUB8gXOOvRkNNFHfONDqPxgTHP4LNtaULlv0KDehhka' id='fWRACAxADQO' alt='' width='800' height='449'></img></div><h2 id='fWRACAdzzeG'>7. 深入学习</h2>

查看官方帮助文档：<a href="http://www.circos.ca/documentation/tutorials/">http://www.circos.ca/documentation/tutorials/</a>；对应每一小节都提供数据练习，找到适合自己的模式，套入符合规范的数据即可。<br/>

<h2 id='fWRACAewobH'>感想</h2>

<div data-section-style='6'><ul id='fWRACAjJdPb'><li id='fWRACAXoHTr' class='' value='1'>Circos官网非常好，文档写得也很好，有很多观点性的篇章能学到工具之外的知识，是我目前接触过文档写的最好的之一

<br/></li><li id='fWRACAz9Lb4' class=''>Circos和Qiime类似，都依赖很多关联包，都安装全就没问题了

<br/></li><li id='fWRACAJVxdP' class=''>Circos非常强大，值得学习扎实，比自己写方便太多

<br/></li><li id='fWRACATYX0k' class=''>Circos版本维护良好

<br/></li></ul></div><br/>

</body></html>
