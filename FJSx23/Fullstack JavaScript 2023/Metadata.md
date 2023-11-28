Back to [[FJSx23]]

### What is it?
Meta is a word for information about information. In HTML it is used in the head tag and is information about the website that is not directly visible to visitors. It is used for webscrapers, search engine crawlers and social media to gain information about your site for various purposes, like knowing what description and image to use in a link.

#### Social Media:
```html
<head>
    <meta property="og:title" content="My Awesome Site" />
    <meta property="og:description" content="Description of my site." />
    <meta property="og:image" content="http://example.com/image.jpg" />
    <meta property="og:url" content="http://example.com/" />
    <meta property="og:type" content="website" />
</head>
```

#### SEO Metadata for search engines:
```html
<head>
    <title>My Awesome Site</title>
    <meta name="description" content="Description of my site." />
    <meta name="keywords" content="keyword1, keyword2, keyword3" />
    <link rel="canonical" href="http://example.com/" />
</head>
```

#### Charset and viewport metadata:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

