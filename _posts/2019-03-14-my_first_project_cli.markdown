---
layout: post
title:      "My First Project: CLI"
date:       2019-03-14 21:46:21 +0000
permalink:  my_first_project_cli
---


After months of lessons and learning through tutorials, the moment had arrived. Our first project was given to us and it was definitely overwhelming at first. I knew that the project was for all the material we had learned up to this given point, but putting all of it together seemed daunting. 

Once that initial feeling of being nervous went away, I began to approach in the way we had approached all other labs. If I had gotten to this point then I knew I had the knowledge to complete my first project. I began by reading through all instructions. Then I read them again. I needed a clear understanding of what was being asked and I needed to start prioritizing tasks for myself. I then started to watch all of the instructional videos provided. These videos definitely made it easier since I was able to see multiple projects completed from start to finish. It also helped having different perspectives from each of the different instructor's projects. 

So, now I needed to find a website to scrape and base my project on. I really like sports, especially basketball, so I wanted to find a way to implement this into my project. I found several sites that had NBA news stories, but the majority had Javascript and so I could not use these to scrape for my CLI. I finally found one that was scrapable and was finally ready to get started. 

I started by creating my repo and writing out the details of my project. The first class I created was a story class that had attributes of a title, author, and content of the story. This was a fairly easy task. I knew also that there would be multiple stories that I would like to have returned to the user so I needed to create an array that would store all of the stories scraped from the website. 

The next thing I needed to do was scrape the data and have it successfully displayed the way I wanted. This was probably the most time consuming part of the project and it took a lot of trial and error. I set up nokogiri, open-uri, and pry in my files in order to be able to execute the scraper. I was able to scrape and return the title and author with no major issues. I had to change the selectors once or twice and then they were working perfectly. The content part of the story was the complete opposite and took me a day and half to get it to work as I wanted to. I had to use regex to remove unneceassary characters and spaces that kept coming up on my returned scrape. 

Last, but not least, I made the CLI class. This was the controller for the entire CLI and is what made everything flow to the user. I made a run method that used all the other methods I created in this class to execute all code. The other methods were made up of "if" and "else" statements. I refactored it several times to make it neat and to make sure it didn't break when a user would give a random input. 


Everything was running the way it should be and I published my CLI as a gem. The user is able to see the latest NBA stories from the website and select which one to read. The user can then either exit the application or read another story. Overall, the completion of this project was a success, and although it had ups and downs along the way, I am proud to say I created my first project !
