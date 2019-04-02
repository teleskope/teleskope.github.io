# Table of contents

* [About Teleskope](#about-teleskope)
* [Project Goals](#project-goals)
* [Mockups](#mockups)

# About Teleskope
Teleskope is an application that provides a new way for local and non-local companies who want to recruit students from UH to make their (potential) opportunities known to students. At the same time, students can create profiles on the site with their interests. The site can match students to employers and vice-versa.

# Project Goals
* Students and Companies can create accounts. 
* Students can view recruiting companies and available positions. 
* Students can find companies that match their skillset & interests. 
* Companies can easily view interested students and receive emails. 

# routes 
- root (/) 
> root path will change depending on whether a user is authenticated as a Admin, Student or a Company. Landing page will be displayed if not logged in. 
- students
  - show profile (/students/:username) 
  - index (/students) **admin only**
- companies
  - index (/companies)
  - show (/companies/:id)
- settings 
  - edit profile (/settings/profile)
- Authentication
  - registration (/sign-up)
  - sign in (/sign-in)

# Mockups
## Landing page

## Student Homepage (logged in)

## Company Homepage (logged in)

## Student profile page

## Company profile page
