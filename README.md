tinymce_rte config loader
=========================

The Loader allows to separate code and configuration. The built in mutation observer monitors newly created elements in the DOM. If an object is created, which fits to the selector, it is transformed into a TinyMCE editor.

#### usage ####

* load dependencies
    * tinyMCE.js
    * depend/MutationObserver.js
* load tinymce_rte.js
* define tinymce_rte.defaultOptions as an object in json notation
* run tinyMCE.init one time

#### example ####

```html
<script type="text/javascript" src="tinyMCE.js"></script>
<script type="text/javascript" src="depend/depend/MutationObserver.js"></script>
<script type="text/javascript" src="tinymce_rte.js"></script>

<script>

	tinymce.init({
		browser_spellcheck: true,
		paste_as_text: true,
		remove_script_host: false,
		relative_urls: false,
		autoresize_max_height: 500,
		hidden_input: false,
		plugins: ['advlist autolink lists charmap hr anchor pagebreak searchreplace wordcount visualblocks visualchars code',
		'nonbreaking save directionality template paste autoresize'],

		toolbar1: 'undo redo | styleselect | bold italic | typo3link typo3image | '
		+ 'alignleft aligncenter alignright alignjustify | bullist numlist',

		style_formats: [
		{
			title: 'Headers', items: [
			{title: 'Header 3', block: 'h3'},
			{title: 'Header 4', block: 'h4'},
			{title: 'Header 5', block: 'h5'},
			{title: 'Header 6', block: 'h6'},
			]
		},

		{
			title: 'Blocks', items: [
			{title: 'Paragraph', block: 'p'},
			{title: 'Blockquote', block: 'blockquote'},
			{title: 'Pre', block: 'pre'}
			]

		},
		],
		formats: {
			alignleft: {selector: 'p,h1,h2,h3,h4,h5,h6,td,th,div,ul,ol,li,table,img', classes: 'left'},
			aligncenter: {selector: 'p,h1,h2,h3,h4,h5,h6,td,th,div,ul,ol,li,table,img', classes: 'center'},
			alignright: {selector: 'p,h1,h2,h3,h4,h5,h6,td,th,div,ul,ol,li,table,img', classes: 'right'},
			alignfull: {selector: 'p,h1,h2,h3,h4,h5,h6,td,th,div,ul,ol,li,table,img', classes: 'full'},
			bold: {inline: 'span', 'classes': 'bold'},
			italic: {inline: 'span', 'classes': 'italic'},
			underline: {inline: 'span', 'classes': 'underline'},
			strikethrough: {inline: 'del'}
		},

		convert_fonts_to_spans : true,
		fix_list_elements : true,
		keep_styles: false

	});

</script>
```

#### dependencies ####

[TinyMCE](https://github.com/webcomponents/webcomponentsjs/blob/master/src/MutationObserver/MutationObserver.js)
[TinyMCE RTE](http://www.tinymce.com/)
[MutationObserver](https://github.com/webcomponents/webcomponentsjs/blob/master/src/MutationObserver/MutationObserver.js)

#### attention ####

the code is untested. 