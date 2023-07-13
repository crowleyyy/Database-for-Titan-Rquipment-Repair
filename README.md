# Database For Titan Equipment Repair

Welcome to the Database For Titan Equipment Repair! This database is designed to manage information about forklift repairs and maintenance. It helps track forklifts, their service history, parts needed for repair, and shipping details.

## Database Structure

The database consists of the following tables:

<details>
<summary>Authentication Table</summary>
Users table:
- UserID (Primary Key)
- Username (Unique)
- Password
- Email
- CreatedAt
</details>

<details>
<summary>Equipment Table</summary>
Equipment table:
- SerialNumber
- LastServiceDate
- LastServiceDone
- NextPNMDate
- NeedsParts (ENUM: 'true', 'false', 'part ordered')
- PartName
- PartsArrived (ENUM: 'true', 'false', 'N/A')
- LocationID (Foreign Key)
</details>

<details>
<summary>Location Table</summary>
Location table:
- ID (Primary Key)
- Name
- Address
- PhoneNumber
</details>

<details>
<summary>Service History Table</summary>
ServiceHistory table:
- ServiceID (Primary Key)
- EquipmentSerialNumber (Foreign Key)
- ServiceDate
- ServiceType
- ServiceDescription
- ServiceNotes
</details>

<details>
<summary>Shipping Table</summary>
Shipping table:
- ShippingID (Primary Key)
- EquipmentSerialNumber (Foreign Key)
- ShippingDate
- ShippingFrom (Foreign Key)
- ShippingMethod
- TrackingNumber
- ShippingStatus
</details>

## Stored Procedures

The database includes the following stored procedures for inserting data into the respective tables:

- InsertEquipment: This stored procedure allows you to insert equipment information into the Equipment table.
- InsertLocation: This stored procedure allows you to insert location information into the Location table.
- InsertServiceHistory: This stored procedure allows you to insert service history information into the ServiceHistory table.
- InsertShipping: This stored procedure allows you to insert shipping information into the Shipping table.
  - **Modified**: When a shipping record is inserted using the InsertShipping procedure, it will check the corresponding Equipment record's PartsArrived column. If the value is 'N/A', indicating that the parts have not arrived yet, it will update the PartsArrived column to 'true'.
- InsertUser: This stored procedure allows you to insert user information into the Users table.
- GetEquipmentByID: This stored procedure retrieves equipment information by the provided SerialNumber.
- GetServiceHistoryBySerialNumber: This stored procedure retrieves service history information by the provided SerialNumber.

## Error Handling

The stored procedures in the database include error handling to ensure proper handling of exceptions that may occur during data insertion. By using the DECLARE EXIT HANDLER FOR SQLEXCEPTION statement, the procedures are equipped to handle any SQL exceptions that might arise.

In case of an exception, the error handling section within each stored procedure allows for customized actions to be taken. Some common error handling practices include logging the error, rolling back the transaction, and displaying an error message to the user. You can customize the error handling section as per your specific requirements.

The error handling mechanism ensures that the database maintains data consistency and integrity, even in the event of unexpected errors during data insertion.

Feel free to modify the error handling section of each stored procedure according to your application's error handling needs.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the Contributing file.

## License

The Database For Titan Equipment Repair is licensed under the MIT License.

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
