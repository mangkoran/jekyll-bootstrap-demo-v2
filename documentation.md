---
author: Afiq Nazrie Rabbani
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

## Jekyll

Make sure you already have local Jekyll website. I won't explain how to
setup a Jekyll website from scratch here, as it already covered in
[Jekyll's own
tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/).

## Bootstrap

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
