jquery.ngAnimate
================

enable css animaion with jquery automatically. inspired by angular animate

Like ngAnimate which module of angular.js we developed native jquery plugin named jquery.ngAnimate.
jquery.ngAnimate has approximately the same functionality with ngAnimate
***
UnLike ngAnimate it don't automatically enable angularAnimation.css effects. Because, it is possible that, if it enabled automatically It will effect some of other plugins in your project and couse performance problems. For this reason, you should indicate that, if enable animation or not.
It doesn't have any new method or required new learning. Just sets of overwritten some common existing jquery methods.
You can enable animations by using below method, with enable animation true: 

.show(true), .hide(true), .toggle(true) If you don't set true argument, animation would not be enabled. 

.addClass('yourClassName', true), .removeClass('yourClassName', true), .toggleClass('yourClassName', true) If you don't add true argument, animation would not be enabled. 

.appendTo(container, true) .prependTo(container, true) .insertBefore(element, true) .insertAfter(element, true) If you don't add true argument, animation would not be enabled. and .detach(true) If you don't add true argument, animation would not be enabled. 
Namely, when one of above method called, jquery.ngAnimate look at the element has animation css class or not. If true, it enables the animation. that is all.

How animations enabled within angularAnimation.css
It is very simple. If an element is shown or hidden via jquery method, it gets proper classes for catching its animation css. Also the same logic is valid for all listed methods. For examples;
show || hide || toggle Methods

If element was already hidden, cannot be hidden again, Also it was shown, cannot be shown again.

<pre id="toggletestElm" class="fast flip-x" style="background:#002240;color:#fff"><span style="color:#ff9d00">$</span>(<span style="color:#3ad900">'</span>.toggletest<span style="color:#3ad900">'</span>).on(<span style="color:#3ad900">'</span>click<span style="color:#3ad900">'</span>, <span style="color:#ffee80">function</span> <span style="color:#e1efff">(</span>) {
                            <span style="color:#ffee80">var</span> <span style="color:#ff9d00">$</span><span style="color:#ff80e1">this</span> <span style="color:#ff9d00">=</span> <span style="color:#ff9d00">$</span>(<span style="color:#ff80e1">this</span>), type <span style="color:#ff9d00">=</span> <span style="color:#ff9d00">$</span><span style="color:#ff80e1">this</span>.attr(<span style="color:#3ad900">'</span>id<span style="color:#3ad900">'</span>)<span style="color:#e1efff">;</span>
                            <span style="color:#08f;font-style:italic"><span style="color:#e1efff">//</span>elm must have speed and animation class</span>
                            <span style="color:#ffee80">var</span> elm <span style="color:#ff9d00">=</span> <span style="color:#ff9d00">$</span>(<span style="color:#3ad900">'</span>#toggletestElm<span style="color:#3ad900">'</span>)
                            <span style="color:#ff9d00">if</span> (type <span style="color:#ff9d00">==</span> <span style="color:#3ad900">'</span>hide<span style="color:#3ad900">'</span>) {
        elm.hide(<span style="color:#08f;">true</span>)
    }
                            <span style="color:#ff9d00">else</span> <span style="color:#ff9d00">if</span> (type <span style="color:#ff9d00">==</span> <span style="color:#3ad900">'</span>show<span style="color:#3ad900">'</span>) {
        elm.show(<span style="color:#08f;">true</span>)
    }
                            <span style="color:#ff9d00">else</span> <span style="color:#ff9d00">if</span> (type <span style="color:#ff9d00">==</span> <span style="color:#3ad900">'</span>toggle<span style="color:#3ad900">'</span>) {
        elm.toggle(<span style="color:#08f;">true</span>)
    }       
})
</pre>
