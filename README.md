jquery.ngAnimate
================

enable css animaion with jquery automatically. inspired by angular animate

Like ngAnimate which module of angular.js we developed native jquery plugin named jquery.ngAnimate.
jquery.ngAnimate has approximately the same functionality with ngAnimate
***
<a href="https://github.com/pedersoft/bootstrap-animate-with-css">
There is bootstrap component set use <code>jquery.ngAnimate</code>
</a>


UnLike ngAnimate it don't automatically enable angularAnimation.css effects. Because, it is possible that, if it enabled automatically It will effect some of other plugins in your project and couse performance problems. For this reason, you should indicate that, if enable animation or not.
It doesn't have any new method or required new learning. Just sets of overwritten some common existing jquery methods.

<p class="help-block">
                        You can enable animations by using below method, with enable animation <span style="color:blue">true</span>:
                        <br><br>
                        <code><span class="pln">.show(true)</span></code>,
                        <code><span class="pln">.hide(true)</span></code>,
                        <code><span class="pln">.toggle(true)</span></code>
                        If you don't set true argument, animation would not be enabled.
                        <br><br>
                        <code><span class="pln">.addClass('yourClassName', true)</span></code>,
                        <code><span class="pln">.removeClass('yourClassName', true)</span></code>,
                        <code><span class="pln">.toggleClass('yourClassName', true)</span></code>
                        If you don't add true argument, animation would not be enabled.
                        <br><br>
                        <code><span class="pln">.appendTo(container, true)</span></code>
                        <code><span class="pln">.prependTo(container, true)</span></code>
                        <code><span class="pln">.insertBefore(element, true)</span></code>
                        <code><span class="pln">.insertAfter(element, true)</span></code>
                        If you don't add true argument, animation would not be enabled.

                        and <code><span class="pln">.detach(true)</span></code>
                        If you don't add true argument, animation would not be enabled.
                        <br>
                        Namely, when one of above method called,
                        <code>jquery.ngAnimate</code> look at the element has animation css class or not. If true, it enables the animation. that is all.
                    </p>

How animations enabled within angularAnimation.css
It is very simple. If an element is shown or hidden via jquery method, it gets proper classes for catching its animation css. Also the same logic is valid for all listed methods. For examples;
<h5><code>show</code> || <code>hide</code> || <code>toggle</code> Methods</h5>

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
<h5><code>addClass</code> || <code>removeClass</code> || <code>toggleClass</code> Methods</h5>

If element already had class, cannot have the same class. If had not the class any class cannot be removed.


<pre id="classtestElm" class="fast" style="background:#002240;color:#fff"><span style="color:#ff9d00">$</span>(<span style="color:#3ad900">'</span>.classtest<span style="color:#3ad900">'</span>).on(<span style="color:#3ad900">'</span>click<span style="color:#3ad900">'</span>, <span style="color:#ffee80">function</span> <span style="color:#e1efff">(</span>) {
                            <span style="color:#ffee80">var</span> <span style="color:#ff9d00">$</span><span style="color:#ff80e1">this</span> <span style="color:#ff9d00">=</span> <span style="color:#ff9d00">$</span>(<span style="color:#ff80e1">this</span>), type <span style="color:#ff9d00">=</span> <span style="color:#ff9d00">$</span><span style="color:#ff80e1">this</span>.attr(<span style="color:#3ad900">'</span>id<span style="color:#3ad900">'</span>)<span style="color:#e1efff">;</span>
                            <span style="color:#08f;font-style:italic"><span style="color:#e1efff">//</span>elem must have speed</span>
                            <span style="color:#ffee80">var</span> elm <span style="color:#ff9d00">=</span> <span style="color:#ff9d00">$</span>(<span style="color:#3ad900">'</span>#classtestElm<span style="color:#3ad900">'</span>)
                            <span style="color:#ff9d00">if</span> (type <span style="color:#ff9d00">==</span> <span style="color:#3ad900">'</span>add<span style="color:#3ad900">'</span>) {
        elm.addClass(<span style="color:#3ad900">'</span>flip-y<span style="color:#3ad900">',</span><span style="color:#08f;">true</span>)
    }
                            <span style="color:#ff9d00">else</span> <span style="color:#ff9d00">if</span> (type <span style="color:#ff9d00">==</span> <span style="color:#3ad900">'</span>remove<span style="color:#3ad900">'</span>) {
        elm.removeClass(<span style="color:#3ad900">'</span>flip-y<span style="color:#3ad900">',</span><span style="color:#08f;">true</span>)
    }
                            <span style="color:#ff9d00">else</span> <span style="color:#ff9d00">if</span> (type <span style="color:#ff9d00">==</span> <span style="color:#3ad900">'</span>toggle<span style="color:#3ad900">'</span>) {
       elm.toggleClass(<span style="color:#3ad900">'</span>flip-y<span style="color:#3ad900">',</span><span style="color:#08f;">true</span>)
    }
})
</pre>

<h3 class="with-border"><i class="font-icon br-globe"></i> Events</h3>

<span class="help-block">
                    There are two common events named <code>animationStart</code> and <code>animationEnd</code> are binded to the element. Events names don't have browser dependency, they are standart.
                </span>
 <span class="help-block">
                    <span class="label label-warning">Warning :</span> Be careful about by which method event was attached. If you use <code>.on()</code>, <code>.bind()</code> etc. maybe you face with recursion problems. We advise using <code>.one()</code>
                </span>
                <pre style="background:#002240;color:#fff"><span style="color:#80ffbb">$</span><span style="color:#e1efff">(</span><span style="color:#e1efff">'</span><span style="color:#5fe461"><span style="color:#e1efff">.</span>myimage</span><span style="color:#e1efff">'</span><span style="color:#e1efff">)</span><span style="color:#ffb054">.removeClass</span>(<span style="color:#3ad900">'</span>flip-x<span style="color:#3ad900">',</span><span style="color:#08f;">true</span>).one(<span style="color:#3ad900">'</span>animationEnd<span style="color:#3ad900">'</span>,
                <span style="color:#ffee80">function</span>(){
                <span style="color:#80ffbb">$</span><span style="color:#e1efff">(</span><span style="color:#e1efff">'</span><span style="color:#5fe461"><span style="color:#e1efff">.</span>myimage</span><span style="color:#e1efff">'</span><span style="color:#e1efff">)</span><span style="color:#ffb054">.addClass</span>(<span style="color:#3ad900">'</span>flip-y<span style="color:#3ad900">',</span><span style="color:#08f;">true</span>)
})
</pre>
