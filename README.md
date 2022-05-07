---

## Shortcode example 

```
[pbl] //Enter your markup here [/pbl]
```

## Shortcode markup

The HTML markup inserted between the `[pbl]` and `[/pbl]` will be used to create the markup for each item (post) in the loop.

For e.g.

`[pbl] <h4>{title}</h4> [/pbl]`

will generate the following output

#### Post 1 Title

#### Post 2 Title

#### Post 3 Title

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

### **List of supported markup template tags**

- `{title}` \- Inserts post title)
- `{link}` \- Inserts post permalink
- `{thumbnail}` \- Inserts post thumbnail with `<img>` markup
- `{thumbnail-url}` \- Inserts post thumbnail URL
- `{thumbnail-alt}` \- Inserts alt text of the thumbnail image or post title as alt text
- `{author-url}` \- Inserts URL or the author page
- `{author-name}` \- Inserts name of the author
- `{date}` \- Inserts post date
- `{terms}` \- Inserts comma-separated post category list with a hyperlink to each category page.
- `{excerpt}` \- Inserts the post excerpt
- `{lang}` \- Inserts language code of the post 

## Shortcode parameters

The shortcode supports multiple parameters to customize the query and the output

### Example of using shortcode parameters

```
[pbl lang="en" posts_per_page=10][/pbl]
```

This shortcode will display 10 recent posts with language code "en" and use the [default markup](<https://github.com/samirank/get-posts-by-language/blob/main/README.md#default-markup>)

### List of supported parameters

- `lang` (string) - Retrieves posts by language. Can accept multiple language codes separated by a comma. E.g. `[pbl lang="en"][/pbl]` will retrieve posts with language code "en" (English), and `[pbl lang="en, de"][/pbl]` will retrieve English (en) and German (de) posts. Default is the active post/page language.

- `lang_detect` (string) - Method used to detect language automatically. Default: 'parent'.<br>

    Supported values:

    - `polylang` \- uses polylang function[ *pll\_current\_language()*](<https://polylang.pro/doc/function-reference/#pll_current_language>) to get the language code
    - `locale` \- uses WordPress function *[get\_locale()](<https://developer.wordpress.org/reference/functions/get_locale/>)* to detect current language
    - `bloginfo` \- uses WordPress function [*get\_bloginfo( 'language' )*](<https://developer.wordpress.org/reference/functions/bloginfo/>) to detect active language
    - `parent` (Default) - uses the language code of the post/page where the shortcode is used.

    - `post_type` (string) - Retrieves posts by post types, default value is ‘post‘. [*See WordPress documentation*](<https://developer.wordpress.org/reference/classes/wp_query/#post-type-parameters>)

- `post_status` (string) - Retrieves posts by post status. Default value is ‘publish‘ [*See WordPress documentation*](<https://developer.wordpress.org/reference/classes/wp_query/#status-parameters>)

- `posts_per_page` (int) - Number of posts to show per page. [*See WordPress documentation*](<https://developer.wordpress.org/reference/classes/wp_query/#pagination-parameters>)

- `offset` (int) - Number of posts to displace or pass over. [*See WordPress documentation*](<https://developer.wordpress.org/reference/classes/wp_query/#pagination-parameters>)

- `orderby` (string) - Sort retrieved posts by parameter. Defaults to ‘date (post\_date)’. [*See WordPress documentation*](<https://developer.wordpress.org/reference/classes/wp_query/#order-orderby-parameters>)

- `order` (string) - Designates the ascending or descending order of the ‘orderby‘ parameter. [*See WordPress documentation*](<https://developer.wordpress.org/reference/classes/wp_query/#order-orderby-parameters>)

- `cat_sep` (string) - Separator between the categories. Default is a comma `', '`







