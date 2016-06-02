---
title: Jupyter Notebook – UCOSP 2016 – Recap
author: Adam Wong
layout: post
categories:
  - Uncategorized
---


-- Adam Wong

Hey everyone, now that I am halfway through my UCOSP project, I would like to take some time to reflect and share some of my experiences.  I have had the honor of working with three other talented students from the University of British Columbia as well as with two friendly and intelligent Mozilla employees in the Jupyter Notebook project. 
 
So what exactly is a Jupyter Notebook, and why should you really care?  
Well, the Jupyter Notebook is an electronic document that can contain Python code as well as flexible human-readable text such as paragraphs, comments, figures, equations, etc.  The code within these documents can be executed and analyzed.

One of the main challenges I have overcome during this experience so far is learning to function within and adapting to the somewhat distributed working environment.  Previous assignments I’ve worked on were with a local team of developers usually in person.  People could be called or messaged and then ideas could be bounced off each other on whiteboards, over a cup of coffee or even on the same computer.

This new approach has team members all over Canada working together (British Columbia, Ontario, Nova Scotia) as well as internationally (England).  The first and most obvious obstacle is that with each different area, there is a different time zone.  When scheduling meetings or Skype calls, it is common to find a reasonable time, taking into consideration the up-to-nine-hour time difference.  Outside of these scheduled weekly meetings, we often find ourselves communicating via IRC or Skype, both platforms which I am familiar with.

The Jupyter Project uses many different technologies – some I have used before and others not so much.  The languages include JavaScript and Python – the former I have used for mere hours (but am currently learning) and the latter I have not used since my first year.  Ramping up was a significant challenge, as the time spent studying syntax and language structure put me even further behind my teammates.  I often felt like the least useful member of the team as the other students were much better versed in the aforementioned technologies.  In spite of this, however, after the initial ramping period I felt much more comfortable working on this project.

You might be asking, “Well I know what the notebooks are, so what is your team doing?”  Our team is currently working on various add-ons for the Jupyter Notebook – extensions that will be released open-source and accessible to the public.

The first project was a simple extension that would allow Jupyter Notebook files to be uploaded to GitHub’s gist platform.  Specifically, the content from the Notebook (code and text) would be uploaded to the authenticated user’s GitHub account via OAuth2 for safe keeping.  During our Toronto code sprint in January, we laid down the foundation for this extension.  The main goal for the meeting was to successfully implement a new button in the JavaScript front-end, and to link it to the Python back-end server (where the Jupyter Notebook was running) for processing.  Knowing I had limited knowledge in JavaScript at the time, I took it upon myself to handle much of the back-end Python code instead.  As I had previously studied OAuth2 in a Computer Security class at my university (ECE568), most of the APIs were familiar.  For those that don’t know, OAuth2 is a protocol used by a client (our server acts as a client to GitHub) and a server (the GitHub server offering the OAuth2 service) to allow secure access to an authenticated user’s private information.  Specifically, the user is redirected to GitHub, where they specify which services to allow us (the client) to use.  After authentication, GitHub will then comply with our requests (in this case, uploading the notebook contents as a Gist) on the user’s behalf.  After sifting through the many pages of the GitHub API documentation, I was able to independently implement the handshaking and authentication process between GitHub and our server.  However, I got stuck with formatting the notebook content which was formatted in JSON.  After spending several hours trying to figure out why my GitHub call would return with a ‘404’ error, I was at a loss.  At that point, knowing nothing about JavaScript or JSON, sought out help from my teammates who were eager to jump in and lend a hand.  Turns out there is a bizarre function call in JavaScript called “JSON.stringify” that ended up solving my issue.  With the whole team working together, we were able to get the extension out and it is now available via ‘pip’ or at https://github.com/mozilla/jupyter-notebook-gist.

Our second extension was an add-on for Apache Spark integration.  Apache Spark is a framework for cluster computing – a system where distributed machines can be used together to perform large computations.  It is very useful when data processing, something that Mozilla would definitely use to process large volumes of Firefox usage information.  If, within the Jupyter Notebook, an Apache Spark job was ongoing, we wanted to provide a progress bar.  Unfortunately this task had just gotten off the ground as the university’s Reading Week began, and I had already made plans to be out of the country.  I kept tabs on the progress (IRC) during that week, but sadly did not have time to make significant contributions.  Upon return, I tried to quickly ramp up, but to little avail. Apache Spark does not like to run on native Windows, so I installed VirtualBox with Ubuntu 15.04 to get it working.  Only after much debugging and installing, did I realize that all the tasks for the Apache project were taken and/or in progress by another team member.  The feeling of insignificance returned, but after expressing my concern to the Mozilla team lead, he mentioned that it might be better to get started on the next project which would soon be fleshed out and discussed.  At the end of our meeting, he mentioned someone around the office was looking for C++ assistance, which is my area of expertise so I will definitely follow up on that as soon as possible. 
 
That pretty much sums up where I am now at currently in the project.  I definitely enjoy working with everyone, and my mentors are very intelligent, open and approachable individuals.  I feel like working in an open-source environment provides me with unrestricted access to the world’s knowledge, and even someone like myself can share everything that I have learned.  Being able to see people happily using what I have worked on is such an amazing pleasure and honor for me, as a software developer.  I hope that I will be able to continue to make a difference both in the Jupyter Notebook project, and in future endeavours.

While UCOSP will soon come to a close, the journey into the world of open-source is a never ending road of exploration, learning and sharing.  Mozilla is a wonderful company with many wonderful people.  It would be a dream to be given opportunities to work with them in the future.