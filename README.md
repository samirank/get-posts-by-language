# Display posts by language

---

## Shortcode example 

```
[pbl] //Enter your markup here [/pbl]
```

## Shortcode markup

The HTML markup inserted between the `[pbl]` and `[/pbl]` will be used to create the markup for each item (post) in the loop.

For e.g.

`[pbl] &amp;amp;lt;h4&amp;amp;gt;{title}&amp;amp;lt;/h4&amp;amp;gt; [/pbl]`

will generate the following output

#### Title 1

#### Title 2

#### Title 3

#### …

### Default markup

If no markup is provided between the `[pbl]` and `[/pbl]` tags, the following default markup will be used

```
<div class="pbl-item">
    <div class="pbl-title"><a href="{link}">{title}</a></div>
    <a class="pbl-thumbnail" href="{link}">
        {thumbnail}
    </a>
    <div class="pbl-meta">
        <div class="pbl-author">
            <a href="{author-url}">{author-name}</a>
        </div>
        <div class="pbl-date">
            {date}
        </div>
        <div class="pbl-terms">
            {terms}
        </div>
    </div>
    <div class="pbl-content">
        {excerpt}
    </div>
</div>
```

### Example of custom markup

Here is an example of how a custom markup can be provided to overwrite the default markup.

```
[pbl]
<div class="item">
     <h3><a href="{link}">{title}</a></h3>
     {thumbnail}
     <div class="categories">{terms}</div>
     {excerpt}
     <a class="read-more-link" href="{link}>Read more</a>
</div>
[/pbl]
```

### **List of supported mark-up template tags**

- `{title}` \- Inserts post title)
- `{link}` \- Inserts post permalink
- `{thumbnail}` \- Inserts post thumbnail with `&amp;amp;amp;amp;amp;amp;amp;lt;img&amp;amp;amp;amp;amp;amp;amp;gt;` markup
- `{thumbnail-url}` \- Inserts post thumbnail URL
- `{thumbnail-alt}` \- Inserts alt text of the thumbnail image or post title as alt text
- `{author-url}` \- Inserts URL or the author page
- `{author-name}` \- Inserts name of the author
- `{date}` \- Inserts post date
- `{terms}` \- Inserts comma-separated post category list with a hyperlink to each category page.
- `{excerpt}` \- Inserts the post excerpt
- `{lang}` \- Inserts language code of the post 

## Shortcode attributes

The shortcode supports multiple attributes to customize the query and the output

