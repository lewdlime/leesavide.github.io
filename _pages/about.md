---
layout: page
title: "About Site"
permalink: /about-mdl/
---
### About abcjs:

# abcjs

**javascript for rendering abc music notation**

[abcjs Home page](http://abcjs.net)

[API Documentation](https://github.com/paulrosen/abcjs/blob/master/api.md)

[Support of the ABC standard](https://github.com/paulrosen/abcjs/blob/master/abc-notation.md)

This library makes it easy to incorporate **sheet music** into your **websites**. You can also turn visible **ABC** text into sheet music on websites that you don't own using a greasemonkey script, or change your own website that contains ABC text with no other changes than the addition of this javascript file.

**NOTE: We are changing the release license to the MIT License, effective immediately. Let us know if this causes any problems, but we're hoping that it solves some. Our goal is that you can use this library in a convenient way, as long as you give us credit for it.**

License: [The MIT License (MIT)](http://opensource.org/licenses/MIT)

### About jekyll-mdl:

###### A Jekyll theme based in Google Material Design Lite library.

This is the base Jekyll Material Design Lite theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](http://jekyllrb.com/)

You can find the source code for the Jekyll MDL theme at: [github.com/gdg-managua/jekyll-mdl](https://github.com/gdg-managua/jekyll-mdl)

You can find the source code for Jekyll at [github.com/jekyll/jekyll](https://github.com/jekyll/jekyll)

###### Sites using jekyll-mdl

If you are using this cool jekyll theme, please open an issue or fork the project, add your site to the list and send a pull request, we will be happy to know where the theme are using.

[fandekasp.github.io](http://fandekasp.github.io/)

###### Custom Themes

If you don't want the default site colors, you can create custom themes for the site in the [mdl theme creator](http://www.getmdl.io/customize/index.html). The site will create a custom css, something like this:

     <link rel="stylesheet" href="https://storage.googleapis.com/code.getmdl.io/1.0.0/material.teal-green.min.css" />

Now add this in the _includes/head.html file, under the main css and enjoy your new theme.

###### Post Options

All the post, require an image and maybe an author, the image are used in the cards and the autor used for the footer in the cards. For use the images and author, just add a new key in the post config, something like this:

    ---
    layout: post
    title:  "Welcome to jekyll-mdl"
    date:   2015-07-11 11:34:20
    categories: jekyll
    image: http://www.wchs4pets.org/wp-content/uploads/2015/03/cat_1-jpg.jpg
    author: Google Developers Group Managua
    ---

###### Layout Configuration
You can setup 4 types of layout

    - Fixed Nav + Simple Card Grid
    - Fixed Nav + Highlight Post + Card Grid
    - Drawer Nav + Simple Card Grid
    - Drawer Nav + Highlight Post + Card Grid

For using this in the [_config.yml](https://github.com/gdg-managua/jekyll-mdl/blob/master/_config.yml) select the type of layout, rebuild the website and voilà :smile:

###### Contributing
If you want to contribute to this project, please read the [CONTRIBUTING](https://github.com/gdg-managua/jekyll-mdl/blob/master/CONTRIBUTING.md) file and perform the following steps

    # Fork this repository
    # Clone your fork
    jekyll serve --watch

    git checkout -b feature_branch
    # Implement your feature and tests
    git add . && git commit
    git push -u origin feature_branch
    # Send a pull request for your feature branch

###### Team
[![Oscar Cortez](https://avatars.githubusercontent.com/u/2553459?v=3&s=100)](http://github.com/oscarmcm)
[![Byron Corrales](https://avatars.githubusercontent.com/u/99616?v=3&s=100)](https://github.com/byroncorrales)

###### License
Licensed under the Apache 2.0 license.

See the [LICENSE](https://github.com/leesavide/leesavide.github.io/blob/master/LICENSE) file for more details.

Copyright © 2015 [Google Developers Group Managua](http://www.gdgmanagua.org).
