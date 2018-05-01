# RestfulContactsManager
Simple CRUD WebAPI using Repository and Dependency Injection Patterns

Solution has been implemented using Database First Approach
Connect to the SQL Server Instance using SSMS and run below SQL

----------------
DATABASE SCRIPT
----------------

#1
CREATE DATABASE Contact;


Execute the following SQL Script
Use Contacts;
Go

CREATE SCHEMA Contacts

Create Table Contacts.ContactDetails
(
	ContactId  bigint IDENTITY (1,1) NOT NULL, 
	FirstName nvarchar(50),
	LastName nvarchar(50),
	Email nvarchar(256),
	PhoneNumber varchar(30),
	Status bit
);
Go

--Now add the clustered index
CREATE CLUSTERED INDEX CIX_ContactID ON Contacts.ContactDetails (ContactId);
GO

--Add some dummy Data to start with after creating the Database (not a mandatory required step)

--------
FEATURES
--------
1. Both RESTful Server (WebAPI) and MVC Client are part of the same solution (to confirm on WebAPI functionality)

2. Class ContactDetailsRepository implementes repository pattern

3. Class ContactDetailsController exposes REST APIs for performing CRUD on Contact Details

4. Dependency Injection has been implemented using Unity, UnityResolver and mapping the DI Types in WebApiConfig

5. Class ContactsManagerController is an MVC Client that invokes hosted Restful APIs

6. Please note Unit Tests for WebPI Controller and MVC Controller have not been included in this release
