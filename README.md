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

### GetEquipmentByID

This stored procedure retrieves equipment information by the provided `SerialNumber`.

### GetServiceHistoryBySerialNumber

This stored procedure retrieves service history information by the provided `SerialNumber`.

## Triggers

The database includes the following triggers:

### UpdateShippingStatus

This trigger adds a trigger called "UpdateShippingStatus" that automatically updates the `ShippingStatus` in the `Shipping` table when the `PartsArrived` value in the `Equipment` table is set to 'true'. The trigger calls the "AutoUpdateShippingStatus" function, which performs the update operation.

### UpdateEquipmentStatus

This trigger adds a trigger called "UpdateEquipmentStatus" that automatically updates the `PartsArrived` column in the `Equipment` table when the `ShippingStatus` value in the `Shipping` table changes. The trigger calls the "AutoUpdateEquipmentStatus" function, which performs the update operation.

## Error Handling

The stored procedures in the database include error handling to ensure proper handling of exceptions that may occur during data insertion. By using the `DECLARE EXIT HANDLER FOR SQLEXCEPTION` statement, the procedures are equipped to handle any SQL exceptions that might arise.

In case of an exception, the error handling section within each stored procedure allows for customized actions to be taken. Some common error handling practices include logging the error, rolling back the transaction, and displaying an error message to the user. You can customize the error handling section as per your specific requirements.

The error handling mechanism ensures that the database maintains data consistency and integrity, even in the event of unexpected errors during data insertion.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
