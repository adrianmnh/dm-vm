# Data Modeling using ERwinDM on Azure Labs

## eMovies.erwin sample Data Models screenshots

Logical Data Model

<img src="https://github.com/adrianmnh/dm-vm/blob/mainBranch/eMovies/LOGICAL.png?raw=true" alt="eMovies outdated Logical Data Model">


Physical Data Model with Views

<img src="https://github.com/adrianmnh/dm-vm/blob/mainBranch/eMovies/PHYSICAL1.png?raw=true" alt="eMovies outdated Physical Data Model with Views">


Physical Data Model with Attributes and Columns

<img src="https://github.com/adrianmnh/dm-vm/blob/mainBranch/eMovies/PHYSICAL2.png?raw=true" alt="eMovies Physical Data Model with Attributes and Columns">


## Notes

* relational data modeling is the process of capturing how the business works by precisely representing business rules

* dimensional data modeling is the process of capturing how the business is monitored by precisely representing navigation

`Enterprise data model` **EXECUTIVE** - one-pager of terms, and business objects and rules
* business objects is an idea that is *fundamental* and *critical* to the organization
* business rule is a  definition of how business objects relate to each other
* edm correlates to an executive summary for an overview of the data landscape of the organization

`Conceptual data model` **Business Management** - scope and needs, leveraging understanding of EDM -> yields the need for a new solution
* The business objcts is a more detailed level a is relevant for the solution they are representing
* cdm correlates to a synopsis for an overview of the data landscape of a solution

`Logical data model` **ARCHITECT** - represents the business solution created from CDM. captures all of the details of the particular solution

* The scope of the logical data model is to provide a business-readable model of what business people require to understand the data landscape for a project and to generate the schema of the database.
* The logical data model uses a standard set of symbols to proreflect the cusiness objects as entities and the business rules as relationships

`Physical Data model` **Engineer** - after understand the business solution, move on to technical solution

* The scope of the pdm is to provide a technical view of the logical data model for technicians to be able to understand the requirements for a project.
* The pdm also makes use of a standard set of symbols to reflect the logical entities as tables and relationships as **deployable** indexes and constraints

### Logical Data Model (Relational)

Detailed business solution on business rules

### Logical Data Model (Dimensional)

Detailed business solution on navigation

Logical Data Model includes entities, attributes and relationships for a particular solution

### Physical Data Model

Detailed technical solution

### Changes I would make to eMovies Data models:

Tips:
- Starting with business objects and definitions
- Have spaces in between words CDM and LDM (easier transition -> physical)
- conceptual -> logical -> physical
- Use Bulk Editor

Physical Model with Attributes and Columns / With Views
- [X] CUST(Customer)
- [X] PAYMENT
- [X] EMP (Employee)
- [X] STORE
- [X] MOVIE_STORE
- [X] MOVIE_COPY
- [X] MOVIE
- [X] MO_RENT_REC
- [X] CUST_CREDIT
- [ ] CUSTOMER_INVOICE
- [ ] OVERDUE_NOTICE


To do:
- [ ] Remove physical store entities
- [ ] payment can be broken down into individual entities - creditcard, cash, check
- [ ] create schemas for the physical data models
- [ ] Add Tables to Schema -> Fully Qualified Table names in Physical Data Model
- [ ] normalize tables
- [ ] LDM has domains: user defined data types(domain driven modeling design)
- [ ] Attributes have to be PascalCase
- [ ] remove repeated attributes
- [ ] add streaming rental as well as physical

  