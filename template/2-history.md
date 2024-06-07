# History

During the semester we learn a lot about time management, producing value each week, and working together as a large group. We also learn about technical specificity on building an app but the transversal skills obtained are far more important.
The proof-of-concept built during the semester has only the main features (inventory, lend/borrow to others, manage the loan). Those features only work online. 
Another main issue that we currently have is the backend security. Indeed, we are using Firebase, and for each GET request, the integrality of the table is fetched to the mobile application. Furthermore, for each POST request, there is no check on the database side, to see if the request’s author has the permission to perform the action.
In order to have a MVP, we would have to be able to manage our inventory offline and secure the database, by using Google Cloud Functions. We would also need to implement some other features, like the possibility to loan multiple objects in one loan, the possibility to group items in our inventory, or adding personalized categories.



*Maximum 1 page*

*Describe the V1 POC as planned by Sprint10.*

*What did you learn?*

*What is missing to bridge from PoC to MVP?*

