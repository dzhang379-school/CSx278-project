# Opportunity Knocks

At a school like Vanderbilt, there are always a large number of great opportunities circulating around, many of which get filled by talented, well-suited students. However, there are also a lot of opportunities which go unfilled, or don't get as many candidates as they want. At the same time, there are always students on campus who are looking for more things to do - another job, club, organization, or internship to be a part of - but they might not hear about some of the more less popular/well known opportunities on campus.

The result is that there are a lot of people on campus, students and professors alike, who have knowledge of opportunities that their peers might find useful. A useful app might collect knowledge from these people so that others might benefit. People might want/be able to pass on opportunities that they don't want by making them public to others. Or, people who are simply looking to hire people specifically from campus could also post their positions to the app to make them more accessible.

The app I envision would keep a database of open opportunities on campus organized by category. Then, someone looking for an opportunity (say, in Biomedical Engineering) could text the service for suggestions. The app would return a list of suggestions, which might be hosted on the web. The suggestions would contain basic information depending on the suppliers, such as a description or a link to the opening.

# Questions:

     1. What platforms do you use to look for clubs/organizations to join?
     2. Do you think you would benefit from a peer-to-peer app which shares information about opportunities on campus?
     3. Would you contribute information to an app which shared information about opportunities on campus?
     4. Does an app like this already exist for your areas of interest?
     5. If so, does it fit your needs? How could it be improved?
     6. What kind of opportunites would you be most interested in hearing about?
     7. What kind of categories would you want for the app?
     8. What would be your preferred format for receiving suggestions? (e.g. web link, purely text, etc.)
     9. What kind of information would you want to know about in a suggestion?
    10. What else would you make available on the app?

# Answers:

## Question 1:

Person A: Primarily word of mouth for things on campus. Websites like Google/Glassdoor for jobs, etc.  
Person B: I mostly joined the clubs I'm in after hearing about them in class or from friends.  
Person C: AnchorLink, Doreways, Glassdoor, LinkedIn.  

## Question 2:

Person A: Yeah, that sounds cool.  
Person B: Yeah, sure.  
Person C: Yeah, I'd use it.  

## Question 3:

Person A: I think so. I feel like a lot of people on campus are competitive though, so I don't know if everyone would be willing to share all the opportunities they know about, but it would be useful for clubs.  
Person B: Sure, like I'm in a few small clubs and I'm pretty sure people don't go to them because no one knows about them.  
Person C: Eh, I'd probably check it more than I'd post to it, it would be nice if you could get professors and whatnot involved so there's more of an inflow for opportunities.  

## Question 4:

Person A: I guess AnchorLink, and yeah, Google, but I don't really use Anchorlink.  
Person B: Well, the clubs that I mentioned are already on AnchorLink, but I feel like we're so small that we don't really show up in the searches that often.  
Person C: Yeah dude, there's way too many apps to be honest. There's like a different one for everything: AnchorLink, DoreWays, Glassdoor, LinkedIn. It's a monster, dude.  

## Question 5:

Person A: I guess. I'm pretty happy with where I am right now, but it would be cool to see what else is out there.  
Person B: I mean, not really, because of the things I mentioned, we're too small to get noticed on any of the big sites.  
Person C: Yeah, they're good apps, it's just a hassle to check all of them all the time.  

## Question 6:

Person A: Organizations and jobs, I guess.  
Person B: Clubs, I guess, but I'd proabbly want to post stuff about my clubs so that other people would join.  
Person C: Jobs and internships.  

## Question 7:

Person A: You could probably separate it by type of activity, like social clubs, athletic clubs, job opportunitys, and stuff like that.  
Person B: Maybe have one for each major, so that people could search according to their major interests.  
Person C: You could separate it by major, and then have filters so that you could select for jobs which are open in certain times for a certain number of hours per week and stuff.  

## Question 8:

Person A: I guess a web format would be the best for me. I don't want to be getting notifications all the time, I just want to access it when I need to.  
Person B: I guess text? I think it could be similar to AnchorLink, as long as it makes it easier to find certain things.  
Person C: I think it would be good to give different options, like text notifications or e-mail.  

## Question 9:

Person A: I think just a link to a website would be fine, it would be hard to put all of the info into a text message.  
Person B: Maybe you could just send out blurbs over text/e-mail suggestions, then include a link to find out more about it.  
Person C: You should have a summary in the immediate suggestions, and then tell them where they can go to learn more about the position.  

## Question 10:

Person A: Eh, not really. It sound pretty good, and it doesn't seem like it needs anything else.  
Person B: Maybe different filtering options? Like how Amazon gives a rating system, a "rising in popularity", or like having a different "featured organization" every month.  
Person C: I dunno, this would be hard to do, but maybe you could integrate with some of the big apps like LinkedIn or Doreways to get more information and reach a wider audience.  

# Requirements

1. The application should allow users to access a database of available opportunities on campus
  a. Users should be able to searach the available opportunities using multiple filtering options
    - Filter by category, e.g. subject areas
    - Filter by activity type, e.g. Internships, Research, Service, Leadership, etc.
    - Filter by commitment, e.g. hours per week
  b. The suggestions should be returned through an existing/popular platform, such as text-messaging
  c. The returned suggestions should provide all relevant information about the opportunity
    - Return a text description of the opportunity, including the details mentioned above
    - If there is additional information hosted on an external resource (e.g. the internet), provide a link
  d. The application should allow users to subscribe to automatic notifications if an opportunity they are interested in is posted/changed
2. The application should allow the user to ask for a list of the filtering options
3. The application should allow users to post opportunities to a central database so that others can access them
  a. The application should have an accessible interface which makes it easy for users to input information
    - The interface should suggest fields which the user should input (e.g. category, type, etc.)
    - The interface should use an existing/popular platform, such as text messaging, or a web form
  b. The application should allow users to update/modify existing opportunities
    - Users should be able to add details 
    - Users should be able to update their postings if an opportunity has been filled
4. The application should be accessible to all types of users, including professors, employers, and students
		
# Development Approach

## 1a. Implementation of the Database

Create a database which can be used to hold the entries  
  a. The database should store each entry as an individual object
    - Each entry should be split into various fields, such as category, activity type, etc.
    - Possible implementation is to store each entry as a map with keys for each field
  b. One should be able to query the database by one/multiple fields
    - Filtering by one field can be done by iterating through the entries and seeing which ones satisfy the condition. The query should return a subset of the database.
    - Filtering by multiple fields can be done by chaining multiple filters together. The query will still return a subset of the database.
  c. If a malformed query is sent to the database, an informative error message should be returned

## 1b. Testing the initial database

Hard-code a sample database  
Test database queries by running them against the test database  
  - Single-filter queries for each filter type
  - Multiple-filter queries
  - Queries which return nothing
  - Queries which would produce an error message

## 2a. Query the Database Through Text Interface

Create a parser which reads text messages and returns the appropriate response  
  a. Provide an option for the user to ask for filtering options. The parser should recognize the user's request and return the desired information
  b. Provide an option for the user to query the available opportunities. The parser should recognize what type of request the user is making, and query the database based on the supplied filtering options
  c. If a malformed request is sent, the parser should recognize it, and return an informative error message

## 2b. Testing the Text Interface for Querying the Database

Using the sample database from before, make the same queries as in 1b, but done through the text interface  
Send a text to ask for filtering options  
Send a text which asks for filtering options that returns an error message  

## 3a. Create Functions for Updating the Database

Implement an update funciton
  - Update the specified entry if it is in the database
  - If the entry is not in the database, return an informative error message
Implement a delete function
  - Delete the specified entry if it is in the database
  - IF the entry is not in the database, return an informative error message

## 3b. Testing the Update/Delete Functions

Run queries to update entries in the database and check that the resulting database is correct  
Query the database after an update command to check that it returns the correct result  

Run queries to delete entries in the database and check that the resulting database is correct  
Query the database after a delete command to check that it returns the correct result

Attempt to update a non-existant entry and affirm that the error message is correct.
Attempt to delete a non-existant entry and affirm that the error message is correct.

