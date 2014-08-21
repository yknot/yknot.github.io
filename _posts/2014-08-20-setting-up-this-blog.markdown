---
title: Setting Up This Blog
layout: post
tags:
    - jekyll
    - blog

---

Motivation
=====

With the start of my new job as a Database Engineer and becoming a professional programmer of sorts you would think that coming home and doing more programming would not be first on my list. Well it turns out the opposite is true and the new position is what motivated me to look into tons of new projects. Now what better to document the successes and inevitable struggles of these than a blog. Well now that sounds like a project in itself.


Why Jekyll?
=====

When it comes to making a blog I looked around at a lot of different methods. Previously I had one hosted on Google\'s blogspot but I really thought that was more the cheaters way out. It did give me a lot of customization but I wanted to actually learn more about what I was creating in terms of HTML/CSS/JavaScript etc. But at the same time I didn\'t want to make it an arduous task to update the darn thing.

Enter Jekyll. You create the site from scratch just like you would any site but then you can automate the creation of static webpage posts so that you don\'t have to worry about it again. You can even write them in markdown, as I am right now!

The next step was how to host it. Luckily GitHub pages was available and runs Jekyll! Aren\'t the stars aligning so perfectly? With all these easy decisions made next was actually getting the website going, this would take a lot of work as I was pretty far out of my depth to begin with.


Starting with Jekyll
=====

The first steps of this process was to set up Jekyll. Because currently I am running windows it was painful. Lucky [this guide](https://help.github.com/articles/using-jekyll-with-pages "GitHub pages") exists and is super helpful. I did end up using bundler in order to try to future proof this process as well as using `bundle update` and having bundler for local builds is very nice.

From there to test it out I needed to set up an `index.html` and this first blog post to really make it official. I used some simple code stolen from Tom Preston-Warner\'s [Jekyll-based blog](http://tom.preston-werner.com/ 'Tom Preston-Werner') to generate a list of my posts on the index page.


{% highlight html %}
{% raw %}
{% for post in site.posts %}
  <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
{% endraw %}
{% endhighlight %}

This made a simple list of my posts with the date and title. Again as basic as possible just to get a feel for what this would look like.

Finally for this post I used markdown as stated above. I tried out my YAML front matter (lack of) skills to tag and title the post and get it up there for the world to see, because if you haven\'t realized this is a long-winded \"Hello World!\" test.

Side Note(s)
----

The code above took me through one of my first struggles with markdown and Liquid tags. This was because Liquid still wanted to evaluate the tag above, while I wanted it to be in a code block. Turns out built-in to Jekyll is a tag: `{{ "{% raw " }}%}` that starts a un-evaluated block of text. You can then use `{{ "{% endraw " }}%}` to end it.

After that I also had to figure out how to get syntax highlighting working because I\'m too OCD about my code not highlighting. After following that rabbit hole I had a new `.css` file and a `_layouts` folder. Basically I needed a `syntax.css` file, created by Pygments and a layout `post.html` to call it.

Next Steps
=====

If you are viewing the site in it\'s current form I applaud you because it hurts my eyes to look at. But it was necessary to get these steps done so I can move on the the much more difficult designing part of this task. Some of the next steps.

* Making a better home page
* Making a better post page
* Create a reamed for GitHub
* Learn and use Sass

And by next time I post hopefully it will be on a much cleaner looking site!
