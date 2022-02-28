# 💻 Code Challenge 〰️ Phone Catalog
> Code challenge proposed by DCSL GuideSmiths  
> Made by Andrea Calvo Moreno
>
> This repository centralises the interface and the api of the "Phone Catalog" application. 
  It gathers the full project management based on a Kanban methodology in order to organise the workflow and Git branches .
  The specific documentation related to the app deployment and performance is defined in this repository.

## 🎯 Fulfilled requirements
 - A REST API providing phones’ information
   - Implemented in NodeJS
   - End-Points: 
        * GET phones
        * GET phone by ID
        * DELETE phone by ID
        * POST new phone  
        (*End-Poins documentation available in README.md from API repository*)
   - Unit & Integration End-Points tests with Mocha & Chai suite
   - Persistence layer with MySQL database
 
 - A REACT APP allowing the user to browse the phones catalog
   - Responsive design for mobiles
   - Home page displays the phone catalog with images
   - Phones' information retrieved from the API
   - Phone details are shown in a new page with a few more info about that phone
   - A spinner component while the REST API is fetching phone info
   request is ongoing and the app is waiting for phones data
   - Routing implemented to navigate through the app
   - E2E test for the form and buttons with Cypress suite
   
 - Full APP deploy in Heroku
 
### 👣 A little further on:  
 - To prove knowledge in agile methodologies, a Kanban project has been created in Github () . 
 - With this, tickets associated with the requirements and app functionalities have been created and labelled based on the level of the requirement:
     - A: minimum
     - B: desirable
     - C: advanced  
and the type development:
     - front-end 
     - back-end  
 - It is possible to track the project duration based on:
     - the estimated duration of the ticket (Points) at the beginning 
     - the real time consumed on its implementation (Consumed Time)  
 - Three boards are displayed on the project wall where tickets rotate according to the status of their resolution: To do, In progress and Done.
 - Workflow:
     - Git has been used to manage the workflow and version control. 
     - For the core app development, a main workflow associated with the "develop" branch is established, and on this branch, the finished tickets are merged.
     - These tickets are associated to branches following the "issue#xy" pattern where "xy" indicates the ticket number which is automatically generated by GitHub.
     - Once the ticket is resolved, the branch with the resolved issue is merged with "develop" with no fast-forwarding to keep the commits after merge.
     - Finally, "develop" it is pushed to the remote GitHub repository.
     - At the end of the project, a code release is performed and the whole application is deployed to Heroku through the "deploy" branch, whose content will be similar to develop with some particularities to make Heroku work correctly.

![alt text](https://github.com/acalvom/phone-catalog-board/blob/master/project_workflow.png?raw=true)
 
  
## ⚙️ Used Technologies
▪️Methodology: `Kanban` `Git`  
▪️Front-End: `React` `JavaScript` `CSS3`  
▪️Back-End: `Node.js` `Express`  
▪️Persistence: `MySQL` `phpMyAdmin` `JawsDB`  
▪️Testing: `Mocha-Chai` `Cypress`  
▪️Deploy: `GitHub` `Heroku` 
      

## 🔖 Libraries, Third party code & Packages
▪️Front-End: `Axios` `Fontawesome` `Bootstrap 5` `SweetAlert2` `React Hook Form` `React Router 5`  
▪️Back-End: `Nodemon` `Multer`

## ☁ Heroku deploy
🔗 [Phone Catalog](https://phone-catalog-acalvom.herokuapp.com/)  

## :octocat: Repositories  
🔗 [React - Front-End](https://github.com/acalvom/phone-catalog-react)  
🔗 [Node.js - API - Back-End](https://github.com/acalvom/phone-catalog-api)  

## 🏁 Project set-up

***Option A: Run in localhost***

##### 1 - Clone with terminal:
🟡 Interface ➡ Front-End
```sh
> cd <folder path>
> git clone hhttps://github.com/acalvom/phone-catalog-react
> cd phone-catalog-react
> phone-catalog-react > npm install
```
🟡 API ➡ Back-End
```sh
> cd <folder path>
> git clone https://github.com/acalvom/phone-catalog-api
> cd phone-catalog-api
> phone-catalog-api> npm install
```
##### 2 - Create MySQL database with info:
```sh
"host": 'localhost',
"user": 'phone-catalog',
"password": 'dcsl',
"database": 'phone-catalog'
```
##### 3 - Execute full app:
🟡 MySQL: Start MySQL engine.     
🟡 API: `> nodemon index.js`    
🟡 React app: `> npm start`  

***Option B: Run in Heroku***

##### 1 - Open Heroku URL in the browser:
🟡 [Phone Catalog](https://phone-catalog-acalvom.herokuapp.com/)  

##### 2 - Things to have in mind ❗:
🟡Image phone will not be uploaded nor displayed on cards due to Heroku dynos have an [ephemeral filesystem](https://devcenter.heroku.com/articles/dynos#ephemeral-filesystem), therefore
static files cannot be stored in here. Alternatively, an external storage solution such as [S3 from AWS](https://aws.amazon.com/es/s3/)
could be use.  
🟡This approach could not be implemented at the time of delivery since there was neither an AWS account nor sufficient knowledge to include it successfully.   
🟡So, when filling the form, even though an image is required, it will not be displayed in the phone card
