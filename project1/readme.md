# eMovies Model Transformation

eMovies is a data model with Logical and Physical models that describe an outdated Movie rental service.

The purpose of this project is to rework the models into a modern format

**CTRL + Click on link to open in new TAB**

`Submission Video v1 BlackBoard`

<a href="https://bbhosted.cuny.edu/webapps/assignment/uploadAssignment?course_id=_2188140_1&content_id=_70625575_1&mode=DEFAULT&currentAttemptIndex=2&attempt_id=_141771406_1#" title="eMovies Reworked"><img src="https://github.com/adrianmnh/dm-vm/raw/mainBranch/eMovies/LOGICAL.jpg" alt="BlackBoard link" width=100px/></a>

`Submission Video v1 GoogleDrive`

<a href="https://drive.google.com/file/d/1CM1FJJYBrqyxCldJN0Mcd0Y1VMcKwdBe/view?usp=sharing" title="eMovies Reworked"><img src="https://github.com/adrianmnh/dm-vm/raw/mainBranch/eMovies/LOGICAL.jpg" alt="GoogleDrive link" width=100px/></a>

## Features of my Models

- [X] Includes a Conceptual Model
- [X] Includes a Logical Model
- [X] Includes a Physical Model
- [ ] Includes views to facilitate database usage
- [X] Multi-dimensional model layers to caputure how the business works by precisely representing business rules
- [ ] Model represents Navigation by capturing how the business is monitored
- [X] Multiple bridge tables allow multi-value attributes
- [X] PDM Tables are Normalized to 3rd normal form (3NF)
- [X] User defined domains for all attributes
- [X] Default values for non null attributes
- [X] Constraints for attributes
- [X] Different methods of payments, multi payment feature

### Conceptual Data Model without Payment entities
<img src="https://raw.githubusercontent.com/adrianmnh/dm-vm/mainBranch/project1/Diagrams/ConceptualModel.png" >

### Logical Data Model with multi-payment methods
<img src="https://raw.githubusercontent.com/adrianmnh/dm-vm/mainBranch/project1/Diagrams/LogicalModel.png" >

### Physical Data Model with Attributes and Columns
<img src="https://raw.githubusercontent.com/adrianmnh/dm-vm/mainBranch/project1/Diagrams/PhysicalModel.png" >
  

Business Definitions

- Employee - Employee is a hourly or salary worker for the company. Employees can have multiple positions within the company. May be responsible for their team having overseeing functions or non managerial positions
- Movie - A Movie is a film that can be streamed online from the Website or purchased in a store
- Store - a Store is a location where customers can buy physical movie formats, movie merchandise and memoribilia
- Customer - A customer is a person that can purchase items from a store, or stream from the website
- Inventory - A full list of ALL products and their description since inception
- Product - Products are merchandise that can be purchased
- Product Store - Individual products offered at a particular store location
- Franchise - A collection of movie titles. A brand or company that fully or partially owns the rights to distribute a movie title
- Movie Franchise - Lists the franchises a movie is part of
- Movie Stream - a Movie Stream is digital movie delivered to a customer via internet
- Employee Store - The employees who work for the store
- Order - an Order is placed at a store by a Customer and processed by an Employee
- Order Detail - Information about an order, the products, their price, quantity and discount
- Website - Movie Streaming License Manager and Distributer
- License - License to stream a movie.
- Movie License - The License to stream a specific movie
- Website Customer - The identifying information of a single web customer
- Customer Details - Personally Idenfiable Information about a customer
- Stream Status - The status for a stream, active or inactive
- Genre - List of movie genres
- Actor Producer Director - List of film actors, producers and directors legal names
- Genre Movie - The categories a film is calssified by
- Stage Name - The stage or industry name of actors and directors
- Stage Name Movie - Lists all the talent involved in the production of a film
- Category - The main product classification
- SubCategory - Product sub-classification
- Rating - Movie ratings
- Rating Movie - The ratings a movie has
- JobTitle - The job title of the talent in a film
- Credit Card - One of three ways our customers can pay for the books they purchase.
- Money Order - One of three ways our customers can pay for the books they purchase.
- Personal Check - One of three ways our customers can pay for the books they purchase.
- Payment - Business payments
- Order Payment - The payments relating to an roder
- Payment License - The payments relating to a License order trough the website


### Conceptual Data Model - Business Rules and navigation

* Customer - A person who can purchase/rent a digital movie copy, buy a physical copy from a store, or purchase movie memorabilia. Website account
* Store - The business physical store location, offers physical movie copies and movie memorabilia
* Employee - A person who works at the physical store or works remotely monitoring the website API
* Movie - A film that can be rented or purchased
* Product - A movie related product that can be bought from physical store
* Payment - One of the types of payment accepted by the business
* Bill - A record of purchase or rental from a store or website
* Employee Record - Details about employee
* Human Resources Schema - Information about employees.

### Logical Data Model
* Customer(Customer Id, First Name, Last Name, Phone Number, Email)
* Payment(Payment Type, Customer Id, CCNum, CCExp, SecurityCode)
* Store(Store Id, Address, City, State, ZipCode, Phone1, Phone2)
* StoreManager(Store Id, Employee Id)
* StoreEmployee(Empl Id, First Name, Last Name, Phone, Email, Manager)
* Movie(Movie Id, Title, Description, Rating, Genre, Stream, BlueRay)
* Product(Product Id, Description, Movie Id, Price)
* Inventory(Product Id, Quantity)
* Bill(Bill Id, Customer Id, StoreId, Date, Total, Payment Type)
* BillRecord(Bill Id, Product Id, Quantity)
* EmployeeRecord(Empl Id, Hire Date, Salary, SSN, Termination Date) 

### Physical Data Model

Customer
* Customer Id, integer, PK
* First Name, String
* Last Name, String
* Phone Number, Numeric(10)
* Email, String

Payment
* Payment Type, smallint, PK
* Customer Id, integer, PK
* CCNum, Numeric(16)
* CCExp, Numeric(4)
* SecurityCode, Numeric(3)

PaymentType
* PaymentId, smallint, PK
* PaymentDescription, String, Domain(credit card, check)

Store
* Store Id, smallint, PK
* Address, String
* City, String
* State, char(2)
* ZipCode, Numeric(5)
* Phone1, Numeric(10)
* Phone2, Numeric(10)

StoreManager
* Store Id, FK
* Employee Id, FK
* StoreEmployee
* Empl Id, integer, PK
* First Name, String
* Last Name, String
* Phone, Numeric(10)
* Email, String
* Manager, boolean

Movie
* Movie Id, integer, PK
* Title, String
* Description, String
* Rating, Domain(1,2,3,4,5)
* Genre, Domain(Multi-Genre)
* Stream, boolean
* BlueRay, boolean

Product
* Product Id, integer, PK
* Description, String
* Movie Id, FK
* Price, currency

Inventory
* Product Id, FK
* Quantity, integer

Bill
* Bill Id, integer, PK
* Customer Id, FK
* StoreId, FK
* Date, datetime
* Total, currency
* Payment Type, FK

BillRecord
* Bill Id, FK
* Product Id, FK
* Quantity, integer

EmployeeRecord
* Empl Id, FK
* Hire Date, date
* Salary, currency
* SSN, numeric(10), Masked
* Termination Date, date 
