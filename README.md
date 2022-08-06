#Scripts
---------
USE roxteste -- carregar primeiro a base de dados.

CREATE TABLE dbo.salesorderdetail (
SalesOrderDetailID    INT  NOT NULL,
SalesOrderID          INT  NOT NULL,
CarrierTrackingNumber VARCHAR(45) NOT NULL,
OrderQty              INT NOT NULL,
ProductID             INT NOT NULL,
SpecialOfferID        INT NOT NULL,
UnitPrice             INT NOT NULL,
UnitPriceDiscount     DECIMAL (2,2) NOT NULL,
LineTotal             VARCHAR(250) NOT NULL,
rowguid               VARCHAR(120) NOT NULL,
ModifiedDate          DATETIME NOT NULL,
CONSTRAINT PK_salesorderdetail PRIMARY KEY (SalesOrderDetailID,SalesOrderID)
);
-------------------------------------------------
CREATE TABLE dbo.salesorderheader(
SalesOrderID                 INT NOT NULL,
RevisionNumber               INT NOT NULL,
OrderDate                    DATETIME NOT NULL,
DueDate                      DATETIME NOT NULL,
ShipDate                     DATETIME NOT NULL,
Status                       INT NOT NULL,
OnlineOrderFlag              INT NOT NULL,
SalesOrderNumber             VARCHAR(45) NOT NULL,
PurchaseOrderNumber          VARCHAR(45) NOT NULL,
AccountNumber                VARCHAR(45) NOT NULL,
CustomerID                   INT NOT NULL,
SalesPersonID                INT,
TerritoryID                  INT,
BillToAddressID              INT,
ShipToAddressID              INT,
ShipMethodID                 INT NOT NULL,
CreditCardID                 INT,
CreditCardApprovalCode       VARCHAR(45),
CurrencyRateID               VARCHAR(4),
SubTotal                     INT NOT NULL,
TaxAmt                       INT NOT NULL,
Freight                      INT NOT NULL,
TotalDue                     INT NOT NULL,
Comment                      VARCHAR(45),
rowguid                      VARCHAR(45) NOT NULL,
ModifiedDate                 DATETIME NOT NULL,
CONSTRAINT PK_salesorderheader PRIMARY KEY (SalesOrderID)
);
-------------------------------------------------
CREATE TABLE dbo.SpecialOfferProduct(
SpecialOfferID                       INT NOT NULL,
ProductID                            INT NOT NULL,
rowguid                              VARCHAR(200) NOT NULL,
ModifiedDate                         DATETIME,
CONSTRAINT PK_SpecialOfferProduct PRIMARY KEY (ProductID,SpecialOfferID)
);
--------------------------------------------------
CREATE TABLE dbo.Product(
ProductID                      INT NOT NULL,
Name                           VARCHAR(45) NOT NULL,
ProductNumber                  VARCHAR(45) NOT NULL,
MakeFlag                       INT NOT NULL,
FinishedGoodsFlag              INT NOT NULL,
Color                          VARCHAR(45),
SafetyStockLevel               INT NOT NULL,
ReorderPoint                   INT NOT NULL,
StandardCost                   INT NOT NULL,
ListPrice                      INT NOT NULL,
Size                           VARCHAR(45),
SizeUnitMeasureCode            VARCHAR(45),
WeightUnitMeasureCode          VARCHAR(45),
Weight                         VARCHAR(45),
DaysToManufacture              INT NOT NULL,
ProductLine                    VARCHAR(45),
Class                          VARCHAR(45),
Style                          VARCHAR(45),
ProductSubcategoryID           VARCHAR(8),
ProductModelID                 VARCHAR(8),
SellStartDate                  VARCHAR(100),
DiscontinuedDate               VARCHAR(15),
rowguid                        VARCHAR(45) NOT NULL,
ModifiedDate                   DATETIME NOT NULL,
CONSTRAINT PK_Product PRIMARY KEY (ProductID)
);
-----------------------------------------------------
CREATE TABLE dbo.Customer(
CustomerID                     INT NOT NULL,
StoreID                        INT,
TerritoryID                    INT NOT NULL,
AccountNumber                  VARCHAR(45) NOT NULL,
rowguid                        VARCHAR(150) NOT NULL,
ModifiedDate                   DATETIME NOT NULL,
CONSTRAINT PK_Customer PRIMARY KEY (CustomerID)
);
-------------------------------------------------
CREATE TABLE dbo.Person(
BusinessEntityID         INT NOT NULL,
PersonType               VARCHAR(2) NOT NULL,
NameStyle                INT NOT NULL,
Title                    VARCHAR(10),
FirstName                VARCHAR(45) NOT NULL,
MiddleName               VARCHAR(45),
LastName                 VARCHAR(45) NOT NULL,
Suffix                   VARCHAR(4),
EmailPromotion           INT NOT NULL,
rowguid                  VARCHAR(150) NOT NULL,
ModifiedDate             DATETIME NOT NULL
CONSTRAINT PK_Person PRIMARY KEY (BusinessEntityID)
);
