<h1>
html-vdom <a href="https://npmjs.org/package/html-vdom"><img src="https://img.shields.io/badge/npm-v2.0.2-F00.svg?colorA=000"/></a> <a href="src"><img src="https://img.shields.io/badge/loc-408-FFF.svg?colorA=000"/></a> <a href="https://cdn.jsdelivr.net/npm/html-vdom@2.0.2/dist/html-vdom.min.js"><img src="https://img.shields.io/badge/brotli-1.8K-333.svg?colorA=000"/></a> <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-F0B.svg?colorA=000"/></a>
</h1>

<p></p>

JSX virtual DOM using standard HTML

<h4>
<table><tr><td title="Triple click to select and copy paste">
<code>npm i html-vdom </code>
</td><td title="Triple click to select and copy paste">
<code>pnpm add html-vdom </code>
</td><td title="Triple click to select and copy paste">
<code>yarn add html-vdom</code>
</td></tr></table>
</h4>

## Examples

<details id="example$from-element" title="from-element" open><summary><span><a href="#example$from-element">#</a></span>  <code><strong>from-element</strong></code></summary>  <ul>    <details id="source$from-element" title="from-element source code" open><summary><span><a href="#source$from-element">#</a></span>  <code><strong>view source</strong></code></summary>  <a href="example/from-element.tsx">example/from-element.tsx</a>  <p>

```tsx
/** @jsxImportSource html-vdom */
import { render } from 'html-vdom'
import { fromElement } from 'html-vdom/from-element'

class FooElement extends HTMLElement {
  root = this.attachShadow({ mode: 'open' })
  set who(name: string) {
    this.root.innerHTML = 'Hello, ' + name
  }
}

const Foo = fromElement(FooElement)
render(<Foo who="world" />, document.body)
```

</p>
</details></ul></details><details id="example$simple" title="simple" open><summary><span><a href="#example$simple">#</a></span>  <code><strong>simple</strong></code></summary>  <ul>    <details id="source$simple" title="simple source code" open><summary><span><a href="#source$simple">#</a></span>  <code><strong>view source</strong></code></summary>  <a href="example/simple.tsx">example/simple.tsx</a>  <p>

```tsx
/** @jsxImportSource html-vdom */
import { $, render } from 'html-vdom'

const App: $<{ who: string }> = ({ who }) => <h1>Hello, {who}!</h1>
render(<App who="world" />, document.body)
```

</p>
</details></ul></details><details id="example$with-hook" title="with-hook" open><summary><span><a href="#example$with-hook">#</a></span>  <code><strong>with-hook</strong></code></summary>  <ul>    <details id="source$with-hook" title="with-hook source code" ><summary><span><a href="#source$with-hook">#</a></span>  <code><strong>view source</strong></code></summary>  <a href="example/with-hook.tsx">example/with-hook.tsx</a>  <p>

```tsx
/** @jsxImportSource html-vdom */
import { $, Hook, hook, render } from 'html-vdom'

let greeting = 'Hello'
let update: Hook

const App: $<{ who: string }> = ({ who }) => {
  update = hook
  return <h1>{greeting}, {who}!</h1>
}

render(<App who="world" />, document.body)

setTimeout(() => {
  greeting = 'Hiya'
  update()
}, 500)
```

</p>
</details></ul></details>

## API

<p>  <details id="Chunk$52" title="Class" ><summary><span><a href="#Chunk$52">#</a></span>  <code><strong>Chunk</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L113">src/jsx-runtime.ts#L113</a>  <ul>        <p>  <details id="constructor$53" title="Constructor" ><summary><span><a href="#constructor$53">#</a></span>  <code><strong>constructor</strong></code><em>(arrayLength)</em>    </summary>    <ul>    <p>  <details id="new Chunk$54" title="ConstructorSignature" ><summary><span><a href="#new Chunk$54">#</a></span>  <code><strong>new Chunk</strong></code><em>()</em>    </summary>    <ul><p><a href="#Chunk$52">Chunk</a></p>      <p>  <details id="arrayLength$55" title="Parameter" ><summary><span><a href="#arrayLength$55">#</a></span>  <code><strong>arrayLength</strong></code>    </summary>    <ul><p>number</p>        </ul></details></p>  </ul></details></p>    </ul></details><details id="dom$57" title="Property" ><summary><span><a href="#dom$57">#</a></span>  <code><strong>dom</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>[]</code></span>  </summary>  <a href="src/jsx-runtime.ts#L115">src/jsx-runtime.ts#L115</a>  <ul><p><span>El</span>  []</p>        </ul></details><details id="firstChild$56" title="Property" ><summary><span><a href="#firstChild$56">#</a></span>  <code><strong>firstChild</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L114">src/jsx-runtime.ts#L114</a>  <ul><p>any</p>        </ul></details><details id="last$58" title="Accessor" ><summary><span><a href="#last$58">#</a></span>  <code><strong>last</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L116">src/jsx-runtime.ts#L116</a>  <ul>        </ul></details><details id="nextSibling$60" title="Accessor" ><summary><span><a href="#nextSibling$60">#</a></span>  <code><strong>nextSibling</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L119">src/jsx-runtime.ts#L119</a>  <ul>        </ul></details><details id="after$65" title="Method" ><summary><span><a href="#after$65">#</a></span>  <code><strong>after</strong></code><em>(x)</em>    </summary>  <a href="src/jsx-runtime.ts#L128">src/jsx-runtime.ts#L128</a>  <ul>    <p>    <details id="x$67" title="Parameter" ><summary><span><a href="#x$67">#</a></span>  <code><strong>x</strong></code>    </summary>    <ul><p><span>Node</span></p>        </ul></details>  <p><strong>after</strong><em>(x)</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details><details id="appendChild$62" title="Method" ><summary><span><a href="#appendChild$62">#</a></span>  <code><strong>appendChild</strong></code><em>(x)</em>    </summary>  <a href="src/jsx-runtime.ts#L125">src/jsx-runtime.ts#L125</a>  <ul>    <p>    <details id="x$64" title="Parameter" ><summary><span><a href="#x$64">#</a></span>  <code><strong>x</strong></code>    </summary>    <ul><p>any</p>        </ul></details>  <p><strong>appendChild</strong><em>(x)</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details><details id="remove$70" title="Method" ><summary><span><a href="#remove$70">#</a></span>  <code><strong>remove</strong></code><em>()</em>    </summary>  <a href="src/jsx-runtime.ts#L134">src/jsx-runtime.ts#L134</a>  <ul>    <p>      <p><strong>remove</strong><em>()</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details><details id="removeChild$72" title="Method" ><summary><span><a href="#removeChild$72">#</a></span>  <code><strong>removeChild</strong></code><em>(x)</em>    </summary>  <a href="src/jsx-runtime.ts#L138">src/jsx-runtime.ts#L138</a>  <ul>    <p>    <details id="x$74" title="Parameter" ><summary><span><a href="#x$74">#</a></span>  <code><strong>x</strong></code>    </summary>    <ul><p>any</p>        </ul></details>  <p><strong>removeChild</strong><em>(x)</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details><details id="save$68" title="Method" ><summary><span><a href="#save$68">#</a></span>  <code><strong>save</strong></code><em>()</em>    </summary>  <a href="src/jsx-runtime.ts#L131">src/jsx-runtime.ts#L131</a>  <ul>    <p>      <p><strong>save</strong><em>()</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details></p></ul></details><details id="DOMAttributes$104" title="Interface" ><summary><span><a href="#DOMAttributes$104">#</a></span>  <code><strong>DOMAttributes</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L8">src/jsx-runtime.ts#L8</a>  <ul>        <p>  <details id="innerHTML$108" title="Property" ><summary><span><a href="#innerHTML$108">#</a></span>  <code><strong>innerHTML</strong></code>     &ndash; Sets the <code>innerHTML</code> of an element to the <strong>exact</strong> string <strong>without</strong> escaping.</summary>  <a href="src/jsx-runtime.ts#L53">src/jsx-runtime.ts#L53</a>  <ul><p>string</p>        </ul></details></p></ul></details><details id="VRef$23" title="Interface" ><summary><span><a href="#VRef$23">#</a></span>  <code><strong>VRef</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L64">src/jsx-runtime.ts#L64</a>  <ul>        <p>  <details id="current$24" title="Property" ><summary><span><a href="#current$24">#</a></span>  <code><strong>current</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L65">src/jsx-runtime.ts#L65</a>  <ul><p><a href="#T$25">T</a></p>        </ul></details></p></ul></details><details id="$$16" title="TypeAlias" ><summary><span><a href="#$$16">#</a></span>  <code><strong>$</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L62">src/jsx-runtime.ts#L62</a>  <ul><p><details id="__type$17" title="Function" ><summary><span><a href="#__type$17">#</a></span>  <em>(props)</em>    </summary>    <ul>    <p>    <details id="props$19" title="Parameter" ><summary><span><a href="#props$19">#</a></span>  <code><strong>props</strong></code>    </summary>    <ul><p><a href="#T$22">T</a> &amp; {<p>  <details id="children$21" title="Property" ><summary><span><a href="#children$21">#</a></span>  <code><strong>children</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L62">src/jsx-runtime.ts#L62</a>  <ul><p>any</p>        </ul></details></p>}</p>        </ul></details>  <p><strong></strong><em>(props)</em>  &nbsp;=&gt;  <ul><span>JSX.Element</span></ul></p></p>    </ul></details></p>        </ul></details><details id="Doc$26" title="TypeAlias" ><summary><span><a href="#Doc$26">#</a></span>  <code><strong>Doc</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L69">src/jsx-runtime.ts#L69</a>  <ul><p><details id="__type$27" title="Function" ><summary><span><a href="#__type$27">#</a></span>  <em>(tag, opts)</em>    </summary>    <ul>    <p>    <details id="tag$29" title="Parameter" ><summary><span><a href="#tag$29">#</a></span>  <code><strong>tag</strong></code>    </summary>    <ul><p>string</p>        </ul></details><details id="opts$30" title="Parameter" ><summary><span><a href="#opts$30">#</a></span>  <code><strong>opts</strong></code>    </summary>    <ul><p><span>ElementCreationOptions</span></p>        </ul></details>  <p><strong></strong><em>(tag, opts)</em>  &nbsp;=&gt;  <ul><span>Element</span></ul></p></p>    </ul></details></p>        </ul></details><details id="Hook$35" title="TypeAlias" ><summary><span><a href="#Hook$35">#</a></span>  <code><strong>Hook</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L85">src/jsx-runtime.ts#L85</a>  <ul><p><span>Fn</span> &amp; {<p>  <details id="fn$37" title="Property" ><summary><span><a href="#fn$37">#</a></span>  <code><strong>fn</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L85">src/jsx-runtime.ts#L85</a>  <ul><p><span>Fn</span></p>        </ul></details><details id="onremove$38" title="Property" ><summary><span><a href="#onremove$38">#</a></span>  <code><strong>onremove</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L85">src/jsx-runtime.ts#L85</a>  <ul><p><span>Fn</span></p>        </ul></details></p>} &amp; <span>Record</span>&lt;string, any&gt;</p>        </ul></details><details id="Props$39" title="TypeAlias" ><summary><span><a href="#Props$39">#</a></span>  <code><strong>Props</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L86">src/jsx-runtime.ts#L86</a>  <ul><p><span>Record</span>&lt;string, any&gt;</p>        </ul></details><details id="VFn$31" title="TypeAlias" ><summary><span><a href="#VFn$31">#</a></span>  <code><strong>VFn</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L70">src/jsx-runtime.ts#L70</a>  <ul><p><details id="__type$32" title="Function" ><summary><span><a href="#__type$32">#</a></span>  <em>(props)</em>    </summary>    <ul>    <p>    <details id="props$34" title="Parameter" ><summary><span><a href="#props$34">#</a></span>  <code><strong>props</strong></code>    </summary>    <ul><p>any</p>        </ul></details>  <p><strong></strong><em>(props)</em>  &nbsp;=&gt;  <ul><span>VKid</span></ul></p></p>    </ul></details></p>        </ul></details><details id="VNode$75" title="TypeAlias" ><summary><span><a href="#VNode$75">#</a></span>  <code><strong>VNode</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L87">src/jsx-runtime.ts#L87</a>  <ul><p>{<p>  <details id="hook$80" title="Property" ><summary><span><a href="#hook$80">#</a></span>  <code><strong>hook</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L91">src/jsx-runtime.ts#L91</a>  <ul><p><a href="#Hook$35">Hook</a></p>        </ul></details><details id="keep$81" title="Property" ><summary><span><a href="#keep$81">#</a></span>  <code><strong>keep</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L92">src/jsx-runtime.ts#L92</a>  <ul><p>boolean</p>        </ul></details><details id="key$79" title="Property" ><summary><span><a href="#key$79">#</a></span>  <code><strong>key</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L90">src/jsx-runtime.ts#L90</a>  <ul><p>string</p>        </ul></details><details id="kind$77" title="Property" ><summary><span><a href="#kind$77">#</a></span>  <code><strong>kind</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L88">src/jsx-runtime.ts#L88</a>  <ul><p><a href="#T$82">T</a></p>        </ul></details><details id="props$78" title="Property" ><summary><span><a href="#props$78">#</a></span>  <code><strong>props</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L89">src/jsx-runtime.ts#L89</a>  <ul><p><a href="#Props$39">Props</a></p>        </ul></details></p>}</p>        </ul></details><details id="Fragment$40" title="Variable" ><summary><span><a href="#Fragment$40">#</a></span>  <code><strong>Fragment</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>...</code></span>  </summary>  <a href="src/jsx-runtime.ts#L96">src/jsx-runtime.ts#L96</a>  <ul><p>typeof   <a href="#Fragment$40">Fragment</a></p>        </ul></details><details id="hook$51" title="Variable" ><summary><span><a href="#hook$51">#</a></span>  <code><strong>hook</strong></code>    </summary>  <a href="src/jsx-runtime.ts#L103">src/jsx-runtime.ts#L103</a>  <ul><p><a href="#Hook$35">Hook</a></p>        </ul></details><details id="createProps$1" title="Function" ><summary><span><a href="#createProps$1">#</a></span>  <code><strong>createProps</strong></code><em>(doc, el, type, props, attrs, cacheRef)</em>    </summary>  <a href="src/props.ts#L131">src/props.ts#L131</a>  <ul>    <p>    <details id="doc$3" title="Parameter" ><summary><span><a href="#doc$3">#</a></span>  <code><strong>doc</strong></code>    </summary>    <ul><p><a href="#Doc$26">Doc</a></p>        </ul></details><details id="el$4" title="Parameter" ><summary><span><a href="#el$4">#</a></span>  <code><strong>el</strong></code>    </summary>    <ul><p><span>Element</span></p>        </ul></details><details id="type$5" title="Parameter" ><summary><span><a href="#type$5">#</a></span>  <code><strong>type</strong></code>    </summary>    <ul><p>string</p>        </ul></details><details id="props$6" title="Parameter" ><summary><span><a href="#props$6">#</a></span>  <code><strong>props</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>{}</code></span>  </summary>    <ul><p><a href="#Props$39">Props</a></p>        </ul></details><details id="attrs$7" title="Parameter" ><summary><span><a href="#attrs$7">#</a></span>  <code><strong>attrs</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>{}</code></span>  </summary>    <ul><p><span>Record</span>&lt;string, <span>Attr</span>&gt;</p>        </ul></details><details id="cacheRef$8" title="Parameter" ><summary><span><a href="#cacheRef$8">#</a></span>  <code><strong>cacheRef</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>el</code></span>  </summary>    <ul><p>object</p>        </ul></details>  <p><strong>createProps</strong><em>(doc, el, type, props, attrs, cacheRef)</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details><details id="html$83" title="Function" ><summary><span><a href="#html$83">#</a></span>  <code><strong>html</strong></code><em>(tagName, options)</em>    </summary>  <a href="src/jsx-runtime.ts#L149">src/jsx-runtime.ts#L149</a>  <ul>    <p>    <details id="tagName$86" title="Parameter" ><summary><span><a href="#tagName$86">#</a></span>  <code><strong>tagName</strong></code>    </summary>    <ul><p><a href="#K$85">K</a></p>        </ul></details><details id="options$87" title="Parameter" ><summary><span><a href="#options$87">#</a></span>  <code><strong>options</strong></code>    </summary>    <ul><p><span>ElementCreationOptions</span></p>        </ul></details>  <p><strong>html</strong>&lt;<span>K</span>&gt;<em>(tagName, options)</em>  &nbsp;=&gt;  <ul><span>HTMLElementTagNameMap</span>  [<a href="#K$85">K</a>]</ul></p>  <details id="tagName$90" title="Parameter" ><summary><span><a href="#tagName$90">#</a></span>  <code><strong>tagName</strong></code>    </summary>    <ul><p><a href="#K$89">K</a></p>        </ul></details><details id="options$91" title="Parameter" ><summary><span><a href="#options$91">#</a></span>  <code><strong>options</strong></code>    </summary>    <ul><p><span>ElementCreationOptions</span></p>        </ul></details>  <p><strong>html</strong>&lt;<span>K</span>&gt;<em>(tagName, options)</em>  &nbsp;=&gt;  <ul><span>HTMLElementDeprecatedTagNameMap</span>  [<a href="#K$89">K</a>]</ul></p>  <details id="tagName$93" title="Parameter" ><summary><span><a href="#tagName$93">#</a></span>  <code><strong>tagName</strong></code>    </summary>    <ul><p>string</p>        </ul></details><details id="options$94" title="Parameter" ><summary><span><a href="#options$94">#</a></span>  <code><strong>options</strong></code>    </summary>    <ul><p><span>ElementCreationOptions</span></p>        </ul></details>  <p><strong>html</strong><em>(tagName, options)</em>  &nbsp;=&gt;  <ul><span>HTMLElement</span></ul></p></p>    </ul></details><details id="jsx$41" title="Function" ><summary><span><a href="#jsx$41">#</a></span>  <code><strong>jsx</strong></code><em>(kind, props, key)</em>    </summary>  <a href="src/jsx-runtime.ts#L97">src/jsx-runtime.ts#L97</a>  <ul>    <p>    <details id="kind$43" title="Parameter" ><summary><span><a href="#kind$43">#</a></span>  <code><strong>kind</strong></code>    </summary>    <ul><p>any</p>        </ul></details><details id="props$44" title="Parameter" ><summary><span><a href="#props$44">#</a></span>  <code><strong>props</strong></code>    </summary>    <ul><p>any</p>        </ul></details><details id="key$45" title="Parameter" ><summary><span><a href="#key$45">#</a></span>  <code><strong>key</strong></code>    </summary>    <ul><p>any</p>        </ul></details>  <p><strong>jsx</strong><em>(kind, props, key)</em>  &nbsp;=&gt;  <ul>any</ul></p></p>    </ul></details><details id="jsxs$46" title="Function" ><summary><span><a href="#jsxs$46">#</a></span>  <code><strong>jsxs</strong></code><em>(kind, props, key)</em>    </summary>  <a href="src/jsx-runtime.ts#L101">src/jsx-runtime.ts#L101</a>  <ul>    <p>    <details id="kind$48" title="Parameter" ><summary><span><a href="#kind$48">#</a></span>  <code><strong>kind</strong></code>    </summary>    <ul><p>any</p>        </ul></details><details id="props$49" title="Parameter" ><summary><span><a href="#props$49">#</a></span>  <code><strong>props</strong></code>    </summary>    <ul><p>any</p>        </ul></details><details id="key$50" title="Parameter" ><summary><span><a href="#key$50">#</a></span>  <code><strong>key</strong></code>    </summary>    <ul><p>any</p>        </ul></details>  <p><strong>jsxs</strong><em>(kind, props, key)</em>  &nbsp;=&gt;  <ul>any</ul></p></p>    </ul></details><details id="render$98" title="Function" ><summary><span><a href="#render$98">#</a></span>  <code><strong>render</strong></code><em>(n, el, doc, withNull)</em>    </summary>  <a href="src/jsx-runtime.ts#L162">src/jsx-runtime.ts#L162</a>  <ul>    <p>    <details id="n$100" title="Parameter" ><summary><span><a href="#n$100">#</a></span>  <code><strong>n</strong></code>    </summary>    <ul><p><span>VKid</span></p>        </ul></details><details id="el$101" title="Parameter" ><summary><span><a href="#el$101">#</a></span>  <code><strong>el</strong></code>    </summary>    <ul><p><span>TargetEl</span></p>        </ul></details><details id="doc$102" title="Parameter" ><summary><span><a href="#doc$102">#</a></span>  <code><strong>doc</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>html</code></span>  </summary>    <ul><p><a href="#Doc$26">Doc</a></p>        </ul></details><details id="withNull$103" title="Parameter" ><summary><span><a href="#withNull$103">#</a></span>  <code><strong>withNull</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>false</code></span>  </summary>    <ul><p>boolean</p>        </ul></details>  <p><strong>render</strong><em>(n, el, doc, withNull)</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details><details id="svg$95" title="Function" ><summary><span><a href="#svg$95">#</a></span>  <code><strong>svg</strong></code><em>(args)</em>    </summary>  <a href="src/jsx-runtime.ts#L150">src/jsx-runtime.ts#L150</a>  <ul>    <p>    <details id="args$97" title="Parameter" ><summary><span><a href="#args$97">#</a></span>  <code><strong>args</strong></code>    </summary>    <ul><p>tuple</p>        </ul></details>  <p><strong>svg</strong><em>(args)</em>  &nbsp;=&gt;  <ul><span>Element</span></ul></p></p>    </ul></details><details id="updateProps$9" title="Function" ><summary><span><a href="#updateProps$9">#</a></span>  <code><strong>updateProps</strong></code><em>(doc, el, type, next, cacheRef)</em>    </summary>  <a href="src/props.ts#L143">src/props.ts#L143</a>  <ul>    <p>    <details id="doc$11" title="Parameter" ><summary><span><a href="#doc$11">#</a></span>  <code><strong>doc</strong></code>    </summary>    <ul><p><a href="#Doc$26">Doc</a></p>        </ul></details><details id="el$12" title="Parameter" ><summary><span><a href="#el$12">#</a></span>  <code><strong>el</strong></code>    </summary>    <ul><p><span>Element</span></p>        </ul></details><details id="type$13" title="Parameter" ><summary><span><a href="#type$13">#</a></span>  <code><strong>type</strong></code>    </summary>    <ul><p>string</p>        </ul></details><details id="next$14" title="Parameter" ><summary><span><a href="#next$14">#</a></span>  <code><strong>next</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>{}</code></span>  </summary>    <ul><p><a href="#Props$39">Props</a></p>        </ul></details><details id="cacheRef$15" title="Parameter" ><summary><span><a href="#cacheRef$15">#</a></span>  <code><strong>cacheRef</strong></code>  <span><span>&nbsp;=&nbsp;</span>  <code>el</code></span>  </summary>    <ul><p>object</p>        </ul></details>  <p><strong>updateProps</strong><em>(doc, el, type, next, cacheRef)</em>  &nbsp;=&gt;  <ul>void</ul></p></p>    </ul></details></p>

## Credits

- [html-jsx](https://npmjs.org/package/html-jsx) by [stagas](https://github.com/stagas) &ndash; Extensible jsx type definitions for standard html interfaces.

## Contributing

[Fork](https://github.com/stagas/html-vdom/fork) or [edit](https://github.dev/stagas/html-vdom) and submit a PR.

All contributions are welcome!

## License

<a href="LICENSE">MIT</a> &copy; 2022 [stagas](https://github.com/stagas)
