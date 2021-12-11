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


APIs: A final up-to-date list/table describing your application’s API // TODO by @elizabethseto

## Database

Here's the description of our database:

        Data types in the tables: 

        Products (id varchar(50), name text, category(text), description(text), image(text), upvote(integer), downvote(integer));

        Users (name text, password varchar(50), email text, id varchar(50));

        Products table contains the product id, name, its category(either food,travel, or entertainment), description, file path for the image and the no. of upvotes/downvotes it gets.
    
        Users table contains the name, password, email, and user id of all the users who log into our application.
        
        Example tables:

        Products:

                         id                  | name  | category | description |       image         | upvote  | downvote 
        -------------------------------------+-------+----------+-------------+---------------------+---------+----------
        0dae2f90-f25b-4a2b-b261-03057292938a | Paris | Travel   | a place     |  imgs/Paris.jpg     |     8   |    11

       

        Users:

          name   | password |       email       |                 id                  
        ---------+----------+-------------------+-------------------------------------
         Nisarga | cs326    | nisarga@gmail.com | rwe2f90-f25b-4a2b-b261-03057292938b


URL Routes/Mappings: 
https://wevote326.herokuapp.com/
* This is the main login page and is where create account button and user login button are located on the top of the website. Users won't be allowed to vote if they do not have an account.
* This page is also accessed when a user hits log out on the navigation bar.
https://wevote326.herokuapp.com/viewPage?page=createAccount
* This is where the user makes an account and fill out the fields in order to create the account.
https://wevote326.herokuapp.com/viewPage?page=login
* This is where the user logins with their credentials.
https://wevote326.herokuapp.com/viewPage?page=foodRatePage
* This is the food rate page. This is where all the food items that are already created and users can rate each food by the upvote and downvote button.
* If you press view, it will take you to a different page where it will display additional details about the food.
https://wevote326.herokuapp.com/viewPage?page=foodCreatePoll
* This is where you enter the food that you want other users to rate. Users can upload a photo of the food, write the name of the food, and details about it.
https://wevote326.herokuapp.com/viewPage?page=foodProductPage&name=Burger
* This is one of the individual food item with all the details listed about the food. It displays the name of the food, a picture, details about the food, and number of upvotes and downvotes. 
https://wevote326.herokuapp.com/viewPage?page=travelRatePage
* This is the travel rate page. This is where all the locations that are already created and users can rate each location by the upvote and downvote button.
* If you press view, it will take you to a different page where it will display additional details about that particular location.
https://wevote326.herokuapp.com/viewPage?page=travelCreatePoll
* This is where you enter the location that you want other users to rate. Users can upload a photo of the location, write the name of the location, and details about it.
https://wevote326.herokuapp.com/viewPage?page=travelProductPage&name=Paris
* This is one of the locations with all the details listed about the location. It displays the name of the location, a picture, details about the location, and number of upvotes and downvotes. 
https://wevote326.herokuapp.com/viewPage?page=entertainmentRatePage
* This is the entertainment rate page. This is where all the entertainment items that are already created and users can rate each entertainment by the upvote and downvote button.
* If you press view, it will take you to a different page where it will display additional details about the food.
https://wevote326.herokuapp.com/viewPage?page=entertainmentCreatePoll 
* This is where you enter the particular entertainment that you want other users to rate. Users can upload a photo of the entertainment, write the name of the entertainment, and details about it.
https://wevote326.herokuapp.com/viewPage?page=entertainmentProductPage&name=Avengers 
* This is one of the movies with all the details listed about the it. It displays the name of the movie, a picture, details about the movie, and number of upvotes and downvotes. 

Authentication/Authorization: Upon login, the user has immediate access which allows them to creating polls and rating items. Their account cannot be accessed by any other user, as it is not sharable, and the user is the only individual that can access their account. 



## Division of Labor

1. Nisarga: Designed the wireframes for the app, Worked on the frontend pages HTML/CSS, Wrote the content for markdown files, Deployed the app and set up the database on Heroku, Worked on the backend for DBMS

2. Elizabeth: Worked on the frontend pages HTML/CSS, deployed the app and set up the database on Heroku, got the data to render on the frontend, create account/login implementation, designed backend for DBMS

3. Yiming: Worked on frontend pages HTML/CSS


Conclusion: Overall, the whole process of creating this project was definitely a learning experience. It involved a lot of trial and errors, but it was worth it. Throughout the design and implementation process, we discussed as a team what would be best for the format of the website and updated based on what we thought was best. After having a solid outline of what the design of the website would look like, we started to code. One important concept that we learned throughout the process is to communicate clearly about what is needed to get each part of the project done. It was difficult at the beginning because some of us never worked on a programming group project before, therefore, it was a very new experience. In terms of technical hurdles that we encountered, getting the Postgres database set up was difficult. After receiving help from the TAs and doing more research, we overcame the issue and were able to set up the database. In conclusion, we are very glad the way the project turns out and really enjoyed the process of making it.

