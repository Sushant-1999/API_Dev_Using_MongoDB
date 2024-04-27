* We’re building a movie review system API called Shive. Web and mobile developers will be able to make use of our API in their applications. At the end of the project, we will have made:

    * A hosted functional Go API connected to a MongoDB database
    * Well-written documentation

We have two types of users in our application:

Administrators are responsible for handling the whole system. They upload and manage the different movies to be reviewed, and manage the users and their activities. Only users assigned the admin role or created as admins can do this.
Movie reviewers are the users who view upcoming movies and review them. After downloading the application, they sign up and create a profile. They can only access the platform contents when they log in.

Authentication and authorization are often used interchangeably, but in actuality, they differ. Authentication involves verifying who a user is. It’s the process of validating users through passwords, biometrics, pins, or some other identifying factor. It’s mostly done before authorization, and only authenticated users can go through the authorization process. On the other hand, authorization involves verifying what a user can access. It occurs after the authentication process. When a user is authorized, they have access to specific functionalities. Authorization is a way to control who accesses particular resources and restrict unwanted access.

