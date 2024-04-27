# Creating the Authentication Middleware File

Middleware is software that allows two or more applications in a distributed system to communicate in one or more ways. Essentially, the middleware in the system allows the controllers and routes to communicate. For example, in order for the users to successfully access the content of the app, they must log in first. To ensure that whoever is attempting to access the data is, in fact, a user, we require some form of identification. Most of the time, this authentication takes the form of user-related data. So when we collect this information, we must run a check on it, and if it’s valid, we proceed with the request. The middleware is the system that performs the check. In short, middleware serves as a hidden layer that facilitates system communication.

# Headers

API headers are essentially extra information we pass when requesting. Headers can be used for authorization, setting content type, accepting a DocID, and protecting data. Headers transport a lot of data and can be used to communicate between servers and clients.

Assume we need to gain access to a specific secure endpoint. In most cases, endpoints of this type are secured by requesting an authenticated user’s token. This token is frequently sent as a header and then used by the user to authorize access to the endpoint.

# AuthMiddleware

We’ll now create an authentication middleware file, authMiddleware.go. We write a function that checks to see if a user’s token generated upon login is being passed as a header. The user is authenticated if a valid token is provided, and the next step is initiated. If this isn’t the case, an error is thrown. The error message, “No Authorization header provided,” is returned if no token is passed and the field is empty. To test this endpoint, we must first create an endpoint that requires a header to be passed. So, let’s build our authentication middleware.

# Fetch User's data

Reading data from a database
Users can browse through the app and perform different activities when they log in successfully. When they go to the “Profile” tab, they should be able to see details about themselves, for example, the name and username they provided during registration.

When users log in successfully and navigate to their “Profile” tab, they want to see details about their account. To do this, we must fetch these details from our database.
To fetch the user's details, we create an endpoint that takes the user's ID as a parameter and then searches for the associated account.
If the account exists, the user details are returned; if not, an error is thrown.


# Fetching all the platform users

Only admin users are able to view every user in the database. The admin can utilize this feature to see who has registered for the platform and how many users there are overall. This request provides details about each user in the database’s user collection.


We need to create a new controller function, GetUsers(). This route is protected by the authentication middleware, which checks to ensure that only authenticated users can access it. Next, we write a check to see the user_type of the user trying to access this data. If the user_type is not equal to ADMIN, we’ll deny this user entry. Next, we need to search the user collection for all the users who have signed up and the total number of registered users. In the userController.go file, we should have a function like this below:


