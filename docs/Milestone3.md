
For our database management system, We are using Heroku Postgres. Our application is deployed on heroku on this link:

Here's the description of our database:


        Data types in the tables: 

        Products (id varchar(50), name text, category(text), description(text), upvote(integer), downvote(integer));

        Users (name text, password varchar(50), email text, id varchar(50));

        Products table contains the product id, name, its category(eitehr food,travel, or entertainment), description, and the no. of upvotes/downvotes it gets.
    
        Users table contains the name, password, email, and user id of all the users who log into our application.
        
        Example tables:

        Products:

                         id                  | name  | category | description | upvote | downvote 
        -------------------------------------+-------+----------+-------------+--------+----------
        0dae2f90-f25b-4a2b-b261-03057292938a | Paris | Travel   | a place     |      8 |       11

       

        Users:
          name   | password |       email       |                 id                  
        ---------+----------+-------------------+-------------------------------------
         Nisarga | cs326    | nisarga@gmail.com | rwe2f90-f25b-4a2b-b261-03057292938b

