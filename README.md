Gohugo bug - Base URLs with path cause problems for static images
=================================================================

This example repository supports the GitHub issue https://github.com/gohugoio/hugo/issues/8078

```
Given my base URL (`config.toml`) is http://example.org/blog - which is an URL that includes a path
And my config.toml file includes `canonifyurls = true`
And I have an image `example.jpg` in my `static` directory
And I reference the image in my markdown file using `![Example image here](/example.jpg)`
And I reference the image in my markdown file using `![Example image here](/blog/example.jpg)`
When I generate the website using `hugo server` (see also `public` directory for output using `hugo`)
And I visit the example post http://localhost:1313/blog/posts/example-post/
Then I can see that the image reference using `/example.jpg` does not work
And I can see that the image reference using `/blog/example.jpg` does work
```

Please note that the problem can be fixed when using `canonifyurls = true` in the `config.toml` file but I am not sure as it is desired. It plays fine with the ananke theme, but with other themes i.e. with anubis it then causes other links to break, such as the archive URL.


--------------------




Generated with hugo 0.80.0, `hugo new site quickstart`
