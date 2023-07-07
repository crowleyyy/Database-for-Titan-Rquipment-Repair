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
  - `SerialNumber`
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

This stored procedure allows you to insert equipment information into the `Equipment` table. It takes the following parameters:
- `p_SerialNumber`
- `p_LastServiceDate`
- `p_LastServiceDone`
- `p_NextPNMDate`
- `p_NeedsParts`
- `p_PartName`
- `p_PartsArrived`
- `p_LocationID`

### InsertLocation

This stored procedure allows you to insert location information into the `Location` table. It takes the following parameters:
- `p_Name`
- `p_Address`
- `p_PhoneNumber`

### InsertServiceHistory

This stored procedure allows you to insert service history information into the `ServiceHistory` table. It takes the following parameters:
- `p_EquipmentSerialNumber`
- `p_ServiceDate`
- `p_ServiceType`
- `p_ServiceDescription`
- `p_ServiceNotes`

### InsertShipping

This stored procedure allows you to insert shipping information into the `Shipping` table. It takes the following parameters:
- `p_EquipmentSerialNumber`
- `p_ShippingDate`
- `p_ShippingFrom`
- `p_ShippingMethod`
- `p_TrackingNumber`
- `p_ShippingStatus`

## Indexing

The following indexes have been added to improve query performance:

- `Equipment` table:
  - Index on `SerialNumber`
  - Index on `LocationID`

- `Location` table:
  - Index on `Name`

- `ServiceHistory` table:
  - Index on `EquipmentSerialNumber`

- `Shipping` table:
  - Index on `EquipmentSerialNumber`

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
