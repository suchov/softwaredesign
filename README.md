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
After discussing the data and the actions that a user can perform to inteact
with the system. The next step would be to talk about which type of DB will 
you use and why. For detailed direneces between SQL VS NoSQL - https://www.scylladb.com/learn/nosql/nosql-vs-sql/

4. High-level system design
Initialy start with very basic design

Extend the design - Creating specific components

Isolating the services - for easier scaling and traffic control

- Replicate the services and databases mention a signle poing of failure - https://www.youtube.com/watch?v=-BOysyYErLY
- Load balancer - Application side & Database side if needed - https://www.youtube.com/watch?v=K0Ta65OqQkY&list=PLMCXHnjXnTnvo6alSjVkgxV-VH6EPyvoX&index=4
https://www.educative.io/courses/grokking-modern-system-design-interview-for-engineers-managers
- Message Queques - Tight coupling to lose cuoupling / Synchronous to Asynchronous communication
https://aws.amazon.com/ru/sqs/
https://aws.amazon.com/ru/message-queue/benefits/
- Data Partitioning - Location-based, UserID based, - https://www.youtube.com/watch?v=5faMjKuB9bc&list=PLMCXHnjXnTnvo6alSjVkgxV-VH6EPyvoX&index=8
- Content Delivery network - To avoid round trips to the main server(reduces latency). https://www.youtube.com/watch?v=Bsq5cKkS33I
https://www.youtube.com/watch?v=dzzPP87zUq4
- Cache - Distributed cache and client-side cache(For faster read access)
https://www.youtube.com/watch?v=U3RkDLtS7uY
https://aws.amazon.com/ru/caching/
https://github.com/donnemartin/system-design-primer/blob/master/README.md#Cache

5. Additional components(optional)
These components can be added to the design if you have time left in the 
interview. Khnowihng about these components helps you answer any in-depth
follow-up questions. Generally, the components mentioned above will
suffice and also take most of your time in the interview. 

- Encryption (msgs) - for messaging services to secure data - https://www.arcserve.com/blog/5-common-encryption-algorithms-and-unbreakables-future
- Analytics service - for analyzing requests and user data.
- ML service - recommendation/news feed ranking(if use case (Netflix)
demands then add it to the basics components) - talk about
the data needeed for your recommendation/ranking model.
- API gateway - https://www.youtube.com/watch?v=TYw-lzL3-Kc, detailed microservices,
and API gateway - https://www.youtube.com/watch?v=5OMx4R9VT-0&list=PLkQkbY7JNJuDqCFncFdTzGm6cRYCF-kZO&index=6
- Service discovery - to dynamically identify microservices - https://www.youtube.com/watch?v=6dpcU3fnSBE

By following this template, any system can be designed in an interview. 

Design Questions

General services
1. Tiny URL: https://www.youtube.com/watch?v=JQDHz72OA3c https://www.educative.io/courses/grokking-modern-system-design-interview-for-engineers-managers/m753voqPO4O
2. PasteBin: https://www.youtube.com/watch?v=josjRSBqEBI&list=PLkQkbY7JNJuBoTemzQfjym0sqbOHt5fnV&index=31 
3. Search service: https://www.youtube.com/watch?v=CeGtqouT8eA
4. Type-ahead suggestion service: https://www.youtube.com/watch?v=xrYTjaK5QVM&list=PLkQkbY7JNJuBoTemzQfjym0sqbOHt5fnV&index=10 
5. Web crawler: https://www.youtube.com/watch?v=BKZxZwUgL3Y
6. API rate limiter: https://www.educative.io/courses/grokking-modern-system-design-interview-for-engineers-managers/g20qW9nP4yZ 
https://www.youtube.com/watch?v=xrizarXJgC8

Social media systems
1. Instagram: https://www.youtube.com/watch?v=QmX2NPkJTKg https://www.educative.io/courses/grokking-modern-system-design-interview-for-engineers-managers/RLnmBXMNpgL
2. Twitter: https://www.youtube.com/watch?v=wYk0xPP_P_8 
3. Facebook news feed: 

Cloud services
1. Google drive: https://www.youtube.com/watch?v=U0xTu6E2CT8 
2. Google docs: https://www.youtube.com/watch?v=2auwirNBvGg
3. Amazon S3: https://www.youtube.com/watch?v=UmWtcgC96X8

Video streaming 
Video is the main data and differnt formats of a video have to be stored.
Recommendation service is key here.

1. Netflix: https://www.youtube.com/watch?v=psQzyFfsUGU&list=PLkQkbY7JNJuBoTemzQfjym0sqbOHt5fnV&index=6
2. How Netflix onboards new movies: https://www.youtube.com/watch?v=x9Hrn0oNmJM

Online shopping:
1. Amazon: https://www.youtube.com/watch?v=EpASu_1dUdE

Messaging system
The difference between HTTP, long pooling, and WebSocets is important to
know for a messaging system - https://www.youtube.com/watch?v=GMlHsF1JmsE&list=PLpQ0aTOL-X-FqEaLF-nCzVRxICMlVNmwi&index=20

1. WhatsApp: https://www.youtube.com/watch?v=vvhC64hQZMk

Cab use cases
1. Uber: https://www.youtube.com/watch?v=umWABit-wbk

Video conferencing:
1. Zoom: https://www.youtube.com/watch?v=G32ThJakeHk

Restaurants review system
1. Yelp: https://www.youtube.com/watch?v=TCP5iPy8xqo

Dating apps
1. Tinder: https://www.youtube.com/watch?v=tndzLznxq40

Payment services 
What is payment gateway: https://www.youtube.com/watch?v=GUurzvS3DlY
1. PayPal

Gaming
1. Online multiplayer:
https://www.youtube.com/watch?v=EU81tjgoKoI
https://www.youtube.com/watch?v=K3Z1PY2vr3Q

Mangement system:
1. Ticker master: https://www.youtube.com/watch?v=lBAwJgoO3Ek 

Google maps: https://www.youtube.com/watch?v=jk3yvVfNvds



