---
layout: post
title:      "Happy Birthday to All!"
date:       2019-04-13 16:55:11 -0400
permalink:  happy_birthday_to_all
---

## My Ruby CLI Gem Project: The Birthday Gem 




### Overview 

My final Ruby CLI Gem Project is the Birthday Gem. It scrapes fun facts on birthdays between 1901 and 2018, which users can access through a CLI. The repository for my project can be found at: https://github.com/ktbliz/birthday

The birthday fun facts are scraped from two websites: 

* My Birthday Ninja (https://mybirthday.ninja/)
* Who2 Biographies (https://www.who2.com/)

The fun facts include: 

1. Number of days until your next birthday
2. Number of days since you've been born
3. Your birth month gemstone
4. Your western zodiac sign
5. Your eastern zodiac sign
6.  Famous people who share your birthday


### Gem Structure

The core of the code for my gem is organized into four classes: 

* CommandLineInterface
* Birthday
* BirthdayStatsScraper
* FamousBirthdayScraper

The code for each of these classes is in a .rb file that shares that class name within the "lib" directory. At a high level, these classes are each responsible for the following: 

* **CommandLineInterface:** This class contains the functions that will be executed via the "run.rb" executable file in the "bin" directory. These functions include: welcoming the user, getting a birthday from the user, validating the birthday, creating instances of the other three classes with that birthday, and pulling information on the given birthday from the two "Scraper" classes. 
* **Birthday:** This class accepts a valid birthday string and creates the Birthday instance that will be used by both the "Scraper" classes. 
* **BirthdayStatsScraper:** This class accepts a Birthday instance and scrapes data from My Birthday Ninja on the given birthday (providing birthday fun facts #1-5). This class pulls information from the Birthday instance and interpolates that information into a My Birthday Ninja url string in order to scrape the correct web page. 
* **FamousBirthdayScraper:** Similar to the BirthdayStatsScraper, this class accepts a Birthday instance and scrapes data from Who 2 Biographies on the given birthday (providing birthday fun fact #6 aka famous people also born on the given birthday). This class pulls information from the Birthday instance and interpolates that information into a Who 2 Biographes url string in order to scrape the correct web page.

