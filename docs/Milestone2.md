Application Structure

1. User Object - ID, Name, Email, Password
2. Product Object - prod_ID, Name, Category, Description, Details, upVotes, downVotes
3. Page Object - page_ID, List (Product Objects)
4. upVote - Is a relationship between 1 Product & 1 User. Each vote is associated with the product name when a user interacts with it.
5. downVote - Is a relationship between 1 Product & 1 User. Each vote is associated with the product name when a user interacts with it.

For our API, we will need CRUD operations with endpoints for:
1. /addProduct which allows for a product to be added to the page when a request is sent to this endpoint containing the  Name, Description, Details, etc. of this product.
2. /productInfo is a read endpoint which returns all fields for the product as a JSON object
3. /createUser  which allows for a new user to sign up with their information
4. /upvote which adds an upvote to the given product  provided a product name, and also increments the upvote count. 
5. /downvote which adds a downvote to the given product  provided a product name, and also increments the downvote count. 
6. /deleteProduct  which allows the user to remove the product they have added to a category for rating
7. /viewPage which should let the user view a page they requested for

Our  file structure to implement:
1. server.js - a server that handles parsing the incoming requests with their URLs and parameters and sends that information to the correct functions. 
2. database.json - a file that stores the database
3. database.js - a file that implements database logic, has functions such as write(), find(), remove(), and update() and handles any errors that may occur
3. pageview.html - a file that renders HTML to view any page
4. productview.html - a file that renders HTML to view any product 
5. productview.js - a client-side JS file which pings the endpoint via fetch for Pageview/product/lookup/ and then uses the returned JSON to inject HTML (via innerHTML) into the productview.html file so that the product details can be viewed
