# jekyll-bootstrap-blog

A theme for Jekyll to build a personal blog, based on [Bootstrap 3](http://getbootstrap.com/), [Font Awesome](http://fortawesome.github.io/Font-Awesome/) and [jQuery](http://jquery.com/).  

* Clean
* Responsive
* Mobile First
* Syntax Highlighting 
* Jekyll 3 Supported
* SEO Friendly

## Screenshots

## Demo

You can see the theme running on [my blog](http://www.waylau.com/).

<!-- more -->

## Usage

### Installation

- Start by cloning the github repo using `git clone`
- You must have jekyll installed to run this, use `gem install jekyll` for installing it
- Use `jekyll serve` to run the site live.

### Configration

```
# Site settings
title: 
name: 
url: 
email: 
description: 
baseurl: 
twitter_username: 
github_username:  
weibo_username: 
facebook_username: 
duoshuo_username: 
baidushare_id: 
baidutongji_id: 
rss_url: "/feed.xml"
logo_image: "/images/logo.png"
# Build settings
gems: [jekyll-paginate]
markdown: rdiscount
highlighter: pygments
permalink: /:title/
paginate: 8
paginate_path: page/:num
```

### Creating Posts

For creating posts add this snippet in front of your post's markdown file:

```
---
layout: post
title:  "your title here"
tags: your tags here
class: post
---
```

Add content below this and save the post in `_posts` directory (you will have to create it).

## License

Feel free to fork and contribute to the project, just create a pull request.

Open sourced under [MIT License](LICENSE) 

