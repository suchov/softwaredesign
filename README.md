# System design template for interviews

1 Requirements

## Functional

What fucntionalities can the system or application provide to the user?
Example: In Twitter, a user can follow another user, tweet, like a tweet,
retweet other's tweet, and share a tweet(focus on the essential features and  
do not delve the complex features of Twitter)

## Non-functional

Mandatory to know CAP theorem: https://mwhittaker.github.io/blog/an_illustrated_proof_of_the_cap_theorem/

For any distributed system, the following are the fundamental consepts to consider:

*High avaliability:* Most of the system must be highly avaliable.
*Consistency:* The system with high avaliability will have eventual
consistency. Any banking system favors consistency over avaliability
as there cannot be discrepancies in data(account balance).

*Reliability:* No loss of user data.

*Latency:* Response time of a user action such as loading a web page,
linking a post, etc.

2 Storage estimations
*Based on the data modality:* A rough estimate of how data must
be stored - To know what type of database can be used and file
storage for storing images/videos.

*The number of requests to the service:* To know how to scale the
services. A service that is read-heavy can be scaled to handle high
traffic of requests.

*Read Write ratio:* Determines whether the system is read-heavy or not.

3. Database design


