# Database For Titan Equipment Repair

Welcome to the Database For Titan Equipment Repair! This database is designed to manage information about forklift repairs and maintenance. It helps track forklifts, their service history, parts needed for repair, and shipping details.

## Database Structure

The database consists of the following tables:

### Authentication Table

- `Users` table:
  - `user_id` (Primary Key)
  - `username`
  - `password`

### Equipment Table

- `Equipment` table:
  - `serial_number` (Primary Key)
  - `last_service_date`
  - `last_service_done`
  - `next_pnm_date`
  - `needs_parts` (ENUM: "True", "False", "Part ordered")
  - `parts_name`
  - `parts_arrived` (ENUM: "True", "False", "N/A")
  - `location_id` (Foreign Key)

### Location Table

- `Location` table:
  - `location_id` (Primary Key)
  - `name`
  - `address`
  - `phone_number`

### Service History Table

- `ServiceHistory` table:
  - `service_id` (Primary Key)
  - `equipment_serial_number` (Foreign Key)
  - `service_date`
  - `service_type`
  - `service_description`
  - `service_notes`

### Shipping Table

- `Shipping` table:
  - `shipping_id` (Primary Key)
  - `equipment_serial_number` (Foreign Key)
  - `shipping_date`
  - `shipping_from` 
  - `shipping_method`
  - `tracking_number`
  - `shipping_status`

## Stored Procedures

The database includes the following stored procedures for inserting data into the respective tables:

### InsertEquipment

This stored procedure allows you to insert equipment information into the `Equipment` table. It takes the following parameters:
- `p_SerialNumber`: The serial number of the equipment.
- `p_LastServiceDate`: The date of the last service.
- `p_LastServiceDone`: Details about the last service performed.
- `p_NextPNMDate`: The next planned maintenance date.
- `p_NeedsParts`: Indicates if parts are needed ("True", "False", or "Part ordered").
- `p_PartName`: The name of the required parts.
- `p_PartsArrived`: Indicates if parts have arrived ("True", "False", or "N/A").
- `p_LocationID`: The ID of the location associated with the equipment.

### InsertLocation

This stored procedure allows you to insert location information into the `Location` table. It takes the following parameters:
- `p_Name`: The name of the location.
- `p_Address`: The address of the location.
- `p_PhoneNumber`: The phone number of the location.

### InsertServiceHistory

This stored procedure allows you to insert service history information into the `ServiceHistory` table. It takes the following parameters:
- `p_EquipmentSerialNumber`: The serial number of the equipment.
- `p_ServiceDate`: The date of the service.
- `p_ServiceType`: The type of service performed.
- `p_ServiceDescription`: A description of the service.
- `p_ServiceNotes`: Additional notes about the service.

### InsertShipping

This stored procedure allows you to insert shipping information into the `Shipping` table. It takes the following parameters:
- `p_EquipmentSerialNumber`: The serial number of the equipment.
- `p_ShippingDate`: The date of the shipment.
- `p_ShippingFrom`: The ID of the location from where the equipment was shipped.
- `p_ShippingMethod`: The shipping method used.
- `p_TrackingNumber`: The tracking number associated with the shipment.
- `p_ShippingStatus`: The status of the shipment.

Please note that these stored procedures provide a convenient way to insert data into the respective tables, helping streamline the data entry process.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
