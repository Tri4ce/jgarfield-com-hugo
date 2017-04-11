+++
date = "2017-04-08T13:27:28+05:00"
draft = false
title = "Everybody Loves Hugo (insert LOST opening sound)"

+++

# Background

In order to create this site, I went through multiple iterations of deciding what tech stack I wanted to use. I went through a lot of considerations, such as...

* Do I want to spend money on the site right now?
* Do I need a database to accomplish my goals?
* Will I need a lot of storage over-time for images and other related items?
* What is available now that wasn't available last time I built this site?
* Is the site worth a full application-size build-out, with full APIs and all that jazz?
* Do I want support for Comments, Analytics, and other packages to help with feedback and metrics?

I looked at Angular (2 through 4) and Aurelia for the front-end. I looked at the state of UI frameworks like Bootstrap, Foundation, and some others. I thought about .NET vs. straight-up JS on node. I thought about all kinds of different things that I'm used to churning through before starting to build something new out.

In the end I backed away from these sorts of thoughts, and focused on what the purpose of the site actually was. I don't need to have a $1000/mo Cloud bill for a site that is just barely going live, nor do I need a database for static articles and information I type maybe once or twice a week and can upload from pretty much anywhere these days. I don't need to be pushing down 1MB client-payloads just to have some jazzy widget look shiny, when my viewers are most likely going to be here to read and learn about certain topics. I do however want analytics and the ability to create conversation and allow constructive feedback on topics, so that I can adjust and correct any mistakes or mis-interpretations I may post over time.

In the end, I decided to start simple for once and if the site gains popularity then I'll expand into all the crazy whiz-bang stuff I'm used to implementing in full-blown applications.

# Static Site Generators

Static site generators are the exact opposite of what we're used to with database-backed, dynamically-rendered, real-time sites and applications. You write your content, configure your markup and templates to smash against the content, and then you run a process to render all of your items into static content. This allows you to host your site anywhere you can serve files to the world without worry about a bunch of underlying infrastructure setup.

There are draw-backs of-course. For-instance, I can't provide a remote administration page to allow editing of the site on-the-fly...I have to create a new markdown file per article or page, re-run the generation process, and upload the new / changed files to the repository they're stored in. I can't use things like Session-state if I decide it's needed for something important down the road (though we should try and stray away from touching Session these days, but that's another article).

With all of that in-mind, I started my search and evaluation of what's currently out there. I decided to eventually see if there was a "GO"-based static site generator, since I just happened to be talking about GO with some friends at the time and decided "Ah, what the hell, I wonder..." That's where I found, and fell in love with HUGO. It meets all of my current requirements for this site, and has a brilliant way of working with, and customizing pretty much any part of the software itself. On-top of that, it offers support for multiple templating engines and lets you create custom themes to radically change how your site looks and functions. Its domain is well thought-through, and the documentation is fantastic (at least I've been able to find answers to all my questions so far). There's also a fantastic community around it offering all sorts of great themes and templates to learn and grow from, helping spark ideas and new designs.

# Where to start?

Never having used a static-site generator before, I spent a day or two deciding what the best plan of attack was to not only take-in what HUGO had to offer, but also how to convey my content and structure the site design to accomodate it. These are my own recommendations on how to proceed, and can obviously be done in whatever is comfortable to you, but this is what worked for me...

## Plan and Draft

Like any site or application, it will be easiest to start with a plan. Think about what you want your site to accomplish...what is the intention of spending your time doing any of this? Is it to provide documentation for a product? Is it a landing page to sell a product? Are you building a blog? Are you building a set of supporting pages? Is it a mix of both? What value do you plan to get from this?

Write-up some content for your pages, articles, etc. in something as simple as Notepad and start to get a feel for where the content should reside and what is attributed to it.

## Design

Once you understand what it is you want to host for content, and what that content may be, now you can start thinking about your design finally. I tried going about it the opposite way, doing design first, and then as I generated more-and-more content, I kept going "Ah, crap, now I need to tweak this in the UI Design, again, to fit this damn thing in here somehow..."

Just like development any other site with HTML / CSS / JavaScript, this is the same old game. I chose to roll with Foundation over Bootstrap for my UI framework, sheerly because I'm tired of using Bootstrap for everything known to man, and I wanted to see what life elsewhere was like when it came to design. The choice is ultimately yours...If you feel comfortable with Bootstrap, then go for it! Neither is better or worse, as they both solve their own sets of problems.

## Get Hugo up and running

Head over to [Hugo's documentation](https://gohugo.io/overview/introduction/), and follow the [Quick-Start](https://gohugo.io/overview/quickstart/) up to step #9. That should get you far enough to understand some basics and have a running Hugo instance to play around with.

## Pick or Create a Theme

Once you're comfortable running Hugo, have some design concepts in-mind, and have written some content to start sculpting, you can now start thinking about a Theme for Hugo. The Quick-Start shows you the Robust and Bleak themes, but there are many more available in the [Themes Showcase](http://themes.gohugo.io/). There are themes readily available for the [Bootstrap 4 Blog](http://themes.gohugo.io/hugo-theme-bootstrap4-blog/) and [Foundation 6 Blog](http://themes.gohugo.io/hugo-theme-foundation6/) provided by the Hugo community if you want to hit the ground-running extremely fast.

I personally needed a little more customization than just being able to include a CSS / UI framework, so I decided to spin-off my own theme that integrates Foundation 6 and allows me to host different types of pages and work with different [Archetypes](https://gohugo.io/content/archetypes/) / [Front Matter](https://gohugo.io/content/front-matter/).

