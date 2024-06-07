# Design and Implementation

## Frontend


The whole front end of our MVP is built using the Android Composables library. We defined some key components to be re-used, with a focus put on minimizing code duplication as this makes the product harder to maintain and more error-prone. 

The key screens for our apps are the “Inventory” where users can see and manage their items, the “Loan Screen” where users can see other user’s items and make requests to borrow them, and most importantly, the “Home Screen” that centralizes the key features to make it more user-friendly, for first-time users and faster for experiences one with a few ‘Quick Access’ buttons. 

One of the crucial components that allowed the MVP to run smoothly was an efficient tracking of images found in the items and user profiles, to ensure the images were correctly cached on the local storage of the app. This allowed us to greatly reduce the number of times the front end spent waiting for images and ensured a smooth user experience. 


## Backend
Application Logic : 
The backend will host the whole application logic, in order for the frontend to be up-to-date and responsive, to allow a pleasant use. It will fetch data for each user request, as well as fetch requests and updates made by other users at the same time.

Dynamic View Rendering : 
The frontend rendering will be determined by the backend, depending on the user’s information. This is mainly seen with the Borrowed Items list, which is not displayed if the user hasn’t borrowed any items. The other main influence of this dynamic view is the way an item is displayed, it will show or not some information depending on the state of the item or the loan linked to it.

Data Updates :
The backend is responsible for recalling the database periodically, to ensure the data displayed is always the latest. This recall is also done at each arrival on a page, to avoid a content update a few seconds after arriving on a screen. 

Responsive Backend-Frontend Interaction : 
For a quick app, it is necessary to have tight interactions between the backend and the front end, that’s why we designed our backend as one view model per screen. This way we can ensure quick response time and only necessary tasks are done in the backend, for each frontend need. A good example of this quick interaction is the QR-Code scanner that pops up and disappears quickly at each call to the functionality. At the instant a Partagix QR-Code is recognized, the user is immediately redirected to the item or the loan (depending on the loan state of the item).

Notifications :
Our backend handles and produces push notifications to ease up interactions between users. This notification service is as quick as it can, to ensure again the best utilization feeling.

Offline Consistency :
Offline features are primordial, that’s why our backend has been developed in order to allow as many actions as it could, users being offline. This is remarkably handled with caching solutions that automatically send changes and requests made offline, as soon as the device is online again. This feature will allow users to use Partagix in their basement, without looking after rare wifi connections, and the application won’t let the user feel any connection lost.


## Data Model

The data management of the MVP is very primitive, as we focused on developing a complete and functional prototype for a Proof of Concept, and not on user data protection or database efficiency.

Our data management can be split into the following 4 steps:

- Firebase: The actual database that stores all our data, with the data of our different objects (users, items, loans, item categories) in Firestore, and all our images (user profile pictures, user-defined items pictures) in the “Storage” section.
  
- Our “Database.kt” class: A Kotlin class at the heart of our app, which acts as an interface between the Firebase functionalities (Firestore data tables and Storage images) and the other parts of our app that read or write data to and from the database.
  
- App Local Cache: Currently only used to cache images, this cache is used by the Database.kt class to reduce the number of calls to Firebase.
  
- ViewModels: Classes that act as an interface between the UI and the Database.kt class. This allows us to implement various data management mechanisms such as asynchronous database calls that do not freeze the main thread while waiting for the answer. ViewModels also perform new calls to the database if the user performs certain actions that require changing the elements we display (eg. filtering items). 

While the app currently doesn’t implement satisfactory data privacy and protection, the app was designed to make this possible with minimal changes once we are past the MVP and want to launch a product on the market. This is why the “Database.kt” file centralizes all data management: implementing a new, more robust data management only requires us to change this interface. 


## Security Considerations

## Infrastructure and Deployment

We will deploy the app on the play store and we will make it available early for users to try it and test it before the official launch. Once we have enough feedback, that we have implemented all the feedback we received, and that the app is bug free we will release it on the Play Store.


## Test Plan

How is the application developed, tested, and deployed?
Any special infrastructure requirements.

Plugin Tests Since we have a dynamic frontend client that can change views,
we should test frontend rendering for all plugins we can compose and support.

Performance Testing We should stress test the app based on the projected peak
traffic during different times of the day/week/semester.

