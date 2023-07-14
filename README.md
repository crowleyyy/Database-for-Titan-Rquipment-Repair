# Database For Titan Equipment Repair

Welcome to the Database For Titan Equipment Repair! This database is designed to manage information about forklift repairs and maintenance. It helps track forklifts, their service history, parts needed for repair, and shipping details.

## Database Structure

The database consists of the following tables:

### Authentication Table

- `Users` table:
  - `UserID` (Primary Key)
  - `Username` (Unique)
  - `Password`
  - `Email`
  - `CreatedAt`

### Equipment Table

- `Equipment` table:
  - `SerialNumber` (Primary Key)
  - `LastServiceDate`
  - `LastServiceDone`
  - `NextPNMDate`
  - `NeedsParts` (ENUM: 'true', 'false', 'part ordered')
  - `PartName`
  - `PartsArrived` (ENUM: 'true', 'false', 'N/A')
  - `LocationID` (Foreign Key)

### Location Table

- `Location` table:
  - `ID` (Primary Key)
  - `Name`
  - `Address`
  - `PhoneNumber`

### Service History Table

- `ServiceHistory` table:
  - `ServiceID` (Primary Key)
  - `EquipmentSerialNumber` (Foreign Key)
  - `ServiceDate`
  - `ServiceType`
  - `ServiceDescription`
  - `ServiceNotes`

### Shipping Table

- `Shipping` table:
  - `ShippingID` (Primary Key)
  - `EquipmentSerialNumber` (Foreign Key)
  - `ShippingDate`
  - `ShippingFrom` (Foreign Key)
  - `ShippingMethod`
  - `TrackingNumber`
  - `ShippingStatus`

### Users Table

- `Users` table:
  - `UserID` (Primary Key)
  - `Username` (Unique)
  - `Password`
  - `Email`
  - `CreatedAt`

## Stored Procedures

The database includes the following stored procedures for inserting data into the respective tables:

### InsertEquipment

This stored procedure allows you to insert equipment information into the `Equipment` table.

### InsertLocation

This stored procedure allows you to insert location information into the `Location` table.

### InsertServiceHistory

This stored procedure allows you to insert service history information into the `ServiceHistory` table.

### InsertShipping

This stored procedure allows you to insert shipping information into the `Shipping` table.

### InsertUser

This stored procedure allows you to insert user information into the `Users` table.

### UpdateUserPassword

This stored procedure allows you to update the password of a user in the `Users` table.

### DeleteUser

This stored procedure allows you to delete a user from the `Users` table.

## Triggers

The database includes the following triggers:

### UpdateShippingStatus

This trigger adds a trigger called "UpdateShippingStatus" that automatically updates the `PartsArrived` column in the `Equipment` table when the `ShippingStatus` value in the `Shipping` table changes.

### UpdateEquipmentStatus

This trigger adds a trigger called "UpdateEquipmentStatus" that automatically updates the `PartsArrived` column in the `Equipment` table when the `ShippingStatus` value in the `Shipping` table changes.

## Constraints

The database includes the following constraints:

- `ck_LastServiceDone` CHECK constraint on `Equipment` table to ensure that `LastServiceDate` and `LastServiceDone` are both NULL or both NOT NULL.
- `ck_NextPNMDate` CHECK constraint on `Equipment` table to ensure that `NextPNMDate` is not earlier than the current date.
- `ck_ServiceDate` CHECK constraint on `ServiceHistory` table to ensure that `ServiceDate` is not later than the current date.
- `ck_ShippingDate` CHECK constraint on `Shipping` table to ensure that `ShippingDate` is not later than the current date.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
