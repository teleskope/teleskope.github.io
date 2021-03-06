# Table of contents

* [About Teleskope](#about-teleskope)
* [Developer Guide](#developer-guide)
  * [Installation](#installation)
* [Community Feedback](#community-feedback)
* [Mockups](#mockups)
* [Actors](#actors)
* [Routes](#routes)



# About Teleskope
Teleskope is an application that provides a new way for local and non-local companies who want to recruit students from UH to make their (potential) opportunities known to students. At the same time, students can create profiles on the site and choose skills they have.  As a company owner, one can own more than one company and add job opportunities under these companies.  In order to attain workers fit for the job a company can add skills to the job.  The app will then recommend companies to students based on te number of common skills between a student and all of the skills jobs listed under the company.  A student will also be able to follow companies and be notified of the companies actions (new job opportunities, removing job opportunities, etc.).  

## Project Goals
* Students and Companies can create accounts. 
* Students can view recruiting companies and available positions. 
* Students can find companies that match their skillset & interests. 
* Companies can easily view interested students and receive emails. 

### Visit our deployed page
[teleskope.meteorapp.com/](http://teleskope.meteorapp.com/#/)

### Check out our progress on our Project Boards
* [Milestone 1](https://github.com/teleskope/teleskope/projects/1)
* [Milestone 2](https://github.com/teleskope/teleskope/projects/2)
* [Milestone 3](https://github.com/teleskope/teleskope/projects/3)

### See our code on Github!
[github.com/teleskope/teleskope](https://github.com/teleskope/teleskope)




# Developer's Guide
This app was built using the Meteor web framework, with MogoDB as the database. Semantic-UI and ReactJS were used to design our user interface. More information on these technologies can be found in the links below:
* [Meteor](https://www.meteor.com/)
* [MongoDB](https://www.mongodb.com/)
* [Semantic-UI](https://semantic-ui.com/)
* [ReactJS](https://reactjs.org/)

## Installation
1. Install Meteor
2. Fork this repo
3. In the terminal, go into the project's app directory and install dependencies using the following command:
> `$ meteor npm install`
4. Run the app
>  `$ meteor npm run start`
5. Go to `localhost:3000` 




# User Guide
This section will showcase the different pages on our site including what they do and what they look like!

### Landing
The landing page serves to welcome you to the site and direct you to register as a student or company while offering information about how the site is doing and who we are.
![image](images/Landing.png)

### Dashboard
The dashboard is the first page you are directed to once you log in. It serves as your hub for viewing any notifications you have about companies interested in you and companies you are following or students you are interested in if you are logged in as a company.

![image](images/Dashboard.png)

### My Profile
This page is for viewing everything about yourself. If you're a student it's your place that companies will find information about you to decide if they want to hire you. If you're a company it will show your company information and list your current openings.

![image](images/Profile.png)

### Companies
This page is for students to browse companies that are on the site that they might want to reach out to or express interest in. At the top of the page are displayed 3 comanies that match the user the best. Below is a sortable list of all of the companies. Users can favorite a company from this page or select a company to find out more.

![image](images/ListCompanies.png)

### Job 
A user can see an individual job posting for a company, its description and click to link them to the online application protal. 
![image](images/ShowJob.png)

### Students
This page is for companies to browse students who they might want to reach out to given information listed in the jobs the company has available. Users can see other students, their skills, and experiences.

![image](images/ListStudents.png)




# Community Feedback
#### Jackie L.
1. Liked the how jobs cards are displayed on a companies page.
2. Did not like the fact that when you submit an account, it does not redirect you from the registration page.
3. Thought the follow function was very useful for keeping track of job postings.

#### Dan S.
1. Thought the CTA buttons like login, registraion, switch registration were easy to use. 
2. Liked how easy it was to follow a company 
3. Thought the sorting types would be more intuitive if they could be reversed as well. 
4. Thinks navigating to your own student profile should allow you to edit it instead of having to go to the /profile path. 

#### Reid D.
1.  Thought the colors and customer review on the landing page were nice, but thinks the reviews should be listed at the bottom and the statistics more centered.
2.  Would have liked to see links on the landing page, perhaps in the text or pictures to something like "exploring opportunities". 

#### Umi C. (Registered as a student)
1.  Menu bar is a bit thick and the rounded corners look off
2.  After registering the app stayed on the registration page (recommended the app redirect to the "Edit profile" component).
3.  The skills they wanted weren't available.
4.  Found it weird that the added skills are listed in the search box causing the box to constantly resize when skills were added or removed (preferred labeling the skills).  
5.  Weren't sure if the skills were added or removed and wanted some confirmation (preferred a checkbox format)
6.  Struggled to find the jobs (asked if there was a list job page)
7.  The "Apply" button doesn't work and it wasn't visibly obvious to him (blended in with the background)
8.  He didn't know what the "Apply" button was supposed to really do.
9.  He wished the app would remember if he applied for jobs or not so he doesn't re-apply.
    
#### Leighton V. (Registered as an employer)
1.  Footer is lacking
2.  The "I'm an employer" button on the landing page directs to the student registration
3.  Regarding the social media fields in the "Edit Profile" component, they didn't know whether to enter their username or the entire link to the profile.
4.  Can't add a job as a company
5.  Regarding the "Edit Profile" component they found that the capitalization of the field labels weren't consistent (twitter, linkedin, and github aren't capitalized)
6.  Company owner can apply to jobs
7.  Can't add a company
8.  Liked the logo




# Mockups
## Landing page
![image](images/Landing.png)

## Company Index (logged in)
![image](images/ListCompanies.png)

## Students Index (logged in)
![image](images/ListStudents.png)

## Student profile page
![image](images/ShowStudent.png)

## Company profile page
![image](images/ShowCompany.png)

### Show Profile page (Logged in as owner of the company
![image](images/ShowCompanyasCompany.png)

## Job show
![image](images/ShowJob.png)

## Student Registration
![image](images/registerstudent.png)

## Company Registration
![image](images/registercompany.png)

## Edit Company
![image](images/EditCompany.png)

## Add Job
![image](images/AddJob.png)




# Actors
* Student
* Company
* Administrator 




# routes 
- root (/) 
> root path will change depending on whether a user is authenticated as a Admin, Student or a Company. Landing page will be displayed if not logged in. 
- students
  - show profile (/students/:username) 
  - index (/students) **admin only**
- companies
  - index (/companies)
  - show (/companies/:id)
- Profile (/profile)
- Dashboard (/dashboard)
- Authentication
  - registration (/signup)
  - sign in (/signin)
  
 
