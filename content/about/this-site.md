+++
title = "This Site"
description = "This Site Page"
draft = false   
+++

# About this site

## History

In the past, I've hosted this site using a broad array of technologies. It has been hosted in Azure and Amazon Web Services, as well as on my own private server. It has also gone through a transformation of front-end technologies, including Aurelia, Bootstrap, jQuery, cujo.js, and Dojo Toolkit. The design and HTML / CSS itself has gone through a life-cycle of HTML 4 to 5, and CSS to LESS to SASS.

## Why I chose Hugo, Foundation, and GitHub Pages

At first I wanted to move the site from Aurelia to Angular 2, so that I could get more experience with Angular. After much thought and consideration, I concluded that there wouldn't really be anything "app"-like about this site. Its intent is focused more on conveying information and helping others discover details about less-widely / improperly covered topics. I have other personal projects in my pipeline that are better suited to fit the Angular / SPA category, so why make this project require extra maintenance, carry more overhead, and cost more to host in the end?

Once I established that I didn't want to be bothered with any complexity for this site, I started hunting around for static site generators. I've heard plenty about them in the past, but have never actually used one myself. I happened to be discussing GO with some friends at the time, so I literally searched for "go based site generator", and low-and-behold, I found HUGO, which has much priase and use across the web. I decided, what the hell, why not give it a shot? Turns out, for my current use-case, this thing is brilliant!

Next came the UI Design. I've built a lot of web applications over the years, and have always stuck with the tried-and-true Bootstrap UI. However, for this project, I wanted to try something different and see what life was like outside of Bootstrap these days. To accomplish this, I did about an hour of Googling and comparing / contrasting all sorts of projects out there. I ended up settling on Foundation UI in the end. This framework is extremely well documented, has awesome example galleries to get your design gears turning, and the community is fantastic! They also offer a set of styles specific to Email Templates, so that you don't have to think through all of the inline styles and tables you need for most email clients to load properly.

## The Process

I started by learning how Hugo functions OOTB with some sample templates and their recommended "Robust" theme. Once through the Quick Start and poking through all of the documentation to get an idea of what it's capabilities are, and whether it would do what I needed, I decided the next step was to start working on the design. Wanting to use Foundation, I decided to poke around the web for any Hugo / Foundation integrations, and low-and-behold some already existed. I pulled down a few different ones, and ended up deciding upon the [Hugo Foundation v6 Blog](http://themes.gohugo.io/hugo-theme-foundation6/) theme to base my site off of. After about an hour, however, I quickly found myself having different requirements than this theme, and so I ported what was useful and started my own Hugo Theme called hugo-theme-jgarfield.

Now that Hugo and Foundation were integrated properly, I could start the site layout and design process.
