My Own Database
Building my own database to store millions of arbitrary data.


Team Members
Weldon Kiprop - Sole participant in building the database.

Technologies

Libraries:
- a. For Database Management:
- SQLite: A self-contained, serverless, zero-configuration, transactional SQL database engine. It's widely used and comes with a C API.
- LMDB (Lightning Memory-Mapped Database): An ultra-fast, ultra-compact key-value data store developed by Symas Corporation.
- LevelDB: A fast key-value storage library written at Google.


Languages:
- a. Programming Language:
- C/C++: Most traditional databases are built using C/C++ due to their performance and low-level control.


Platforms:

a. Operating System:
- Linux: Many databases are built to run on Linux due to its stability, security, and open-source nature.


Hardware:

a. System Requirements:
- High-performance CPU: Depending on the scale and requirements of your database, you may need a CPU with multiple cores and high clock speeds.
- Sufficient RAM: The more RAM, the better for caching and indexing large datasets.
S- torage: Fast storage subsystem (SSDs preferred over HDDs).


Books and Resources:

a. Books:
- "Database Management Systems" by Ramakrishnan and Gehrke: It provides a comprehensive introduction to database systems.
- "Designing Data-Intensive Applications" by Martin Kleppmann: This book covers modern database technologies and concepts.

b. Online Resources:
- SQLite Documentation: For understanding SQLite database internals and usage.
- LMDB Documentation: For understanding LMDB database internals and usage.
- LevelDB Documentation: For understanding LevelDB internals and usage.
- Database Internals: Websites like "Database Internals" provide detailed information about the internal workings of various databases.


Challenge Statement
I ran into a problem where I needed to store millions of records of arbitrary data ranging from 1 KB-8KB, in the way that I can find, search, read, iterate through my data as quickly as possible, just like native disk access.






Risks
Technical Risks:
Performance Issues:
Potential Impact: The database may not perform optimally, leading to slow query execution and poor overall system performance.
Safeguards/Alternatives:
Conduct thorough performance testing at each stage of development.
Implement indexing and caching mechanisms to improve performance.
Consider parallel processing and optimization techniques.
Data Corruption:
Potential Impact: Data integrity could be compromised, leading to incorrect query results or even data loss.
Safeguards/Alternatives:
Implement robust transaction management and ACID (Atomicity, Consistency, Isolation, Durability) properties.
Use checksums and error detection mechanisms to detect and prevent data corruption.
Regularly backup the database to minimize the impact of data corruption.
Scalability Challenges:
Potential Impact: The database may not scale efficiently to handle growing amounts of data and increasing user load.
Safeguards/Alternatives:
Design the database with scalability in mind, using techniques such as sharding, replication, and partitioning.
Monitor system performance and scalability metrics regularly to identify bottlenecks and scalability issues early.
Non-Technical Risks:
Legal and Compliance Issues:
Potential Impact: Failure to comply with data protection regulations could result in legal action, fines, and damage to the organization's reputation.
Strategies to Prevent Negative Outcomes:
Ensure compliance with data protection regulations such as GDPR, HIPAA, etc., by implementing appropriate security measures and access controls.
Regularly audit the database system to ensure compliance with legal and regulatory requirements.




Budget Overruns:
Potential Impact: Exceeding the allocated budget could delay the project or result in incomplete implementation.
Strategies to Prevent Negative Outcomes:
Conduct a thorough cost analysis at the beginning of the project to estimate hardware, software, and labor costs accurately.
Monitor project expenses closely and identify potential cost overruns early to take corrective action.
Resource Constraints:
Potential Impact: Insufficient resources (e.g., skilled personnel, hardware, etc.) could delay the project or compromise the quality of the database system.
Strategies to Prevent Negative Outcomes:
Ensure adequate staffing with the necessary skills and expertise to develop and maintain the database system.
Allocate sufficient hardware resources to support the database's requirements, including CPU, RAM, and storage.




Infrastructure
Branching and Merging Strategy:
GitHub Flow:
Process for Branching and Merging:
Create feature branches for each new feature or bug fix.
Regularly push changes to the feature branch and open pull requests for code review.
Once the code is reviewed and approved, merge it into the main branch (or development branch if using a Gitflow-like approach).
Use a "pull request" model where changes are reviewed before merging into the main branch.
Advantages:
Simple and easy to understand.
Encourages frequent releases and collaboration.
Disadvantages:
May not scale well for larger teams or more complex projects.
Deployment Strategy:
Continuous Deployment (CD):
Strategy for Deployment:
Automate the deployment process to ensure rapid and reliable releases.
Use a CI/CD pipeline to build, test, and deploy changes automatically.
Deploy changes to a staging environment for testing before promoting them to production.
Implement feature flags to enable/disable features in production easily.
Advantages:
Enables rapid and reliable releases.
Reduces the risk of human error during deployment.
Disadvantages:
Requires significant upfront investment in setting up CI/CD pipelines.




Data Population Strategy:
Data Seeding:
Process for Populating the App with Data:
Use data seeding scripts or tools to populate the database with initial data.
Automate the data population process to ensure consistency and repeatability.
Use mock data for testing and development purposes.
Tools and Automation:
Use database migration tools like Flyway or Liquibase to manage database schema changes and seed initial data.
Use scripting languages like Python or Node.js to write data seeding scripts.
Advantages:
Ensures that the database is populated with consistent and meaningful data.
Automates the data population process to save time and effort.
Testing Strategy:
Test Automation:
Tools and Automation:
Use unit testing frameworks like JUnit (for Java), pytest (for Python), or Mocha (for JavaScript) to write and automate unit tests.
Use integration testing frameworks like Selenium or Cypress for end-to-end testing of the application.
Use code quality tools like SonarQube or CodeClimate to ensure code quality and adherence to best practices.
Process for Testing:
Write unit tests to test individual components and functions.
Write integration tests to test the interaction between different components/modules of the application.
Use test automation tools and CI/CD pipelines to automate the testing process.
Advantages:
Ensures that the application behaves as expected and meets the requirements.
Identifies bugs and issues early in the development process, reducing the cost of fixing them later.


Existing Solutions
I have not come across a similar solution to this.




















MVP Specifications
Architecture
MVP Diagram:





Description:

Database Server:

Description: Central component responsible for storing and managing data.

Functionality:

- Stores structured data in tables.
- Provides interfaces for data manipulation (insert, update, delete).
- Supports querying data using SQL (Structured Query Language).

Backend Server:

Description: Middle-tier component responsible for processing business logic and interacting with the database server.

Functionality:

- Handles client requests and responses.
- Executes business logic and application workflows.
- Communicates with the database server to fetch or manipulate data.




Client Application:

Description: Front-end component used by end-users to interact with the system.

Functionality:

- Provides a user interface for data input and presentation.
- Sends requests to the backend server for data retrieval or manipulation.
- Displays data to users in a human-readable format.

Data Flow:

- Data Input:
- Users interact with the client application to input data.
- The client application sends data input requests to the backend server.

Data Processing:

- The backend server receives data input requests from the client application.
- It executes business logic and application workflows.
- The backend server communicates with the database server to store or retrieve data.

Data Storage:

- The database server stores structured data in tables.
- It provides interfaces for data manipulation (insert, update, delete).
- Users can query the database server using SQL to retrieve data.


User Stories

As a user, I want to be able to register an account, so that I can access the system and store my data securely.

Acceptance Criteria:

- User should be able to provide their name, email, and password to register.
- User should receive a confirmation email upon successful registration.

As a user, I want to be able to add new data to the database, so that I can store and manage my information effectively.

Acceptance Criteria:

- User should be able to input data through a user-friendly interface.
- Data should be validated before being stored in the database.

As a user, I want to be able to view and search existing data in the database, so that I can retrieve information easily.

Acceptance Criteria:

- User should be able to view a list of existing data entries.
- User should be able to search for specific data entries using keywords.


As a user, I want to be able to update existing data in the database, so that I can keep my information up-to-date.

Acceptance Criteria:

- User should be able to edit data entries through the user interface.
Changes to data entries should be saved in the database.
- As a user, I want to be able to delete existing data from the database, so that I can remove outdated information.

Acceptance Criteria:

- User should be able to delete data entries through the user interface.
- Deleted data entries should be removed from the database permanently.








