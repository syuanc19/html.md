# html.md
# 基本结构

```html
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

------

# 基礎文本格式
<table>
	<thead>
		<tr>
			<th>標籤</th>
			<th>效果</th>
		</tr>
	</thead>
 	<tbody>
		<tr>
			<td>&lt;strong&gt;, &lt;b&gt;</td>
			<td><strong>加粗</strong></td>
		</tr>
		<tr>
			<td>&lt;em&gt;, &lt;i&gt;</td>
			<td><em>傾斜</em></td>
		</tr>
		<tr>
			<td>&lt;ins&gt;, &lt;u&gt;</td>
			<td><ins>下划線</ins></td>
		</tr>
		<tr>
			<td>&lt;del&gt;, &lt;s&gt;</td>
			<td><del>刪除線</del></td>
		</tr>
	</tbody>
 
</table>

## 圖像標籤
`<img src="圖像url" alt="替代文字" title="懸停時提示文字>`
<br>

## 音頻標籤
`<audio src="音頻url" control>` <br><br>
屬性：
<ul>
	<li>controls 控制面板</li>
	<li>loop 循環播放</li>
	<li>autoplay 自動播放</li>
</ul>

## 影片標籤
`<video src="影片url" controls>`<br><br>
屬性：
<ul>
	<li>controls 控制面板</li>
	<li>loop 循環播放</li>
	<li>autoplay 自動播放</li>
	<li>muteplay 靜音播放</li>
</ul>

------

## 路徑- 相對與絕對<br>
相對路徑：從&nbsp;<strong>當前文件位置</strong>&nbsp;出發尋找目標<br>
&nbsp;<strong>/</strong>&nbsp;表示進入某個文件夾裡面<br>
&nbsp;<strong>.</strong>&nbsp;表示當前文件所在的資料夾<br>
&nbsp;<strong>..</strong>&nbsp;代表上一級<br>
> e.g. ../../example/a.jpg 訪問以當前位置為主，上上個資料夾的example裡的a.jpg<br>

絕對路徑：從&nbsp;<strong>硬碟</strong>&nbsp;出發尋找目標(windows從硬碟出發，Mac從根目錄出發)<br>

> e.g. F:\User\Desktop\example.jpg<br>


------
# **表格** 

> table嵌套tr, tr嵌套 th/td, thead與 tbody則用來使語法更工整 <br>
> 表格最好用来展示数据，而非用来布局

```html
<table align="center" border="1" cellpadding="1" cellspacing="0" width="500" height="500">
	<thead>
		<tr>
			<th> 标题单元格1 </th>
			<th> 标题单元格2 </th>
			<th> 标题单元格3 </th>
        </tr>
	</thead>
	<tbody>
		<tr>
			<td> 内文1 </td>
			<td> 内文2 </td>
			<td> 内文3 </td>
		</tr>
	</tbody>
</table>
```
**效果：**

<table>
	<thead>
		<tr>
			<th> 标题单元格1 </th>
			<th> 标题单元格2 </th>
			<th> 标题单元格3 </th>
        </tr>
	</thead>
	<tbody>
		<tr>
			<td> 内文1 </td>
			<td> 内文2 </td>
			<td> 内文3 </td>
		</tr>
	</tbody>
</table>


| 标签名                       | 含义                            |
| ---: | ---- |
| `taable`        | 表格标签                            |
| `thead`,`tbody` | 标题、内文群组标签                  |
| `th`            | [th] 标题标签(自动置中加粗)             |
| `tr`,`td` | [tr] 行标签、[td] 内文标签 |

## table属性

> (弃用) 因后续会在`CSS`里设置

align、bgcolor、border、cellpadding、cellspacing

## 合并表格
|     标签名     |  含义  |
| :------------: | :----: |
| `colspan=数字` | 行合并 |
| `rowspan=数字` | 列合并 |

<hr>

# **自定义列表**

```html
<dl>
	<dt>名词一</dt>
	<dd>名词一释义</dd>
	<dd>名词二释义</dd>
</dl>
```

> `dl`里只允许有 `dt` or `dd`，但`dt` `dd`里可以放任何标签


------

# **表单**

```html
<form action="url地址" method="get/post" name="表单域名称">
```

| method = get                                                 | method = post                                                |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| <img src="https://github.com/syuanc19/Image-Hosting/blob/main/image-20221204031948665.png"> | <img src="https://github.com/syuanc19/Image-Hosting/blob/main/image-20221204032010539.png"> |
| /xxx.php?username=syuan19&pwd=a140472 | /xxx.php |

## input

```html
<input type="属性" name="name" value="value" checked="checked">
```

> `checked="checked"` 可实现选项标签预设选择值

<table>
<form>
<thead>
    <tr>
        <th>属性</th>
        <th>描述</th>
        <th>效果</th>
    </tr> 
</thead>
<tbody>
   <tr>
       <td>button</td><br>
       <td>可点击按钮</td>
       <td><img src="https://raw.githubusercontent.com/syuanc19/picbed/main/2023/07/upgit_20230713_1689186646.png"></td>
    </tr>
    <tr>
        <td>checkbox</td>
        <td>复选框</td>
        <td><input type="checkbox" name="checkbox" value="checkbox1" checked=checked>复选1 <input type="checkbox" name="checkbox" value="checkbox2">复选2</td>
    </tr>
    <tr>
        <td>file</td>
        <td>供文件上传</td>
        <td><input type="file" name="file" value="upload"></td>
    </tr>
    <tr>
        <td>password</td>
        <td>密码字段</td>
        <td><input type="password" name="pwd" placeholder="请输入密码"></td>
    </tr>
    <tr>
        <td>radio</td>
        <td>单选按钮 (禁止复选需定义相同name)</td>
        <td><input type="radio" name="必须相同" value="1" checked=checked>选项1<br /><input type="radio" name="必须相同" value="2">选项2<br /><input type="radio" name="必须相同" value="3">选项3</td>
    </tr>
    <tr>
        <td>reset</td>
        <td>重置按钮</td>
        <td><input type="reset" name="reset" value="重置"></td>
    </tr>
    <tr>
        <td>submit</td>
        <td>提交按钮</td>
        <td><input type="submit" name="submit" value="点击上传"></td>
    </tr>
    <tr>
        <td>text</td>
        <td>单行输入字段，默认20em</td>
        <td><input type="text" name="text" placeholder="请输入文字"></td>
    </tr>
        <tr>
        <td>image</td>
        <td>图像形式的提交按钮</td>
        <td><input type="image" name="image" src="xx.jpg" width="150" alt="an image"></td>
    </tr>
    <tr>
        <td>hidden</td>
        <td>隐藏的输入段</td>
        <td><input type="hidden" name="hidden" value="hidden"></td>
    </tr>
</tbody>
</table>
<hr>

## Label标签

```html
<input type="text" id="指定id"> <Label for="指定id"> 用户名: </Label> 
```

> 能实现点击标签名也能选取框元素的功能




## select列表

<table>
	<form>
		<tr width="350" height="10">
			<th>代码</th>
			<th>效果</th>
		</tr>
		<tr>
			<td>
					&lt;select&gt; <br>
    					&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;option&gt;选项一&lt;/option&gt;<br>
    					&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;option&gt;选项二&lt;/option&gt;<br>
    					&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;option&gt;选项三&lt;/option&gt;<br>
					&lt;/select&gt;
    		<td>
    			<form>
    				<select>
     					<option>选项一</option>
      					<option>选项二</option>
    					<option>选项三</option>
    				</select>
    			</form>
    		</td>
    	</tr>
    <form>
</table>

> `selected="selected"` 可实现选项标签预设选择值

**效果：**

<table>
	<form>
		<tr width="350" height="10">
			<th>代码</th>
			<th>效果</th>
		</tr>
		<tr>
			<td>
					&lt;select&gt; <br>
    					&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;option&gt;选项一&lt;/option&gt;<br>
    					&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;option&gt;选项二&lt;/option&gt;<br>
    					&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;option&nbsp;selected="selected"&gt;选项三		
                		&lt;/option&gt;<br>
					&lt;/select&gt;
    		<td>
    			<form>
    				<select>
     					<option>选项一</option>
      					<option>选项二</option>
    					<option selected="selected">选项三</option>
    				</select>
    			</form>
    		</td>
    	</tr>
    <form>
</table>



## textarea文本域

<table>
	<tr>
		<th>代码</th>
		<th>效果</th>
	</tr>
	<tr>
		<td>自我介绍：<br>
				&lt;textarea placeholder="篇幅120为限" maxlength="120"&gt;<br>
				&lt;/textarea&gt;
		</td>
		<td>
			<form>
				自我介绍：<textarea placeholder="篇幅120为限" maxlength="120"></textarea>
			</form>
		</td>
	</tr>
</table>

### textarea属性

> 一般不用，会在`CSS`里改

```html
<textarea cols="100" rows="5"></textarea>
```

| 标签名 | 含义           |
| ------ | -------------- |
| `cols` | 每行中的字符数 |
| `rows` | 预设显示的行数 |

