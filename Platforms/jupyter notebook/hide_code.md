TOC

1. [nbextension-Hide input](#nbextension-hide-input)
2. [nbviewer](#nbviewer)

## nbextension-hide input
1. `hide input` Enable check

2. 노트북 화면에 아래 그림처럼 툴바 생김
![](img/2017-08-31-11-32-23.png)
- 실행 화면
![](img/hidecell.gif)

> HTML로 저장하면 코드가 보임 

## nbviewer
[참고사이트](http://chris-said.io/2016/02/13/how-to-make-polished-jupyter-presentations-with-optional-code-visibility/)

1. Cell input 설정을 Raw NBConvert로 바꾸고

2. 사이트에 나와있는 코드 앞과 뒤에 입력하고 github에 저장

3. github주소를 nbviewer에 붙여넣기
example)http://nbviewer.jupyter.org/github/jk-jang/TIL/blob/master/Platforms/jupyter%20notebook/notebook_polished.ipynb

- HTML로 저장한 화면
![](img/08-31-hidecell.gif)

- [nbviewr.jupyter.org이용한 화면](http://nbviewer.jupyter.org/github/jk-jang/TIL/blob/master/Platforms/jupyter%20notebook/notebook_polished.ipynb)

- CODE
```html
<script>
  jQuery(document).ready(function($) {  
  
  $(window).on('load', function(){
    $('#preloader').fadeOut('slow',function(){$(this).remove();});
  });
  
  });
</script>

<style type="text/css">
  div#preloader { position: fixed; 
      left: 0; 
      top: 0; 
      z-index: 999; 
      width: 100%; 
      height: 100%; 
      overflow: visible; 
      background: #fff url('http://preloaders.net/preloaders/720/Moving%20line.gif') no-repeat center center; 
  }

</style>

<div id="preloader">

</div>

<script>
  function code_toggle() {
    if (code_shown){
      $('div.input').hide('500');
      $('#toggleButton').val('Show Code')
    } else {
      $('div.input').show('500');
      $('#toggleButton').val('Hide Code')
    }
    code_shown = !code_shown
  } 
  
  $( document ).ready(function(){
    code_shown=false; 
    $('div.input').hide()
  });
</script>
<form action="javascript:code_toggle()"><input type="submit" id="toggleButton" value="Show Code"></form>

```
<----------------표시할 코드(start)--------------->
```python
import plotly
import plotly.graph_objs as go
import string
import numpy as np
plotly.offline.init_notebook_mode() 

x = np.random.randn(26)
y = x + np.random.randn(26)
labels = ['Observation ' + c for c in list(string.ascii_uppercase)]

trace = go.Scatter(
    x=x,
    y=y,
    mode='markers',
    marker=dict(size='13'),
    text=labels,
    hoverinfo='x+text',
    name="Sample Data",
)

fig = dict(data=[trace], layout={})
fig['layout']['xaxis'] = dict(title='Variable X')
fig['layout']['yaxis'] = dict(title='Variable Y')
 
plotly.offline.iplot(fig, show_link=False)
```
<----------------표시할 코드(end)--------------->
```html
<script>
  $(document).ready(function(){
    $('div.prompt').hide();
    $('div.back-to-top').hide();
    $('nav#menubar').hide();
    $('.breadcrumb').hide();
    $('.hidden-print').hide();
  });
</script>

<footer id="attribution" style="float:right; color:#999; background:#fff;">
Created with Jupyter, delivered by Fastly, rendered by Rackspace.
</footer>
```