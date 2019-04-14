---
layout: post
title:      "Happy Birthday to All!"
date:       2019-04-13 16:55:11 -0400
permalink:  happy_birthday_to_all
---

## My Ruby CLI Gem Project: The Birthday Gem 




### Overview 

My final Ruby CLI Gem Project is the Birthday Gem. It scrapes ~fun facts~ on birthdays between 1901 and 2018, which users can access through a CLI. The repository for my project can be found at: https://github.com/ktbliz/birthday

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

The code for each of these classes is in its own .rb file within the "lib" directory. At a high level, these classes are each responsible for the following: 

* **CommandLineInterface:** This class contains the functions that will be executed via the "run.rb" executable file in the "bin" directory. These functions include: welcoming the user, getting a birthday from the user, validating the given birthday, creating instances of the other three classes using the given birthday, and pulling information on the given birthday from the two "Scraper" classes. 
* **Birthday:** This class accepts a valid birthday string and creates the Birthday instance that will be used by both the "Scraper" classes. 
* **BirthdayStatsScraper:** This class accepts a Birthday instance and scrapes data from My Birthday Ninja on the given birthday (providing birthday fun facts #1-5). This class pulls information from the Birthday instance and interpolates that information into a My Birthday Ninja url string in order to scrape the correct web page. 
* **FamousBirthdayScraper:** Similar to the BirthdayStatsScraper, this class accepts a Birthday instance and scrapes data from Who 2 Biographies on the given birthday (providing birthday fun fact #6 aka famous people also born on the given birthday). This class pulls information from the Birthday instance and interpolates that information into a Who 2 Biographes url string in order to scrape the correct web page.


### User Experience 

Users interact with the Birthday gem by running "bin/run.rb", which creates a new instance of the CommandLineInterface class and calls the #run method on that instance. The #run method, in turn, calls all the CommandLineInterface instance methods that are relevant to the user's interaction with the gem. 

The following link contains a short video walkthrough of how a user would interact with the Birthday gem: 
* https://drive.google.com/file/d/1AeA-h2VwV7J885oJbN1pbNmeP7wDp0s1/view



### Reflections 

Finally, as a programming student, a few reflections on the learning experience of this project: 

* Most of our labs that deal with object relationships make a lot of use of class methods, especially class methods that store all instances of the class. I didn't really see a big need for these in my program, so the initial (pre-review) version doesn't have them. In this CLI gem, users enter their birthday and then can access a menu of information on their birthday. They can then enter another birthday and access the same menu of information for that birthday. But, at least the way the menu is currently set-up, there is no way (or need that I can see) to access previously entered birthdays without just re-entering the birthday. This did get me thinking about how to set up programs in a way that their functionality can easily be extended. And ways in which I have or have not built my program to allow this. I think the Birthday gem serves its purpose well, but I definitely have plenty to learn on this subject. 
* Learning how to structure the files in my gems, set up all the "require" / "require_relative" lines and gems, and follow all the right conventions was probably the newest part for me. It gave me an appreciation for how I've been in a bubble of pure Ruby coding. 
* Validating that users (a) enter a birthday in the correct format and (b) enter a valid birthday was an unexpected pinchpoint. In retrospect this makes perfect sense because you can't access the rest of the program without entering a valid birthday, but alas I was more focused on the scarping at the beginning. The code that validates the entered birthday is in the #get-birthday and #birth_date_validator methods within the CommandLineInterface Class. This code is also copied below, suggestions for improvement are welcome!


```
  def get_birthday 
    
    until @birth_date != nil
    
      birth_date = gets.strip
      
      if birth_date_validator(birth_date) && birth_date.match(/\A[01][0-9]\W[0-3][0-9]\W[12][0-9]{3}\z/) 
        @birth_date = birth_date 
      elsif birth_date.match(/\A[01][0-9]\W[0-3][0-9]\W[12][0-9]{3}\z/) 
        puts "The birthday you've entered may not be valid. Note that the Birthday gem only covers birthdays between 1901 and 2018.  Please re-enter your birthday in the following format: MM/DD/YYYY."
      else 
        puts "Please re-enter your birthday in the following format: MM/DD/YYYY"
      end
      
    end 
    
  end
  

  
  def birth_date_validator(birth_date)
    
    date_array = birth_date.split("/")
    month = date_array[0].to_i
    day = date_array[1].to_i
    year = date_array[2].to_i
    
    month > 0 && month <= 12 ? m = true : m = false 
    day > 0 && day <= 31 ? d = true : d = false 
    year >= 1901 && year <= 2018 ? y = true : y = false 
    
    months31 = [1, 3, 5, 7, 8, 10, 12]
   
    if day == 31
      months31.include?(month) ? test31 = true : test31 = false 
    else 
      test31 = true 
    end 
      
    if month == 2 
      day <= 29 ? feb_test = true : feb_test = false 
    else 
      feb_test = true
    end 
    
    if month == 2 && day == 29
      year % 4 == 0 ? leap_test = true : leap_test = false
    else
      leap_test = true
    end 
    
    true if m && d && y && test31 && feb_test && leap_test
    
  end 

```




