---
layout: post
title:  "Building my first app - The CLI Data Gem Project"
date:   2017-01-25 16:57:50 -0500
---


To put it lightly, I was a little overwhelmed when I first started this lab. I think it was the lack of tests to run. I love the tests. They tell me exactly what my program needs to do and I can take it one step at a time. Without that, I didn't know where to start! "Start by writing tests", you say. Touche - I didn't write any tests because I was anxious to jump in and feel like I was making progress. This probably wasn't the best method, but thanks to the resources attached to the lab, it didn't go totally awry. 

![](https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcReg70H0mjcP4vKhp-aK2vAVsbzvVL1xfFOkZoba2fnjhXj3qiBRg)

My initial idea was extremely complicated - I wanted to be able to give the user a choice of 6 different climbing locations, and then the program would pull videos from Vimeo and Youtube and present them in a chronological list of videos for the location. Then the user could choose a video to get more information about. I also wanted the user to be able to specify how far back in the search history they wanted to go for videos. I quickly realized this was too complex. I had so many questions!
- How do I get videos from multiple pages on Youtube and Vimeo?
- Why can't I scrape Vimeo (turns out the Vimeo API requires you to register your app before pulling data)
- How do I change the text date from the scraper into a date I can sort by?
- WHAT AM I DOING?!?

Haha. Luckily, a discussion with my instructor showed me that I was getting in a little over my head. Start small! You can always improve on your ideas later. 

In the end, I made an app that could pull the latest 20 videos from youtube for each of the climbing locations and display them in chronological order. Then the user could choose a video from the list to get more information. I'm happy with it! I feel more confident about my ability to get multiple classes to collaborate and have a better understanding about separating my methods into the right classes. By the end, I felt really good about reading error messages, and working through them one by one to get my program to work. 

I ran into a second set of issues when I tried to publish my gem to rubygems.org. My app worked fine when I ran my bin file, but when I installed my gem from the site, I was getting an Uninitialized Constant (NameError) for my module name - SeClimbingVideos. After some trial and error, I realized I had an issue declaring the module name twice because of the version.rb file set up by Bundlr (which is how I started my gem). I ended up scrapping my config/environment.rb file and embracing the file structure made by Bundlr, which expects that information in a different file![](http://). I also had to define a Class Constant with all of my locations within my CLI. I orginally had this constant defined in my module, which was inherited into the CLI. The constant was only used in the CLI file, so I moved it over. I thought the other way was prettier, but I'd rather work within the structure I have set up instead of trying to fight against it.
### TAKEAWAYS:

- Use your resources! They really help.
- Start simple - you can always make things more complex later. 
- There are multiple ways to code everything! And this is your first time trying to figure that part out, so give yourself some slack and reach out for help if you need it. 
- Understand your Gemspec (especially the files and executables portion) - I found it easier to understand how Bundlr set this up and work around it. I ran into issues when I tried to change the file required to run the app instead of working with the Bundlr template. 

**CHECK OUT MY CODE HERE:** [https://github.com/liahwallace1/se-climbing-videos-cli-app](https://github.com/liahwallace1/se-climbing-videos-cli-app)

**DOWNLOAD MY GEM HERE:** [https://rubygems.org/gems/se_climbing_videos](https://rubygems.org/gems/se_climbing_videos)
