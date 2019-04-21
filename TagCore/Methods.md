<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Methods</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__left">
    <div class="stackedit__toc">
      
<ul>
<li><a href="#tag-core-methods">Tag Core Methods</a>
<ul>
<li><a href="#hide">hide</a></li>
<li><a href="#haveandgetselector">haveAndGetSelector</a></li>
<li><a href="#getselector">getSelector</a></li>
<li><a href="#haveandgetselectorid">haveAndGetSelectorID</a></li>
<li><a href="#hasparent">hasParent</a></li>
<li><a href="#name">name</a></li>
<li><a href="#getobjname">getObjName</a></li>
<li><a href="#getelement">getElement</a></li>
<li><a href="#iselement">isElement</a></li>
</ul>
</li>
</ul>

    </div>
  </div>
  <div class="stackedit__right">
    <div class="stackedit__html">
      <h1 id="tag-core-methods">Tag Core Methods</h1>
<h2 id="hide">hide</h2>
<p>Add to tag <code>style="display: none;"</code>.</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @param bool $eq You can pass a boolean value as a switch when rendering.
 * @return $this  
 */</span>
<span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">hide</span><span class="token punctuation">(</span><span class="token variable">$eq</span> <span class="token operator">=</span> <span class="token boolean">true</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="haveandgetselector">haveAndGetSelector</h2>
<p>Get the identifier attribute if there is, if not, create a unique attribute and return the <code>JS Query</code> selector.</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @return string  
 * @throws \Exception  
 */</span>
<span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">haveAndGetSelector</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="getselector">getSelector</h2>
<p>Alias <code>haveAndGetSelectorID</code></p>
<h2 id="haveandgetselectorid">haveAndGetSelectorID</h2>
<p>Get the value of the identifier attribute if there is one, if not create a unique one and return the <code>JS Query</code> selector.</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @return string  
 * @throws \Exception  
 */</span>
<span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">haveAndGetSelectorID</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="hasparent">hasParent</h2>
<p>Check if there is a parent object.</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @return bool  
 */</span>
 <span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">hasParent</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="name">name</h2>
<p>Set the internal name for easy access through the <code>_s</code> helper.</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @param string $name  
 * @return $this  
 */</span>
<span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">name</span><span class="token punctuation">(</span>string <span class="token variable">$name</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
<span class="token function">_s</span><span class="token punctuation">(</span><span class="token variable">$name</span><span class="token punctuation">)</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">text</span><span class="token punctuation">(</span><span class="token string">"Hello"</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="getobjname">getObjName</h2>
<p>Name getter</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @return string  
 */</span>
 <span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">getObjName</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="getelement">getElement</h2>
<p>Element getter</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @return string  
 */</span>
 <span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">getElement</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="iselement">isElement</h2>
<p>Checks if an item has an element.</p>
<pre class=" language-php"><code class="prism  language-php"><span class="token comment">/**  
 * @return bool  
 */</span>
 <span class="token variable">$tag</span><span class="token operator">-</span><span class="token operator">&gt;</span><span class="token function">isElement</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
</code></pre>

    </div>
  </div>
</body>

</html>
