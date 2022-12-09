
<dl>
<dt id="user-content-mergeconfig">
  <h4>
    <code>interface</code>
    <a href="#user-content-mergeconfig">MergeConfig</a></h4>
</dt>

<dd><p>Configuration options to <code>MergeView</code> that can be provided both
initially and to <a href="#user-content-mergeview.reconfigure"><code>reconfigure</code></a>.</p>
<dl><dt id="user-content-mergeconfig.orientation">
  <code><strong><a href="#user-content-mergeconfig.orientation">orientation</a></strong>&#8288;?: &quot;a-b&quot; | &quot;b-a&quot;</code></dt>

<dd><p>Controls whether editor A or editor B is shown first. Defaults
to <code>&quot;a-b&quot;</code>.</p>
</dd><dt id="user-content-mergeconfig.revertcontrols">
  <code><strong><a href="#user-content-mergeconfig.revertcontrols">revertControls</a></strong>&#8288;?: &quot;a-to-b&quot; | &quot;b-to-a&quot;</code></dt>

<dd><p>Controls whether revert controls are shown between changed
chunks.</p>
</dd><dt id="user-content-mergeconfig.renderrevertcontrol">
  <code><strong><a href="#user-content-mergeconfig.renderrevertcontrol">renderRevertControl</a></strong>&#8288;?: fn() → <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement">HTMLElement</a></code></dt>

<dd><p>When given, this function is called to render the button to
revert a chunk.</p>
</dd><dt id="user-content-mergeconfig.highlightchanges">
  <code><strong><a href="#user-content-mergeconfig.highlightchanges">highlightChanges</a></strong>&#8288;?: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean">boolean</a></code></dt>

<dd><p>By default, the merge view will mark inserted and deleted text
in changed chunks. Set this to false to turn that off.</p>
</dd><dt id="user-content-mergeconfig.gutter">
  <code><strong><a href="#user-content-mergeconfig.gutter">gutter</a></strong>&#8288;?: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean">boolean</a></code></dt>

<dd><p>Controls whether a gutter marker is shown next to changed lines.</p>
</dd><dt id="user-content-mergeconfig.collapseunchanged">
  <code><strong><a href="#user-content-mergeconfig.collapseunchanged">collapseUnchanged</a></strong>&#8288;?: {margin&#8288;?: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, minSize&#8288;?: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>}</code></dt>

<dd><p>When given, long stretches of unchanged text are collapsed.
<code>margin</code> gives the number of lines to leave visible after/before
a change (default is 3), and <code>minSize</code> gives the minimum amount
of collapsible lines that need to be present (defaults to 4).</p>
</dd></dl>

</dd>
<dt id="user-content-directmergeconfig">
  <h4>
    <code>interface</code>
    <a href="#user-content-directmergeconfig">DirectMergeConfig</a> <code>extends <a href="#user-content-mergeconfig">MergeConfig</a></code></h4>
</dt>

<dd><p>Configuration options given to the <a href="#user-content-mergeview"><code>MergeView</code></a>
constructor.</p>
<dl><dt id="user-content-directmergeconfig.a">
  <code><strong><a href="#user-content-directmergeconfig.a">a</a></strong>: <a href="https://codemirror.net/docs/ref#state.EditorStateConfig">EditorStateConfig</a></code></dt>

<dd><p>Configuration for the first editor (the left one in a
left-to-right context).</p>
</dd><dt id="user-content-directmergeconfig.b">
  <code><strong><a href="#user-content-directmergeconfig.b">b</a></strong>: <a href="https://codemirror.net/docs/ref#state.EditorStateConfig">EditorStateConfig</a></code></dt>

<dd><p>Configuration for the second editor.</p>
</dd><dt id="user-content-directmergeconfig.parent">
  <code><strong><a href="#user-content-directmergeconfig.parent">parent</a></strong>&#8288;?: <a href="https://developer.mozilla.org/en/docs/DOM/Element">Element</a> | <a href="https://developer.mozilla.org/en/docs/DOM/document.createDocumentFragment">DocumentFragment</a></code></dt>

<dd><p>Parent element to append the view to.</p>
</dd><dt id="user-content-directmergeconfig.root">
  <code><strong><a href="#user-content-directmergeconfig.root">root</a></strong>&#8288;?: <a href="https://developer.mozilla.org/en/docs/DOM/document">Document</a> | <a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot">ShadowRoot</a></code></dt>

<dd><p>An optional root. Only necessary if the view is mounted in a
shadow root or a document other than the global <code>document</code>
object.</p>
</dd></dl>

</dd>
<dt id="user-content-mergeview">
  <h4>
    <code>class</code>
    <a href="#user-content-mergeview">MergeView</a></h4>
</dt>

<dd><p>A merge view manages two editors side-by-side, highlighting the
difference between them and vertically aligning unchanged lines.
If you want one of the editors to be read-only, you have to
configure that in its extensions.</p>
<p>By default, views are not scrollable. Style them (<code>.cm-mergeView</code>)
with a height and <code>overflow: auto</code> to make them scrollable.</p>
<dl><dt id="user-content-mergeview.constructor">
  <code>new <strong><a href="#user-content-mergeview.constructor">MergeView</a></strong>(<a id="user-content-mergeview.constructor^config" href="#user-content-mergeview.constructor^config">config</a>: <a href="#user-content-directmergeconfig">DirectMergeConfig</a>)</code></dt>

<dd><p>Create a new merge view.</p>
</dd><dt id="user-content-mergeview.a">
  <code><strong><a href="#user-content-mergeview.a">a</a></strong>: <a href="https://codemirror.net/docs/ref#view.EditorView">EditorView</a></code></dt>

<dd><p>The first editor.</p>
</dd><dt id="user-content-mergeview.b">
  <code><strong><a href="#user-content-mergeview.b">b</a></strong>: <a href="https://codemirror.net/docs/ref#view.EditorView">EditorView</a></code></dt>

<dd><p>The second editor.</p>
</dd><dt id="user-content-mergeview.dom">
  <code><strong><a href="#user-content-mergeview.dom">dom</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement">HTMLElement</a></code></dt>

<dd><p>The outer DOM element holding the view.</p>
</dd><dt id="user-content-mergeview.chunks">
  <code><strong><a href="#user-content-mergeview.chunks">chunks</a></strong>: readonly <a href="#user-content-chunk">Chunk</a>[]</code></dt>

<dd><p>The current set of changed chunks.</p>
</dd><dt id="user-content-mergeview.reconfigure">
  <code><strong><a href="#user-content-mergeview.reconfigure">reconfigure</a></strong>(<a id="user-content-mergeview.reconfigure^config" href="#user-content-mergeview.reconfigure^config">config</a>: <a href="#user-content-mergeconfig">MergeConfig</a>)</code></dt>

<dd><p>Reconfigure an existing merge view.</p>
</dd><dt id="user-content-mergeview.destroy">
  <code><strong><a href="#user-content-mergeview.destroy">destroy</a></strong>()</code></dt>

<dd><p>Destroy this merge view.</p>
</dd></dl>

</dd>
<dt id="user-content-chunk">
  <h4>
    <code>class</code>
    <a href="#user-content-chunk">Chunk</a></h4>
</dt>

<dd><p>A chunk describes a range of lines which have changed content in
them. Either side (a/b) may either be empty (when its <code>to</code> is
equal to its <code>from</code>), or points at a range starting at the start
of the first changed line, to 1 past the end of the last changed
line. Note that <code>to</code> positions may point past the end of the
document. Use <code>endA</code>/<code>endB</code> if you need an end position that is
certain to be a valid document position.</p>
<dl><dt id="user-content-chunk.constructor">
  <code>new <strong><a href="#user-content-chunk.constructor">Chunk</a></strong>(<a id="user-content-chunk.constructor^changes" href="#user-content-chunk.constructor^changes">changes</a>: readonly <a href="#user-content-change">Change</a>[], <a id="user-content-chunk.constructor^froma" href="#user-content-chunk.constructor^froma">fromA</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, <a id="user-content-chunk.constructor^toa" href="#user-content-chunk.constructor^toa">toA</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, <a id="user-content-chunk.constructor^fromb" href="#user-content-chunk.constructor^fromb">fromB</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, <a id="user-content-chunk.constructor^tob" href="#user-content-chunk.constructor^tob">toB</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>)</code></dt>

<dd></dd><dt id="user-content-chunk.changes">
  <code><strong><a href="#user-content-chunk.changes">changes</a></strong>: readonly <a href="#user-content-change">Change</a>[]</code></dt>

<dd><p>The individual changes inside this chunk. These are stored
relative to the start of the chunk, so you have to add
<code>chunk.fromA</code>/<code>fromB</code> to get document positions.</p>
</dd><dt id="user-content-chunk.froma">
  <code><strong><a href="#user-content-chunk.froma">fromA</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The start of the chunk in document A.</p>
</dd><dt id="user-content-chunk.toa">
  <code><strong><a href="#user-content-chunk.toa">toA</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The end of the chunk in document A. This is equal to <code>fromA</code>
when the chunk covers no lines in document A, or is one unit
past the end of the last line in the chunk if it does.</p>
</dd><dt id="user-content-chunk.fromb">
  <code><strong><a href="#user-content-chunk.fromb">fromB</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The start of the chunk in document B.</p>
</dd><dt id="user-content-chunk.tob">
  <code><strong><a href="#user-content-chunk.tob">toB</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The end of the chunk in document A.</p>
</dd><dt id="user-content-chunk.enda">
  <code><strong><a href="#user-content-chunk.enda">endA</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>Returns <code>fromA</code> if the chunk is empty in A, or the end of the
last line in the chunk otherwise.</p>
</dd><dt id="user-content-chunk.endb">
  <code><strong><a href="#user-content-chunk.endb">endB</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>Returns <code>fromB</code> if the chunk is empty in B, or the end of the
last line in the chunk otherwise.</p>
</dd></dl>

</dd>
<dt id="user-content-getchunks">
  <code><strong><a href="#user-content-getchunks">getChunks</a></strong>(<a id="user-content-getchunks^state" href="#user-content-getchunks^state">state</a>: <a href="https://codemirror.net/docs/ref#state.EditorState">EditorState</a>) → {chunks: readonly <a href="#user-content-chunk">Chunk</a>[], side: &quot;a&quot; | &quot;b&quot;} | <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null">null</a></code></dt>

<dd><p>Get the changed chunks for the merge view that this editor is part
of, plus the side it is on. Or null if the editor isn't part of a
merge view or the merge view hasn't finished initializing yet.</p>
</dd>
</dl>
<p>This package also exports the diffing utilities it uses internally.</p>
<dl>
<dt id="user-content-change">
  <h4>
    <code>class</code>
    <a href="#user-content-change">Change</a></h4>
</dt>

<dd><p>A changed range.</p>
<dl><dt id="user-content-change.constructor">
  <code>new <strong><a href="#user-content-change.constructor">Change</a></strong>(<a id="user-content-change.constructor^froma" href="#user-content-change.constructor^froma">fromA</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, <a id="user-content-change.constructor^toa" href="#user-content-change.constructor^toa">toA</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, <a id="user-content-change.constructor^fromb" href="#user-content-change.constructor^fromb">fromB</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>, <a id="user-content-change.constructor^tob" href="#user-content-change.constructor^tob">toB</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a>)</code></dt>

<dd></dd><dt id="user-content-change.froma">
  <code><strong><a href="#user-content-change.froma">fromA</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The start of the change in document A.</p>
</dd><dt id="user-content-change.toa">
  <code><strong><a href="#user-content-change.toa">toA</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The end of the change in document A. This is equal to <code>fromA</code>
in case of insertions.</p>
</dd><dt id="user-content-change.fromb">
  <code><strong><a href="#user-content-change.fromb">fromB</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The start of the change in document B.</p>
</dd><dt id="user-content-change.tob">
  <code><strong><a href="#user-content-change.tob">toB</a></strong>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number">number</a></code></dt>

<dd><p>The end of the change in document B. This is equal to <code>fromB</code>
for deletions.</p>
</dd></dl>

</dd>
<dt id="user-content-diff">
  <code><strong><a href="#user-content-diff">diff</a></strong>(<a id="user-content-diff^a" href="#user-content-diff^a">a</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String">string</a>, <a id="user-content-diff^b" href="#user-content-diff^b">b</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String">string</a>) → readonly <a href="#user-content-change">Change</a>[]</code></dt>

<dd><p>Compute the difference between two strings.</p>
</dd>
<dt id="user-content-presentablediff">
  <code><strong><a href="#user-content-presentablediff">presentableDiff</a></strong>(<a id="user-content-presentablediff^a" href="#user-content-presentablediff^a">a</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String">string</a>, <a id="user-content-presentablediff^b" href="#user-content-presentablediff^b">b</a>: <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String">string</a>) → readonly <a href="#user-content-change">Change</a>[]</code></dt>

<dd><p>Compute the difference between the given strings, and clean up the
resulting diff for presentation to users by dropping short
unchanged ranges, and aligning changes to word boundaries when
appropriate.</p>
</dd>
</dl>
