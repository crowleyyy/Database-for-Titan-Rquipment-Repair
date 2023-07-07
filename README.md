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
  - `shipping_from` (Foreign Key)
  - `shipping_method`
  - `tracking_number`
  - `shipping_status`

## Stored Procedures

The database includes the following stored procedures for inserting data into the respective tables:

- `InsertEquipment`: Inserts equipment information into the `Equipment` table.
- `InsertLocation`: Inserts location information into the `Location` table.
- `InsertServiceHistory`: Inserts service history information into the `ServiceHistory` table.
- `InsertShipping`: Inserts shipping information into the `Shipping` table.

These stored procedures provide a convenient way to insert data into the respective tables, helping streamline the data entry process.

## Indexing

To improve the performance of the database queries, certain columns have been indexed. The following indexes have been added:

- `Equipment` table:
  - Index on `serial_number` column for faster lookup of equipment by serial number.
  - Index on `location_id` column for efficient retrieval of equipment based on location.

- `ServiceHistory` table:
  - Index on `equipment_serial_number` column for quick access to service history by equipment.

- `Shipping` table:
  - Index on `equipment_serial_number` column for efficient retrieval of shipping details by equipment.

The indexes help optimize the database queries and enhance the overall performance of the system.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
