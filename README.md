# eCHT online research community

This file contains information about the eCHT website and how to edit it. It's written as more of a "user's guide" than a technical document.

Last updated: September 2026 by Maxine Calle





# Basic Info

The website is based off of the "academic websites" template, which you can see more about here: https://academicpages.github.io/

The template has been heavily edited for this website, but the basic contents of the repository are the same. In particular, you can follow the instructions they give to run the website locally. 


## Files and folders

1. _config.yml contains settings that affect the entire site, like the url and site title. Aside from the basic site settings, everything is blank.

2. _data > navigation.yml has the various navigation menus that appear on the site. The main menu (which would appear horizontally at the top of the site) is currently blank; left_nav is the menu that appears in the left sidebar.

3. _includes has the different html files used to build the site. More on that below.

4. _layouts has different html files for page layout templates. I've only used "default" throughout the site, but you could get fancier if you want to.

5. _pages has the different html files that correspond to actual pages that make up the website. More on that below.

6. _sass has scss files that customize how things look on the website. More on that below.

7. _site I think is automatically generated? I never touch anything in here.

8. _assets was included in the template. I never touch anything in here.

9. files contains all the pdfs that are linked in the website, e.g. talk notes and slides.

10. Gemfile and Gemfile.lock are there to help you run the site locally with Jekyll.

11. images contains all the images used on the website, e.g. the logo and favicon.

12. index.md is the markdown file for the homepage of the website.

13. README.md is this file :)






#Editing the website



## How to make a new page

Let's say you want to make a new page on the website, for a Course on Topic X. What should you do?

The easiest thing to do is to go to _pages > courses and make a copy of one of the html files there. You should then change the file name to be something like 'course-on-topic-x-date' (e.g. 'course-on-stable-homotopy-theory-fall-26'). 

When you open the html file, you should edit the top to look something like this:

---
permalink: /course-on-topic-x-date/
title: "eCHT Course on X"
redirect_from: 
  - "/course-on-topic-X.html"
layout: default
sidebar:
  nav: "left_nav"
---

It's important that this block is surrounded on either side by "---". The first line says what the url for the page should be, in this case, it will be accessible at https://echtorc.github.io/course-on-topic-x-date/. Also, if you want to link to this webpage from another page, you'd say <a href="/course-on-topic-x-date/">hyperlink text</a> (versus <a href="https://echtorc.github.io/course-on-topic-x-date/">hyperlink text</a>). 

Now, the rest of the page can be edited with html, and the whole thing should be encased in

<div class="page">
...(content)...
</div>

If you've copy-pasted the html file from a pre-existing one, the basic layout should already be there and you can just edit the text as you wish. You can also copy-paste other elements from different html files in the _pages folder, if you see something you like on another page.



## How to make things look different

If you want to change the aesthetics of the website, or add new elements, there are two folders that you should go to: _includes and _sass. The former contains the html files for the basic aspects of the website (e.g. footer, header, masthead, sidebar) and the latter contains the scss files that govern how these things look.

Here are the most basic things you might want to edit:

- Colors, fonts, etc: Go to _sass. The files _syntax.scss and _themes.scss govern things like typography. If you go to the folder theme, you'll find different scss files that govern the colors for the website. Currently the one that's used is _contrast (both light and dark, depending on what the user's computer dictates. There is an option to make light/dark mode "toggle" (see the masthead files) but it's not currently in use). 

- Buttons, lists, the sidebar menu, footer, etc: Go to _sass > layout. The files in here govern how specific elements of the website look. For example, say you wanted to change what happens when you hover over a link in the sidebar. You should go to the file _navigation.scss (it might be worth looking in _sidebar.scss as well) and edit the code in the "Navigation list" section.



## I'm confused, help!

Yeah, honestly, the best advice I can give is to poke around in the other files and try different things to see what works. Google is also pretty good for basic html things, and probably AI / LLMs are much better at anything coding-related than I am. But you can also always reach out to me (Maxine Calle) and I can do my best to help. You've got this!
