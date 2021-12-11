# Team Delta

## WeVote App

### Fall 2021

Our application is deployed on heroku on this link: https://wevote326.herokuapp.com

We have implemented a web application where people can add and read product reviews in different categories. These reviews will be in the form of upvotes and downvotes on items in each category. Some of the categories that we have integrated into the application are: Entertainment, Food, and Travel. This application will be similar to some shopping websites in a way that the users have the ability to click on the item that they are interested in, and be directed to a different page where they can see more details about the particular item. These details will include the description of the item, and the number of upvotes/downvotes it gets. 

Our app is using the key concept from social media platforms such as Facebook and Instagram, where users are able to like/dislike each other’s posts and the person who’s posting can see the feedback they are receiving from other users. Since this is a familiar concept that many people do on a daily basis, the voting application will be very straightforward and intuitive to use.

WeVote App will be helpful for the users who are looking for new places to travel, want to explore different food options, need TV show/movie recommendations, and so on. They can look at the upvotes and downvotes for all the items in different categories when they are trying to choose their best option. They can also upload any item of their choice into one of the categories so they can seek other users' opinions about that item in terms of upvotes and downvotes.

## Team Members

1. Nisarga Patil (@nisargapatil)
2. Elizabeth Seto (@elizabethseto)
3. Yiming Zhao (@yimingzhao14)


## User Interface

Our UI has four main compoments: Home Page, Rating Pages, Product Pages, Create Poll Page

### Home Page

This is how the home page looks when you first go to the heroku link. You can see the Food, Travel, and Entertainment categories to choose from, as well as create account and log in buttons at the top.

![Home Page](Final_Screenshots/HomePage.png)

If you try to select a category before creating your account or logging into your existing one, you will get this alert.

![Alert](Final_Screenshots/HomePageAlert.png)

When the user selects create account, they will be redirected to this form to fill out their details and create an account.

![Create](Final_Screenshots/CreateAccount.png)

If the user wants to log in instead, they will be redirected to this form to enter their username and password.

![Log In](Final_Screenshots/Login.png)


### Rating Pages

Once the user is logged in and selects a category, they will be able to view all the products and corresponding ratings on that page.

Depending on the chosen category, these are the pages you will be redirected to:

1. Food

![Food](Final_Screenshots/FoodRating.png)

2. Entertainment

![Entertainment](Final_Screenshots/EntertainmentRating.png)

3. Travel 

![Travel](Final_Screenshots/TravelRating.png)

### Product Pages

When you click on 'view' on one of the featured products, it takes you to the product details page which displays the upvotes and downvotes on the product, and its description added by the user. 

For example, if you wanted to view more details about 'Stranger Things' on the 'Entertainment' page, this is what you will find : 

![Details](Final_Screenshots/ViewProduct.png)

### Create Poll Page

If you click on 'Add Item' on the ratings page, you will be able to create your own rating poll for whichever product you use. You simply have to enter the information in this form, and the product will be added to that catgeory.

![Poll](Final_Screenshots/FoodPoll.png)


## API 

All API endpoints are located in server.js

* POST: /api/:createUser
This call gets all of the user's data and creates an account for them.

* POST: /api/:login
This call gets user information from the database once user enters credentials and log in.

* POST: /api/:addProduct
This call adds a product that an user enters.

* GET: /api/: productInfo
This call gets all of a product's information such as name and details about it.

* GET: /api/: productSummary
This call list the summary of the products.

* POST: /api/:upvote
This call is used to have user upvote.

* POST: /api/:downvote
This call is used to have user downvote.

## Database

Here's the description of our Postgres database:

Data types in the tables: 

#### Users table

| Column| Data Type| Description|
|---|---|---|
| name | text  | Name the user logs in with |
| password | varchar(50)| First name the user registered with  |
| email| text| Email the user registered with |
| id  | varchar(50) | unique user ID for every registered user |

Users table contains the name, password, email, and user id of all the users who log into our application.

Example User Table: 

          name   | password |       email       |                 id                  
        ---------+----------+-------------------+-------------------------------------
         Nisarga | cs326    | nisarga@gmail.com | rwe2f90-f25b-4a2b-b261-03057292938b



#### Products table

| Column| Data Type| Description|
|---|---|---|
| id  | varchar(50) | unique product ID for every added product |
| name | text  | Name of the product |
| category | text| Category of the product  |
| description | text| More details about the product |
| image  | text | Image file path for product picture |
| upvote  | integer | No. of upvotes the product received  |
| downvote  | integer | No. of downvotes the product received |


Products table contains the product id, name, its category(either food,travel, or entertainment), description, file path for the image and the no. of upvotes/downvotes it gets.
  
        
Example Product table:

                         id                  | name  | category | description |       image         | upvote  | downvote 
        -------------------------------------+-------+----------+-------------+---------------------+---------+----------
        0dae2f90-f25b-4a2b-b261-03057292938a | Paris | Travel   | a place     |  imgs/Paris.jpg     |     8   |    11


## URL Routes/Mappings: 

* This is the main login page, where create account button and user login button are located on the top of the website. Users won't be allowed to vote if they do not have an account.
* This page is also accessed when a user hits log out on the navigation bar.
https://wevote326.herokuapp.com/

* This is where the user makes an account and fill out the form in order to create the account.
https://wevote326.herokuapp.com/viewPage?page=createAccount

* This is where the user logins with their credentials.
https://wevote326.herokuapp.com/viewPage?page=login

* This is the food ratings page. This is where all the food items are displayed along with voting options. Users can rate each item using the upvote and downvote button.
https://wevote326.herokuapp.com/viewPage?page=foodRatePage

* This is one of the individual food items with all the details listed about the food. It displays the name of the food, a picture, description about the food, and number of upvotes and downvotes. It will be displayed if you click on 'view' on one of the food items. 
https://wevote326.herokuapp.com/viewPage?page=foodProductPage&name=Burger

* This is where you can create a poll for the food item you want other users to vote on. Users can upload a picture of the food, and write its name and description.
https://wevote326.herokuapp.com/viewPage?page=foodCreatePoll

* This is the travel rate page. This is where all the locations that are already created and users can rate each location by the upvote and downvote button.
https://wevote326.herokuapp.com/viewPage?page=travelRatePage

* This is where you enter the location that you want other users to rate. Users can upload a photo of the location, write the name of the location, and details about it.
https://wevote326.herokuapp.com/viewPage?page=travelCreatePoll

* This is one of the locations with all the details listed about the location. It displays the name of the location, a picture, details about the location, and number of upvotes and downvotes. It will be displayed if you click on 'view' on one of the Travel items. 
https://wevote326.herokuapp.com/viewPage?page=travelProductPage&name=Mumbai

* This is the entertainment rate page. This is where all the entertainment items that are already created and users can rate each entertainment by the upvote and downvote button.
https://wevote326.herokuapp.com/viewPage?page=entertainmentRatePage

* This is where you enter the particular entertainment that you want other users to rate. Users can upload a photo of the entertainment, write the name of the entertainment, and details about it.
https://wevote326.herokuapp.com/viewPage?page=entertainmentCreatePoll 

* This is one of the movies with all the details listed about the it. It displays the name of the movie, a picture, details about the movie, and number of upvotes and downvotes. 
https://wevote326.herokuapp.com/viewPage?page=entertainmentProductPage&name=Avengers 


## Authentication/Authorization
 
Upon login, the user has immediate access which allows them to create polls and vote on items. Their account cannot be accessed by any other user, as it is not sharable, and the user is the only individual that can access their account.

Where the user tries to log in, we will check if the password they entered matches the one in our database associated with their username, before their login is approved. We are currently not using any ecryption since there is no sensitive user data on the app and you also cannot see which user has added which products.


## Division of Labor

1. Nisarga: Designed the wireframes for the app, Worked on the frontend pages HTML/CSS, Wrote the content for markdown files, Deployed the app and set up the database on Heroku, Created tables, Worked on the backend for DBMS and wrote queries, designed the grading rubric

2. Elizabeth: User interface implementation, worked on the frontend pages HTML/CSS, deployed the app and set up the database on Heroku, got the data to render on the frontend, create account/login implementation, backend implementation of user authentication, designed backend for DBMS, documentation for markdown files

3. Yiming: Worked on frontend pages HTML/CSS


## Conclusion

 Overall, the whole process of creating this project was definitely a learning experience. It involved a lot of trial and errors, but it was worth it. Throughout the implementation process, we discussed as a team what would be best for the format of the website and updated based on that. After having a solid outline of what the design of the website would look like, we started to code. One important concept that we learned throughout the process is to communicate clearly about what is needed to get each part of the project done. It was difficult at the beginning because some of us never worked on a programming group project before, therefore, it was a very new experience. 
 
 In terms of technical hurdles that we encountered, getting the Postgres database set up was difficult. After receiving help from the TAs and doing more research, we overcame the issue and were able to set up the database. We still faced some issues with keeping the images persistent as they would stop loading after a certain period of time, and found some related documentation - https://help.heroku.com/K1PPS2WM/why-are-my-file-uploads-missing-deleted. It did not affect the functionality of our app, and is also not the highlight of all the features, so it was not the top priority.
 
 If we had more time, we would definitely introduce some interactive features such as comments on the products in addition to upvotes/downvotes. All users will be able to add comments and respond to other user' comments on a product. We would also like to separate categories such as Sports, Movies, TV shows which currently fall under Entertainment. We could also add more categories like Fashion, Beauty, etc. We would also update the database set up to only allow unique usernames and email addresses, and add encryption for passwords.
 
 We are happy with the way our project turned out and really enjoyed the process of making it.

