# Pico Categories Page

### About
Categories Page for PicoCMS. Provide Categories Page and Meta Category.

### Instalation
1. [Download](https://github.com/julindra/pico_categories_page/archive/master.zip).
2. Extract and copy folder `pico_categories_page` to your Pico `plugins` folder.
3. Add a category to your post. Example:
	<pre>
	/*
		Title: Third Day
		Description: Third day. Let's be happy
		Author: Renhard Julindra
		Date: 2015/11/4 21:00
		Category: My Story
	*/
	</pre>
4. Create a page named `categories.md`, and fill with:
	<pre>
	/*
		Title: Categories
		Purpose: pico_categories_page
	*/
	</pre>
5. Add the following code to your theme:
````html	
	<pre>
	{% if meta.purpose == "pico_categories_page" %}
		<ul style="list-style-type: none;">
			{% for cat, cated_pages in pico_categories_page %}
				<li>
					<h4><b>{{ cat }}</b></h4>
					<ul>
						{% for cated_page_title, cated_page_link in cated_pages %}
							<li><a href="{{ cated_page_link }}">{{ cated_page_title }}</a></li>
						{% endfor %}
					</ul>
				</li>
			{% endfor %}
		</ul>
	{% endif %}
	</pre>
````
6. That's it. Open browser and go to Categories page (Ex: http://mywebsite.com/categories).
7. Category can now be accessed with `{{ meta.category }}`.

### Screenshot
<img src="http://renhard.net/github/pico_categories_page/pico_categories_page.png" alt="Pico Categories Page">

### About Pico
Pico is a stupidly simple, blazing fast, flat file CMS. See http://pico.dev7studios.com for more info.