# *PLUGIN* - Mouse move Object
> Movendo um elemento com Javascript

# Objeto HTML
```html
  <div>
    <img class="dragme" src="cubo.png" width="200" height="200">
  </div>
  <div class="dragme">
    <b>mova-me!!! please!!!</b><br />repare que eu estou por cima!!!!
  </div>
```

# Objeto Javascript
```javascript
var ie = document.all
var nn6 = document.getElementById&&!document.all
var isdrag = false
var x,y
var dobj
function movemouse(e){
    if (isdrag){
        dobj.style.left = nn6 ? tx + e.clientX - x : tx + event.clientX - x
        dobj.style.top  = nn6 ? ty + e.clientY - y : ty + event.clientY - y
        return false;
    }
}
function selectmouse(e){
    var fobj       = nn6 ? e.target : event.srcElement
    var topelement = nn6 ? "HTML" : "BODY"
    while (fobj.tagName != topelement && fobj.className != "dragme"){
        fobj = nn6 ? fobj.parentNode : fobj.parentElement
    }

    if (fobj.className=="dragme"){
        isdrag = true
        dobj = fobj
        tx = parseInt(dobj.style.left+0)
        ty = parseInt(dobj.style.top+0)
        x = nn6 ? e.clientX : event.clientX
        y = nn6 ? e.clientY : event.clientY
        document.onmousemove = movemouse
        return false
    }
}
document.onmousedown = selectmouse
document.onmouseup = new Function("isdrag=false")
```
# Objeto CSS
```css
.dragme{position: relative;}
```

# demo
[DEMO](https://code.sololearn.com/W55sL5aweC1s)

# LOG

**02/10/2021**
> add index.html<br>
> add cubo.png



SCRIPT TUTORIAIS + LUMATECH APPS E GAMES = LUIZ BRUNO R. T.
