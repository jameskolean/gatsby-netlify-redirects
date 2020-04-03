# Gatsby Netlify Redirects

Gatsby-Netlify-Redirects demonstrates how to do redirects on the edge with Netlify.
There are two options:

1. Use `_redirects`
   To use this you need to create a file called \_redirects in the static folder. In ther you can add you redirects. See Netlify docs [here](https://docs.netlify.com/routing/redirects/#syntax-for-the-redirects-file)

example

```
# redirect request for non-existent page at /no-where to /welcome-to-the-blog
/no-where              /welcome-to-the-blog
```

2. Another option is to use `netlify.toml` this file should be in the broject root and can contain rules. Here is an exapmle of different routes based on Locales. Note: as of this writing there is a bug preventing this from working with complex accepts-language header. It should be fixed in Q2 of 2020

```
[[redirects]]
  from = "/no-where/*"
  to = "/welcome-to-the-blog"
  conditions = {Language = ["en"], Country = ["US"]}

[[redirects]]
  from = "/no-where/*"
  to = "/hello-world"
  conditions = {Language = ["fr"], Country = ["FR"]}
```
