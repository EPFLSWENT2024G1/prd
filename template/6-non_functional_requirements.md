# Non-Functional Requirements

## Security, privacy, and data retention policies

Security:
Since users will log in with Google, we won't need to handle their credentials directly. However, we still need to ensure our database is secure, as it will store their contact information.

Privacy:
As we are being able to modify the profile picture of our items, the app we have access to the photos of the users. Moreover, our backend should be designed so that we should not save/extract or infer any
Personally identifiable information about a user, such as Name, Age, Gender, Address, etc. Because we only need a means of contact and a username to create your account, both of which will be given by your Google account

Data retention policies:
We should be viewed simply as a facilitator to lend/borrow items to others. This means that we need to keep a strict and well-defined policy around what user data we retain. For example, if we collect and retain all the loan information and user preferences and then we see that some users or a certain area always needs the same items we could send them targeted ads


## Adoptions, Scalability and Availability

Adoption:
- Users should have the option to enable push notifications to know when an item is requested or to be updated on their loan requests
  
- The application’s user interface must include easily accessible settings for customizing notification preferences.

Scalability:
- We expect the traffic to be rather low/medium all year long even around events there shouldn’t be too much events overlapping themselves so the loan request should not be too high. However, in case of high traffic the system should maintain optimal performance and response time.
  
Availability:
- The application must achieve a minimum uptime of 99.9%, ensuring consistent availability to users.
  
- Regular data backups and a robust disaster recovery plan must be in place to enable quick restoration of services in case of system failures


