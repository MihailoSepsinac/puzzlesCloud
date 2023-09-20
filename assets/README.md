---
weight: 2
---
`site.author` | `site.author.name`
`site.email`  | `site.author.email`


### Social networks

You can add links to the accounts you have on other sites, with respective icon as an SVG graphic, via the config file.
From `Minima-3.0` onwards, the social media data is sourced from config key `minima.social_links`. It is a list of key-value pairs, each entry
corresponding to a link rendered in the footer. For example, to render links to Jekyll GitHub repository and twitter account, one should have:

```yaml
minima:
  social_links:
    - { platform: github,  user_url: "https://github.com/jekyll/jekyll" }
    - { platform: twitter, user_url: "https://twitter.com/jekyllrb" }
```

Apart from the necessary keys illustrated above, `title` may also be defined to render a custom link-title. By default, the title is the same
as `platform`. The `platform` key corresponds to the SVG id of the sprite in the composite file at URL `/assets/minima-social-icons.svg`.

The theme ships with an icon for `rss` and icons of select social-media platforms:

- `devto`
- `dribbble`
- `facebook`
- `flickr`
- `github`
- `google_scholar`
- `instagram`
- `keybase`
- `linkedin`
- `microdotblog`
- `pinterest`
- `stackoverflow`
- `telegram`
- `twitter`
- `youtube`

To render a link to a platform not listed above, one should first create a file at path `_includes/social-icons/<PLATFORM>.svg` comprised of
graphic markup **without the top-level `<svg></svg>`**. The icon is expected to be centered within a viewbox of `"0 0 16 16"`. Then, make an
entry under key `minima.social_links`.

For example, to render a link to an account of user `john.doe` at platform `deviantart.com`, the steps to follow would be:
  - Get DeviantArt logo in SVG format.
  - Using a text-editor, open the downloaded file to inspect if the `viewBox` attribute is defined on the `<svg>` element and is set
    as `"0 0 16 16" (or similar "square" dimension)`.
  - If the `viewBox` attribute is non-square or undefined, the graphic *may optionally need* to be edited in a vector graphic editor such as
    *Inkscape* or *Adobe Illustrator* for properly aligned render on page.
  - Edit the SVG file in text-editor to delete everything **except** what is contained between `<svg></svg>` and save it into the Jekyll
    project at path `_includes/social-icons/deviantart.svg`.
  - Finally, edit the Jekyll config file to enable loading of new icon graphic with:
    ```yaml
    minima:
      social_links:
        - platform: deviantart  # same as SVG filename.
          user_url: "https://www.deviantart.com/john.doe"  # URL of profile page.
          title:  My profile at DeviantArt.com  # Optional. Text displayed on hovering over link.
    ```

**Notes:**
- The list of social-links is declarative. List-items are rendered in the order declared in the downstream configuration file and not merged
  with entries from upstream config file(s) such as theme-config-file or prior local config files.
- The `user_url` is rendered as given without handling any special characters within.


### Enabling Google Analytics

To enable Google Analytics, add the following lines to your Jekyll site:

```yaml
  google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

### Enabling Excerpts on the Home Page

To display post-excerpts on the Home Page, simply add the following to your `_config.yml`:

```yaml
show_excerpts: true
```


## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/jekyll/minima. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `script/bootstrap`.

To test your theme, run `script/server` (or `bundle exec jekyll serve`) and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme and the contents. As you make modifications, your site will regenerate and you should see the changes in the browser after a refresh.

## License

The theme is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).