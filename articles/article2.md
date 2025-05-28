---
title: kilosite
url: kilosite
category: ★
date: 23rd May, 2025
---

# {{ title }} <span>// {{ date }}</span>
### <span>the static site generator to rule them all!</span>

For the past few months I've been trying to gain my programming independence from Unity by creating new projects outside of my comfort zone, this is the tale of one such project.  

I was bored and trying to think of something fun that could be completed relatively quickly when I thought it'd be cool to have a corner of the internet to write about whatever I wanted, whenever I wanted.  
I knew I needed an area to host this place, I could've utilised [neocities](https://neocities.org/) or [spacehey](https://spacehey.com/)[^1] however I thought it'd be more engaging to create my own site and a static site generator alongside it. Coming from knowing nothing I did a bit of research.[^2] It looked like Python or JavaScript were languages people liked to use when making something like this, and although I was trying to challenge myself, I like C# too much to depart from it just yet. It also had some nice nuget packages I could use to my advantage when working with something like this.

I came up with kilosite's name quite quickly, "kilo" meaning thousand, combined with site to create "thousand site" which represents one of it's core values of being able to be used for multiple purposes to create whatever the user wants a thousand times over.

### Implementation
FYI I've never used any other static site generators prior to this. I know the names of some that exist, like Jekyll, Hugo and Hexo but that's as far as my knowledge goes. Saying that, I did know what I wanted the base implementation to be:

```shell
 $ ./kilosite.exe <create | newpost | build> <project_name>
 ```

These are the only commands that I think I'd need, something to create a new blog, something to create a templated article and something to build everything to a html, website-ready state.

### Creating a blog
This was the part I enjoyed the most, I spent some time creating a template site, provided to kilosite which is used as the basis for each new project. My knowledge with web-dev in general is pretty limited however I took a lot of reference from my neocities page,[^3] creating a layout that's clean, responds well on mobile screens and is easy for new users to manipulate and build their blogs off of. 

Each new article is generated with some YAML tags; an article name, url, data and category alongside some headers and lorem ipsum to pad out the page. Users can then fill out this config with whatever key and values they want and add correlating `{{{ key }}}` tags in their markdown which kilosite will then scan and automatically replace.

### Looking back
Now I know slightly more what I'm doing, if I were to rewrite kilosite I'd probably allow for a few changes, the way I handle YAML is slightly messy and involves a lot of back and forth. I'd probably scan through all the articles, storing their data earlier and then handling everything that's needed. It'd also be interesting to add support for extensions. I noticed this when I added code highlighting support which allows for nice things 

```csharp
// like this:
private static void Main()
{
    Console.WriteLine("#kilositerulezz");
}
```

It added a bit of untidy code in the main file which I didn't like too much, I'd rather have a bunch of 'em and loop through each one executing different functions. This could nicely tie in to a plan I had for an overall YAML config file which would allow for extra customization, and the enabling/disabling of different extensions.  
Also probably should have used timestamps instead of strings for article dates which would allow for further customization. ;^)

Now kilosite is in a MVP state, I'm happy with what it became although I'm not sure how much more I'll work on it, but that's the beauty of open-source. If anyone wants to check out the source and modify it feel free to have a gander here: [https://github.com/Murgn/kilosite](https://github.com/Murgn/kilosite)

Thanks for reading!

[^1]: [spacehey](https://spacehey.com/) is a "retro social network" influenced by the myspace era of socialising which actually does have a neat blogging feature.

[^2]: [Build Your Own Static Site Generator](https://blog.hamaluik.ca/posts/build-your-own-static-site-generator/), [Building a Static Site Generator in 3 steps](https://dev.to/devmount/building-a-static-site-generator-in-3-steps-72e)

[^3]: My neocities page wouldn't be anything without [sadgrl.online](https://goblin-heart.net/sadgrl). Awesome stuff to help beginners with web-dev!