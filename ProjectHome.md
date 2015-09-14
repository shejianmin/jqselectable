## jQselectable ##
<strong>日本語ドキュメントを更新しました：<a href='http://moto-mono.net/2008/09/14/jqueryselectable.html'>selectボックスをシンプルなプルダウンに拡張するjQselectable | 5509(+1)</a></strong>

Selectbox gets more usability with jQselectable.


---


## Demo ##
<a href='http://jqselectable.googlecode.com/svn/trunk/index.html'>View the live demo</a>


---


## Download ##
<a href='http://jqselectable.googlecode.com/files/jqselectable.1.3.2.zip'>jqselectable1.3.1</a>


---


## Usage ##
### HTML ###
Pages that using jQselectable has been loading the 'jQuery'.
```
<script type="text/javascript" src="http://www.google.com/jsapi"></script>
<script type="text/javascript">google.load("jquery", "1.3.2");</script>
```
Loading both css and js files.
```
<style type="text/css" href="skin/selectable/style.css" />
<script type="text/javascript" src="js/jQselectable.js"></script>
```
### JS ###
#### Basic ####
```
$(object).jQselectable();
```

And you also use the old method that is <strong>'selectable'</strong>.<br />
But if the selectable plugin of jQuery UIs has already loading, you cannot access that method.

```
$(object).selectable();
```

#### Using with Options ####
```
$(object).jQselectable({
 style: 'simple',
 set: 'fadeIn',
 out: 'fadeOut',
 top: -10
});
```


---


## Options ##

| **key** | **value** |
|:--------|:----------|
| style   | 'selectable', 'simple' |
| set     | 'show', 'slideDown', 'fadeIn' |
| out     | 'hide', 'slideUp', 'fadeOut' |
| setDuration | 'slow', 'normal', 'fast', int(millisecond) |
| outDuration | 'slow', 'normal', 'fast', int(millisecond) |
| opacity | 1 (0~1)   |
| top     | 0 (px)    |
| left    | 0 (px)    |
| callback | function(){} |



### style ###
You may change styles either '**selectable**' or '**simple**' you like.<br />
Default style is the '**selectable**'.
### set (out) ###
Set selectable(s) showing(hiding) method.<br />
These method is as same as jQuery showing(hiding) methods.
<ul>
<li><b>show (hide)</b></li>
<li><b>slideDown (slideUp)</b></li>
<li><b>fadeIn (fadeOut)</b></li>
</ul>
### setDuration (outDuration) ###
Set selectable(s) duration of showing(hiding) animation.
<ul>
<li><b>slow</b></li>
<li><b>normal</b></li>
<li><b>fast</b></li>
<li><b>int(milliseconds)</b></li>
</ul>
### opacity ###
Set opacity of selectable(s)'s dropdown list.
### top (left) ###
This property is used by adjusting target selectable(s) position top(left).
### callback ###
You may also use callback function.<br />
'this' keyword is called as target select(s).

ex)
```
function(){
 alert($(this).val());
}
```

---


## API ##
If you need to rebuild the selectable, you would like to use api.

```
var instance = $('#sample').jQselectable();
~~~
instance.rebuild();
```

### Table ###
| **method** | **summary** |
|:-----------|:------------|
| rebuild    | Rebuilding selectable |


---


## With using AjaxZip2 ##

This is sample with using AjaxZip2 by rebuild.<br />
<a href='http://www.kawa.net/works/ajax/ajaxzip2/ajaxzip2.html'>AjaxZip2</a> is the library to complement prefecture with zipcode.

<a href='http://jqselectable.googlecode.com/svn/trunk/withzipsample.html'>View the live demo</a>

<a href='http://jqselectable.googlecode.com/files/jqselectable_withzip.1.3.2.zip'>Download sample files</a>

### Source code ###
```
var pref = $("#pref").jQselectable({
 set: "fadeIn",
 setDuration: "fast",
 opacity: .9
});

$("#zip").keyup(function(){
 // AjaxZip2
 AjaxZip2.zip2addr(this,"pref","addr");
}).blur(function(){
 // rebuilds target jQselectable element
 pref.rebuild();
});
```


---


### Author ###

nori @ <a href='http://5509.me/'>5509</a>


---


## Special Thanks ##
rewish @ <a href='http://rewish.org'>rewish.org</a>