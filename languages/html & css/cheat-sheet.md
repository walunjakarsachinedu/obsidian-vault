# HTML5 & CSS3 Notes

This is my study notes for HTML5 & CSS3. You will find lot of basic HTML/CSS stuff as well. This is because I didn't know even the basics and taking notes on them as well.  

reference: http://developers.whatwg.org/ and several other sources. Many points were noted using firebug (firefox add-on) during usual browsing.

This document has 3 major sections:
* HTML5
* CSS3
* How To

---

# HTML5

## Text Level Semantics

reference: http://developers.whatwg.org/text-level-semantics.html#text-level-semantics

* `a element` -- anchor. useful to provide a link for a block of content. also helpful for cross reference using `id`. e.g. a text ad that should have a link wherever it is clicked.
* `em element` -- emphasis. emphasizing a particular word or phrase. e.g. you are _not_ welcome!. not to be confused with `i element`. typically emphasis changes the meaning of a sentence in a subtle way. think about this example.
* `i element` -- change of context. voice, thinking, mood, etc. e.g. "i loved it" _not really but can i tell the truth?_
* `strong element` -- represents strong importance of its contents. does not change the meaning of a sentence. e.g. *warning*: contents are inflammable.
* `b` -- content to draw attention. without adding importance or change in mood or voice. e.g. `<b>Ragu</b> and <b>Anu</b> are brothers since birth.`
* `mark` -- part of text highlighted for reference purpose. may not be intended by original author. e.g. searched word highlighted in search results.
* `small element` -- small print. disclaimers, caveats, legal restrictions or copyrights. meant for short runs of text only. when legal info becomes main content, it should not be marked as small. also it doesn't mean low importance. `small` content can be marked as `strong`. e.g. `<strong><small>violation of this rule is unacceptable</small></strong>`
* `s element` -- content no longer relevant or accurate. not to be confused with `del`. e.g. MRP Rs 100; Our price Rs 99.99
* `del element` -- removal from document. e.g. todo list done entries.
* `cite` -- citation. title of the quoted content from elsewhere. referred content. not to be confused with quote `q element`. it is only title.
* `q` -- quoting something. should not include quotation marks. it is work of styling.
* `dfn` -- definitions. just as in the beginning of formal documents. e.g. `<dfn><abbr title="Maximum Retail Price">MRB</abbr></dfn>`
* `abbr` -- marks something as abbreviation. `title` attribute is optional to provide the expanded version of the abbreviation.
* `data` -- provides machine readable form of content. e.g. <data value="10">patthu is the tamil word for ten</data>`. also see `time`.
* `time` -- special case of `data`. date, time, time zone, etc. e.g. `<time>2012-08-15</time>`.
* `code` -- computer source code. e.g. `The <code>code</code> element represents a fragment of computer code.`
* `var` -- variable. placeholder. e.g. `Rs 25 x <var>qty</var> = <var>total</var>`.
* `samp` -- sample program output. e.g. `Output: <samp>Hello World!</samp>`
* `kbd` -- user input. e.g. `<kbd>Ctrl</kbd>+<kbd>F4</kbd>` or `<kbd>File | Exit</kbd>`
* `sub` and `sup` -- sub and superscripts respectively. not for styling (branding LaTeX). Only to be used if the superscript and subscript meaning is important. e.g. `E=MC<sup>2</sup>`
* `ruby` -- nothing to do with ruby language. useful in case of parallel annotation with the content. e.g. english transliteration over tamil words in a sentence.
* `span` -- means nothing. used with global attributes such as `class`, `lang`, or `dir`. e.g. `In Tamil, we greet with <span lang="ta">vaanga</span>`. Another e.g. `<code class="lang-ruby"><span class="keyword">def</span> initialize</code>`.
* `br` -- line break. not actually meant for styling/presentation. again meant for meaning. useful for poetry, address, etc.
* `wbr` -- line break opportunity. useful in source code markup. e.g. `def a_method(param1, <wbr>param2, <wbr>param3)`

for usage summary look [here](http://developers.whatwg.org/text-level-semantics.html#usage-summary).

## Sections

reference: http://developers.whatwg.org/sections.html#sections

* `body` -- main content of the document. just one per page.
* `section` -- parts of the document. e.g. home page can be split into intro, news items, contact info, etc. tabbed box can have different section for each tab, chapters.
* `article` -- useful for syndication. independently distributable or reusable. e.g. forum post, blog post, etc. `article` may have `sections`. `sections` can have `articles`. go figure.
* `nav` -- navigation. a section with navigation links. special case of section. e.g. table of contents, links to major pages that should appear in all the pages, etc.
* `aside` -- content related to and part of main content. special case of section. could contain `q` quote. e.g. highlight of an article.
* `h1`, `h2`, ..., `h6` -- headings, subheadings, etc. e.g. `<h3>How to:</h3><h1>Programming without using hands</h1><h2>You never thought it is possible! Did you?</h2>`
* `hgroup` -- heading of a section. used for grouping h1, h2, .... e.g. previous example could be contained with this tag.
* `header` -- group of introductory or navigation aids. could contain `hgroup`.
* `footer` -- represents footer. not necessarily that has to appear in the end. because it is presentation concern. e.g. author, copyright, etc. of an article.
* `address` -- _not_ meant for postal addresses unless it is related to contact info of the current page or article. could be part of footer.

## Content Flow

* `figure` -- contains a unit where the main content can _flow_ around. similar to magazine content where the text can flow around an image, side bar, did you know?, etc.
* `figcaption` -- provides a caption for the `figure`.
* `div` -- avoid using it whatever it means. this is probably the mostly used tag though. :)

## Grouping

* `ul` -- unordered list
* `li` -- list item. need not have closing tag. e.g. `<ul><li>india<li>srilanka</ul>`
* `ol` -- ordered list
* `dl` -- definition list. e.g. `<dl><dt>gold<dd>a rare metal<dt>silver<dd>not that rare</dl>` where `dt` is defn title; `dd` is defn description
* `pre` -- pre-formatted text. useful for formatting `code` for example. ascii art. etc.
* `hr` -- separates content. typically horizontal rule. but again it is the meaning that matters in HTML5; not presentation.

## Forms

* `form` -- form which contains elements that take input
* `input` -- `<input type=checkbox id=a_checkbox value=cheeze checked>`. It has many other types such as `textbox`, `radio`, `submit`, `reset`.
* `button` -- alternative to input when it comes to buttons such as `submit` or `reset`. It have more possibilities for styling through CSS.
* `fieldset` -- Helps to group related items such as radio buttons, checkboxes, etc.
* `label` -- a label to go along with the input controls. e.g. `<label>Cheese: <input...`
* Possible client side possibilities and validations: `range`, `pattern`, `datalist`, `autofocus`, `email`, `url`, `tel`, `required`

## Link Relations

* `rel=` -- used along with `link` element. possible to provide different relationships to semantically relate a particular link or a file
* `rel=stylesheet` -- points to css file that is to be used for rendering the page.
* `rel=alternate` -- useful for rss feed link, pdf version of the page, etc.
* `rel=prev` `rel=next` `rel=start` `rel=end` -- relates other pages with the current page. Helpful for navigation between related pages.
* `rel=shortcut icon` -- sets favicon.
* `rel=prefetch` -- indicates specified resource to be likely necessary and helpful if fetched before hand.
* `rel=search` -- references document helpful for searching current page. This should be [OpenSearch](http://www.opensearch.org/Home) document.
* `rel=tag` -- useful for specifying tags or categories of the page.

## Rich Media

* `video` -- Streaming video. Additional options: `controls`, `poster`, `preload`, `autoplay`, `repeat`, etc.
* `audio` -- Streaming audio.
* `canvas` -- Block element that marks up the area for drawing. Tutorial [here](http://devhammer.net/blog/exploring-html5-canvas-part-1---introduction)
* SVG -- It is no more just image format that is scalable better! Of course, svg could be used as part of `img`. Since svg is xml, it can be directly embedded in html. Most interesting thing is different svg elements can raise events and accordingly javascript code can manipulate the svg shapes. Here is a beautiful [example](http://croczilla.com/bits_and_pieces/svg/samples/svgtetris/svgtetris.svg).

## Advanced Features

* Local Storage -- Caching at the client side. Not merely cookies. Can have a whole web app cached locally.
* Canvas Text API -- Provides a way to draw text. Though Canvas is generally supported by modern browsers, text API support is not widespread yet.
* Web Workers -- Threaded execution for scripts. Not yet widespread support.
* Offline Web Application -- Can work with web app even if offline. When we go online, data will be in sync. Very important for mobile apps.
* Microdata -- Standards for additional semantic info. E.g. Contact details if specified in standardized microdata format, it can be converted to vCard.
* History API -- Allows to read and manipulate browsing history. For example, going back/forward need not refresh the whole page since the page can decide what to refresh from the previous page.
* [WebM](http://www.webmproject.org/) -- Open video format designed for HTML5. WebM is supported by Mozilla, Opera, Adobe, Google and more than seventy other publishers and software and hardware vendors. Also checkout WebP which seems to be similar thing for photos.
* Geolocation API -- Provides a way to work with client's current location. 

# CSS3

* CSS selectors -- Ways to identify the portion of html to set the styles to. It could be based on `id`, `class`, `span`, `div`, etc.
* Precedence -- The styles will be applied on a particular precedence. User's browser preferences take the top priority. Then the parent element's style, and so on.
* Possibilities -- font size, typeface, underline, overline, strikethrough, color, etc.
* Even bullet styles can change. Within the bullet points first can be different, or the last can be different, or the nth item can be different.

## text

* `text-shadow` -- provides shadow effect
* `text-transform` -- uppercase, camel case, etc.

## font

* `font-size` -- don't use pt or px since they cannot be standardized. Reference [this](http://kyleschaeffer.com/best-practices/css-font-size-em-vs-px-vs-pt-vs/) article for best practice. 
* font possibilities -- simply everything. `font-weight`, `line-height`, `letter-spacing`, `word-spacing`, `font-variant`, `font-style`, alignments, indent, `white-space`, `text-decoration`

## color & background

* ways to specify colors -- named colors, hex, rgb, hsl, rgba, hsla
* background -- color, image, pattern / tiling, positioning, attachment (scroll/fixed). Allows `shorthand` for mixing different options.

## list

* `list-style-type` -- none for horizontal menu. numbered, roman, circle, etc.
* `list-style-image` -- image in place of bullets
* `list-style-position` -- level of indentation

## table

* `border`, `border-spacing`
* `caption-side` 
* There are just too many ways to slice and dice tables. Sky is the limit!
* border styles, background color for specific row/column/cell, etc.

## box

* As opposed to inline elements such as `i`, `em`, etc., special styling can be done for block style or box elements such as `div`.
* Background colour, margin, alignment, border, outline, stacking, overflow are some of the possibilities.
* `cursor` allows to set a cursor style when a particular element is hovered over.
* `border-radius` provides fillets for box. Specific fillet is also possible such as `border-bottom-right-border`

# How To

* How to get rid of the underline in links? `text-decoration: none`