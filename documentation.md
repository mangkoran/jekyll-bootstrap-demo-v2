---
layout: post
title: Documentation
---

# Preface

When we were children, Hassan and I used to climb the poplar trees in
the driveway of my father’s house and annoy our neigh-bors by reflecting
sunlight into their homes with a shard of mirror. We would sit across
from each other on a pair of high branches, our naked feet dangling, our
trouser pockets filled with dried mul-berries and walnuts. We took turns
with the mirror as we ate mul-berries, pelted each other with them,
giggling, laughing. I can still see Hassan up on that tree, sunlight
flickering through the leaves on his almost perfectly round face, a face
like a Chinese doll chis-eled from hardwood: his flat, broad nose and
slanting, narrow eyes like bamboo leaves, eyes that looked, depending on
the light, gold, green, even sapphire. I can still see his tiny low-set
ears and that pointed stub of a chin, a meaty appendage that looked like
it was added as a mere afterthought. And the cleft lip, just left of
midline, where the Chinese doll maker’s instrument may have slipped, or
perhaps he had simply grown tired and careless.

*-The Kite Runner*

# Prerequisites

-   `git`
-   Whatever in [Jekyll's
    prerequisites](https://jekyllrb.com/docs/installation/)

# Steps

## Jekyll Setup

Make sure you already have local Jekyll website. I won't explain how to
setup a Jekyll website from scratch here, as it already covered in
[Jekyll's own
tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/).

## Bootstrap Setup

Assuming that your Jekyll site has `_sass` directory:

-   Clone Bootstrap repository into your site's `_sass` directory (so it
    will be `_sass/Bootstrap`):

``` bash
git clone https://github.com/twbs/bootstrap.git _sass/Bootstrap
```

-   Or if your site is a `git` repository, add Bootstrap repository as
    `git` submodule:

``` bash
git submodule add https://github.com/twbs/bootstrap.git _sass/Bootstrap
```

Create a SCSS file for your website. Here I named it `styles.scss` with
the following code:

``` scss
---
---
@import "main";
```

The `---` section is needed to tell Jekyll to process this file. It
isn't required in the other SCSS files as they will be processed by
Sass.

In `_sass` directory create `main.scss` containing the following code:

``` scss
@import "custom_variables" /* if you want to override certain Bootstrap variables,
                            * create custom_variables.scss and add this line */
@import "bootstrap/scss/bootstrap"
```

In `_config.yml` make sure to have the following configuration:

``` yaml
sass:
    sass_dir: _sass
    style: compressed
```

This informs Jekyll that our Sass files are placed in `_sass` directory
and it should "compress" the CSS it produces. However, as we building
Bootstrap from Sass source, it needs to be
[autoprefixed](https://github.com/postcss/autoprefixer). For this, we
need to use some additional Ruby gems.

Add the following gems to your `Gemfile`:

``` gemfile
gem 'jekyll-autoprefixer'
gem 'mini_racer'
```

`jekyll-autoprefixer` is the gem that will auto-prefix Bootstrap source
file. The autoprefixer uses JavaScript, because of that we need to use
\`mini<sub>racer</sub>\` to bridge between V8 JavaScript engine and
Ruby.

Add `jekyll-autoprefixer` to the `gems` property inside `_config.yml`.
Here is my gems configuration, you may use less or more gems than what I
use:

``` yaml
plugins:
  - jekyll-feed
  - jekyll-seo-tag
  - jekyll-sitemap
  - jekyll-autoprefixer
```
