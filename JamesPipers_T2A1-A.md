# T2A1-A - Workbook

#### Q1 Describe the architecture of a typical Flask application
---

A typical flask application is designed to be both lightweight and easily customizable to suit a variety of web designer’s needs. Most commonly a flask application will be organised keeping the Model-View-Controller (MVC) model in mind and separating each components accordingly within the program structure. 

To name a few of the components that we might see within the app, we have the app itself, models, views, schemas, controllers, commands, and configuration files. 

The app itself will be separated into its own file and draw on these resources when needed for operation. This is the central component pulling all the resources into it for use. 

The Model represents the application data and business logic. Using an object relational mapping (ORM) tool such as SQLAlchemy, model structures will be grouped together and a new file made for each table built.

The Viewing layer of the application is responsible for user interface. This portion will take user requests, process these requests to the controller and provide HTTP responses. Essentially this will be the portion that is visible to the user, and they will interact with on a day to day. 

The Controller portion of the application will process the user input in a specific way depending on the route accessed. Blueprints will be used to organise routes under a domain of functionality making it easier to scale up the application. In flask decorators are used to map these routes. Each of these routes will take the request from the viewing layer, process it and then return the response to the view of the consumer. A tool is needed to ensure that this data is valid and converted appropriately up to viewing layer and this is where schemas come in. By using a tool like marshmallow to build schemas, data can be validated and de-serialized into Json for the viewing layer to manipulate. Each Schema and controller is separated into it's own documentation and groups accordingly to provide a clear reference if the code needs to be adjusted.

Commands are designed to interact with the terminal for creating, seeding, or dropping the database if required. Configuration files hold information regarding environment that the application is currently running in and encryption control. it is important to keep the configuration files secure and separate from the main application. In development environments a general outline of how these environment variables is written but the actual information is held in confidence for security reasons.

---
### Q2	Identify a database management system (DBMS) commonly used in web applications (including Flask) and discuss the pros and cons of this database
---

PostgreSQL is an open-source database management system that is known for its robust nature and reliability. It is a relational database model that has both pros and cons just like many of the other systems used in the industry. 

PostgreSQL is ACID compliant. Having Atomicity, Consistency, Isolatable, and Durability. Atomicity meaning that each transaction that occurs can be broken down into smaller subparts that could be dependent on one another. Consistency implies that the database only functions when following the validation rules set. By using constraints such as unique, primary key, nullable field settings and only specific response types, the model is able to constrain input and retain integrity within the server. Isolation referring to the ability to simultaneously perform transactions into the database that won't affect each other. Postgres uses Multi-Version Concurrency Control to do this. Finally, durability refers data loss measures that minimize risks of data loss for example, saving transactions at the time of completion.

Postgres is flexible in its data typing giving a large array and selection for the user to work with. The community that supports the use of the database is extensive as well providing a large array of open-source documentation and third-party extensions. This comes with the benefit of good support in terms of troubleshooting issues. Of highlight PostgreSQL handles large datasets and high workloads well, offering good solutions for scalability.

 On the negative side there is a steep learning curve for newcomers in comparison to other database systems that are available. It is resource intensive, especially in regard to the use of RAM. The backwards compatibility of the system is usually ok but when planning out version upgrades careful planning and testing needs to take place. Although as mentioned earlier community support is great, commercial support offered for this product is not nearly as strong as some other databases available on the market such as Oracle. If the build requires use of a NoSQL database PostgreSQL would not be the optimal choice as the support for this is quite limited.

 In conclusion, Postgres has many strong points that would cement its position and use in larger scale operations. However, in terms of fit the project, if a simpler database solution is required the downsides like the RAM commitment and potential need for extensive database administration may not make it the best fit.  


---
### Q3 Discuss the implementation of Agile project management methodology
---

The Agile methodology essentially involves the process of a series of smaller development cycles known as sprints over an extended period. The methodology provides flexibility for implementing ongoing changes and has extensive opportunity for feedback to adapt the project. Alternative models for management such as the waterfall model suffer without this flexibility making Agile the more suitable solution if parameters or end goal are not clearly defined. It also gives us multiple points of exit to the project so that we can push the product for early released if need be to cut back on costs, etc. 

Agile is broken down into multiple stages involve planning, designing, developing, testing, releasing and then giving feedback. By planning we are choosing which user stories to work on and putting them into a backlog of tasks to restrict the workload for the current sprint cycle. This involves prioritization of more important tasks to ensure functionality sooner rather than later. Designing involves sketching out a rough plan for how each user story will be implemented in the product. This could involve further elaboration from the user stories side or UI design processes that detail out the vision of those stories. Development is the step by which code is written. Testing will involve validation of the coding step to make sure it works. Tests can be automated or human driven depending on the requirement for the created implementation. Release is different from testing in the life cycle in that it provides a more liberal use to a larger audience, whether this be beta testers or otherwise. Feedback is where more user stories are gathered and then the process will loop back into planning phase.

In conclusion Agile projects are highly adaptable and focuses on the collaborative efforts of different team members and repeated testing to provide a quality product that evolves over time.




---
### Q4 Provide an overview and description of a standard source control workflow
---

Source control, alternatively known as Git workflow or version control workflow, outlines the steps for managing changes in source code while collaborating as a team to complete a project. There are a few different methodologies but for our purposes, let's look at feature branch workflow.

First, we need a source repository that will house the bulk of the project. A Cloud based hosting websites such as GitHub and Gitlab provide a central online remote repository for the team to access during the development phase and beyond. Each team member will clone this repository to create a local copy of the code on the main branch of their own independent machine. From here they log out of the main or master branch and create a sub-branch to modify the code. During the modification step multiple commits describing what has been completed will be made to avoid loss of progress. Once they are done the remote repository will be cloned again back onto the main branch. By doing this any changes the rest of the team may have made to the code in the meantime can be compared for conflicts and adjusted for before pushing the branch to the remote repository for review. If the code passes review it will be either merged or a rebasing of the code will occur on the main development branch. This cycle continues over the development life cycle to produce multiple iterations of the code for the product and document all stages of the changes that are occurring. 
 
 The basic goal of git workflow is to provide a robust history of all changes and allow for collaborative workflow to improve efficiency and quality of output. Feature branch workflow in particular performs well to achieve this basic goal but can be adapted depending on team requirements.

---
### Q5 Provide an overview and description of a standard software testing process (e.g. manual testing)
---

Testing processes will occur toward the later end of the agile project management and deliver feedback for improvement of future interations. We will look at Manual testing as it involves the human aspect of evaluating the project changes. 

Human testers will evaluate the behaviour of the software, execute tests for functionality and provide feedback to the development team for improvement. A diverse tester base and different machine configurations should be used to cover a variety of case scenarios. Tests will need to be created that focus on evaluating the implemented changes in the current interaction. They will often include a step-by-step input followed up with an expected output the the tester should receive. This limits the scope of testing to ensure that the current implementations are functional and any defects or direct issues as a result can be fixed prior to release. Test users will be expected to document their findings for future reference as well. 

Human or manual testing is meant to evaluate the real-user interaction with the program as there is many things that can be missed in an automatic, code-based testing solution. However, it can be time consuming. A combination of automatic and manual testing would be the best approach to ensure that the product is up to par upon release. 


---
### Q6 Discuss and analyse requirements related to information system security and how they relate to the project
---

Good system security measures will ensure data integrity, confidentially of users and provide availability of data to those that need it. In relation to the project, authentication will be the key to ensure that base of operation is successful. Processes will need to be implemented to ensure that those accessing the application will only perform actions that they are allowed to and good authentication will cover this. With proper data encryption techniques the authentication of each user can be well protected as well.

Authentication methods should be multi-layered to provide different levels of access across the application. With authentication it is important that any passwords or sensitive data is encrypted during the running of the application including when the data is in storage, transmission and/or being processed. We could look at ensuring that data is transmitted through HTTPS and that we are using the relevant tools within the application we build to ensure encryption is acheived at each of these stages. 

Audit trials and logs need to be kept and in the best interest it would be wise to look at and determine what information should be retained and stored long term. We will also need regularly review any vulnerabilities that may become present in the application and resolve them, apply security patches and updates where necessary. In light of this point it would be pragmatic to create backup storage in case the system is breached and set up a recovery plan to cope with any failures.

 Training should be provided to all users to facilitate awareness of any potential security risks that may affect them, particulary in the case of passwords. An example of this might be prompt users to use more varied characters in their passwords or change them more frequently. 
 
 In short all these aspects are fundemental in the project design and implemenation. They will help safeguard company assets and should be reviewed and considered over the life of the project. These reviews should be done working closely with stakeholders and security experts to ensure that security levels are appropriately met.  

---
### Q7 Discuss common methods of protecting information and data and how you would apply them to the project
---
Data protection plays an important role in maintaining confidentiality of users and integrity of database resources for the project. Common methods that provide data protection include, access controls, encryption, data backups and audit logs to name a few. 

It would be best to authorize specific personnel to access portions of the data set based on their roles within the organisation. In some cases, a multi-factor authentication may be required if the user situation is not within the norm, example being the MAC address of the user has changed from normal so a text message will be sent to the user with an additional authentication key to gain access. These access controls for each role should be regularly reviewed to ensure that only the minimum access level is given to a role for the task that needs to be performed. This could prevent disclosure of sensitive data to parties that don't need to see it.

Data encryption will be applied to data in transit and data that stays at rest in the database. A separate master key for decryption will be kept in a secure location to decode the encrypted data only at the time of need and by authorized parties.

In the case of breach or system failure it is important that a backup of data be kept. This is also important in the case of physical storage and a cloud-based solution alongside a physical one should work well to combat any issues. 

Audit logs of transactions passing through the server should also retained and monitored regularly for suspicious activity. they should be maintained in a separate tamper-evident repository to ensure integrity.

Regular review and updates to security measures are essential to adapting to evolving threats and keeping the projects data and resources safe over the long-term. 



---
### Q8 Research what your legal obligations are in relation to handling user data and how they can be met for the project
---

The legal obligations can vary depending on the juristiction but the mostly cover the same basic principles. In australia for example we would need to ensure that our customers are protected from theft, misuse, inteference, loss, unathorised access, modification and/or disclore. 

Additionally, if the information a customer is no longer needed on the database it is a requirement that we destroy it in a secure way. Minimizing the amount of sensitive data required would be benificial in meeting legal obligations. In gathering of any data we need to communicate our intention with the user. This will give them the opportunity to withdraw their consent which we need to allow at any stage of the use on the project. In line with this we should allow the user access to their own information as this is a right they need to have.

On the backend we need to ensure that a breach plan is layed out in to quickly respond to incidents and notify authorities of incidents. If legal issues present themselves it is important that documentation is well detailed and we should audit this regularly to ensure compliance.

We also need to consider that our legal obligations could change over time so it is crucial that we stay informed with regard to this field. Compliance will build trust with the user base as well as protect data.


---
### Q9 Describe the structural aspects of the relational database model. Your description should include information about the structure in which data is stored and how relations are represented in that structure.
---
A relational database needs to include several tables that are connected by relationships. 

Each Table will include columns, also known as attributes, that specify the property of the data within the vertical dimension below it. Columns specify the data typing such as text, date, integers, Boolean values etc. as well as introduce different types of data constraints such as the inclusion or exclusion of nullable values. This provides better integrity to the data set. 

Each row represents an entry or record of data. They will have an identifier known as a primary key attached to them to provide uniqueness to each entry. By using this primary key, relationships between different tables can be established. This is typically done by incorporating the primary key as the foreign key into a different table of the database for example, in a one-to-one or one-to-many relationship this occurs. However, in a many-to-many relationship an additional table to retain uniqueness of each data entry is required. By keeping each piece of data in its own persistent table normalization is achieved essentially eliminating redundancy and ensuring data integrity. 


---
### Q10 Describe the integrity aspects of the relational database model. Your description should include information about the types of data integrity and how they can be enforced in a relational database.
---
Data integrity is the method by which accuracy, completeness, validity, and consistency is maintained with the database. Let's consider three different types of data integrity: entity integrity, referential integrity and domain integrity. 

Entity integrity within the database involves the creation of a primary key alongside each new record. This ensures that every entry is distinct preventing duplication of a data piece and allows a linking via relationships. By setting up a primary key for each tables creation entity intregrity is mostly resolved as an issue.

Referential integrity involves the connection or relationships established between tables and ensures that each connection is complete. Take 2 tables one called customers, and another called orders. To have good referential integrity the database will reject the creation of an order entry if the customer id used does not link to a customer in the customer’s table. To enforce this kind of protection in a database, certain elements should be set to delete on cascade if they are ever removed. Following the customer, order model established earlier for example, you would delete all the order entries when a customer is removed.

Domain integrity is commonly implemented to protect different columns of data. For example, you can limit the amount of characters in a description, set specific values that could be entered, prevent columns from being left blank or even set constraints on sales cost to prevent excessive discounts. This works to keep the data in line with the company requirements and policies and makes sure that when interacting with different components of the model it can filter the data appropriately. These can easily be set up within the models when defining column characteristics. 

Proper implementation and enforcement of constraints is crucial for maintaining the quality and reliability of the database over the long-term.


---
### Q11 Describe the manipulative aspects of the relational database model. Your description should include information about the ways in which data is manipulated (added, removed, changed, and retrieved) in a relational database.
---

Objects are manipulated in a relational database model using SQL (Structured Query Language) commands and operations. 

To add data to the data model you would use the INSERT statement followed by the table name, table headers and the relevant information to be inserted into the given table. This creates a new entry within the specified table. The user will give this data via the view port and the API will convert into SQL and add the record. An example is as below.

```
INSERT INTO Users (UserID, UserName, Email, DOB)
VALUES (1, 'john', john@email.com', 5/02/2023);
```
To remove data the DELETE statement is used. This will delete entire records and in the case where this data is linked via a delete cascade will delete data from other tables as well. To ensure the correct data is deleted the statement needs to be linked with a WHERE clause otherwise some serious damage can happen. For example the below will delete the all entries where the users name is john. Add additional clauses or delete by user ID to would be prefered to prevent this issue. 

```
DELETE FROM Users
WHERE UserName = 'John';
```

To change or update data, use the UPDATE statement. This will modify a specific entries values and fucntionally serves to fix issues of misinformation, price changes or other user needs. An example as below targets the table and columns that need to be updated as well as the new value where the requirement of the WHERE clause is met.

```
UPDATE Users
SET UserName = 'Steve'
WHERE UserID = 1;
```
To retrieve data the SELECT statement is used. Multiple clauses can be added alongside this statement to properly filter the data and provide feedback to the user. Clauses can include but are not limited to WHERE, ORDER BY, GROUP BY and JOIN. It is also possible in the retrieval of this data to perform mathematical operations to analysis the data for the user to review. Examples of aggregate functions that do this include SUM, AVG or COUNT. The return of data using the select statement is also not limited to a single table and can be manipulated using the JOIN operation during the call of the statement. An example as below looks at all of these functions working in concert to return the total length of fish a user of the platform was able to catch.

```
SELECT u.UserName, SUM(f.Length) AS TotalFishLength
FROM Users u
LEFT JOIN Fish f ON u.UserID = f.UserID
GROUP BY u.UserName;
```

---
### Q12 Conduct research into a web application (app) and answer the following parts:

I've conducted research into the Trello web application to review for this question. It is basically a visual tool used to manage projects and workflow.

  a. List and describe the software used by the app.

* HTML and CSS - Render the visual interface used for the application.
* JavaScript - A programming language known to be used in web development to add interactivity to webpages. It is a versatile and high-level language. 
* CoffeeScript - A smaller language that compiles code into readable JavaScript. Considered easier to write than Javascript.
* Backbone.JS - JavaScript library that allows structuring the visual information of the application client side.
* Mustache - A logic-less templating language using pre-written text to design templates for the viewpoint.
* Node.JS - a backend cross-platform JavaScript runtime environment that supports multiple simultaneous requests.
*HAProxy - A software used to balance server load across multiple servers.
* REDIS - In memory storage structure used for caching data.
* MongoDB - a noSQL database model that stores objects in Json. The non-conforming data structure indexes data in a hierarchical way to provide a quick and powerful response time for client queries.
* Git version control - Hosting of software versions are available on Github. Used to provide record of changes and public support to the project for future development.


  b. Describe the hardware used to host the app.

Trello like most web applications, relies on cloud-based infrastructure to host the application. This provides a level of flexibility when scaling the application that physical storage would not allow for at such a rapid pace. Virtual Servers would be needed to host the run-time environment. Cloud storage would be required for the REDIS caching and MongoDB database setup. The application would need to access a networking infrastructure with routers, switches and firewalls that are designed to manage this load. A separate storage would probably be allocated to keeping logs and logging tools.

It may also be possible that the team keeps a physical storage somewhere in case disaster strikes they have a recovery plan in place.



  c. Describe the interaction of technologies within the app

The front-end viewport is rendered using a combination of HTML and CSS, HTML to define the structure and CSS to define style. JavaScript gets mixed into this and provides functionality and interactivity. Backbone.Js helps to structure and organise JavaScript client side and complements it by providing a framework for managing relationships. The JavaScript with the help of backbone.JS can use the templates made through Mustache to render out the HTML dynamically based on server data and user interactions. Note that most of this JavaScript code would be written using coffee script and then compiled into JavaScript to make the development cycle quicker. 

In the backend of the operation, we see Node.JS interacting taking in any of the requests from the front end and processing it to the relevant data model. It interacts with the REDIS caching system in favour of the MongoDB for quicker load times. Node.js will also interact with the MongoDB to perform CRUD operations to the primary data storage. During the development cycle we'll see any changes made throughout this ecosystem of control being tracked via git version control. 

  d. Describe the way data is structured within the app

Data in MongoDB is organised into collections of documents that are stored as Json like objects. Each collection or entity receives a unique identifier that allows the MQL (Mongo Query Language) to access them. For example, in the case of the Trello application we could include collections the boards, lists or cards. Multiple cards would be mapped to a single list and multiple lists mapped to a single board. This builds associations are constructed in a hierarchical way making it quicker and more efficient to retrieve large volumes of data.

  e. Identify entities which must be tracked by the app

* Boards - They are a top-level representation of the projects, teams, or topics. Each of the boards contains multiple lists associated with the project.
* Lists are used to categorize and organise the different tasks that could be given through cards. In the workflow these are often represented with a 'to do' or 'in progress' to denote the current stage of completion.
* Cards - these are the individual task that need to be achieved. they will often include descriptions and due dates for completion.
* Users - Individual records for the consumers of the Trello application. would include email addresses, names etc. and most likely hold more sensitive data to the individual.
* Comments - timestamped changes made to a card that let team members see changes that happen for collaboration.
* Attachments - added files, links, images for enhancing the information.
* Activity history - a log of recorded changes made to cards, boards, list etc.
* Teams or organisations - a top level entity in the hierarchical structure for business class or enterprise users.
* Notifications - tracks updates and changes that inform users about activity on the board.

  f. Identify the relationships and associations between the entities you have identified in part (e)

Due to the hierarchical structure of most of the database the relationships within the data set can be obvious but there are a few that aren't.

Boards share a one-to-many relationship with the lists and the lists share a one-to-many relationship with the cards. This is the basic setup for the overall vision. Users are then setup in a many to many relationships with the boards allowing an interaction where they can modify different list and cards depending on what they are associated with. 

Comments, attachments, and activity history are all related to the cards in a one-to-many relationship where one card can have many of each of these. Teams and organisations have a one-to-many relationship with the boards and finally notifications serve a many to many relationships with the user providing feedback on multiple boards and cards.


  g. Design a schema using an Entity Relationship Diagram (ERD) appropriate for the database of this website (assuming a relational database model)
  ---
Note that this application does not use the relational database modelling but if it did, for brevity the relationship model would look like the below.

![relationship model](./trello%20ERD.png)


  ---






resources


  https://mariadb.com/resources/blog/acid-compliance-what-it-means-and-why-you-should-care/

  https://builtin.com/data-science/data-integrity

  https://business.gov.au/online/cyber-security/protect-your-customers-information

  https://medium.com/codex/what-technologies-are-used-at-netflix-70bf6166be8e#:~:text=At%20the%20core%20of%20Netflix's,large%2C%20distributed%20systems%20like%20Netflix's.

  https://github.com/trello

  https://blog.trello.com/the-trello-tech-stack#:~:text=for%20AJAX%20polling.-,REDIS,all%20of%20them)%20are%20lost.

  https://app.diagrams.net/
