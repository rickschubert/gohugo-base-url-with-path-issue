Gohugo bug - Base URLs with path cause problems for static images
=================================================================

This example repository supports the GitHub issue https://github.com/gohugoio/hugo/issues/8078

Given my base URL (`config.toml`) is http://example.org/blog - which is an URL that includes a path
And I have an image `example.jpg` in my `static` directory
And I reference the image in my markdown file using `![Example image here](/example.jpg)`
And I reference the image in my markdown file using `![Example image here](/blog/example.jpg)`
When I generate the website using `hugo`
And I visit the example post http://localhost:1313/blog/posts/example-post/
Then I can see that the image reference using `/example.jpg` does not work
And I can see that the image reference using `/blog/example.jpg` does work


Generated with hugo 0.80.0, `hugo new site quickstart`
