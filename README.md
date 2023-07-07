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
  - `technician_id` (Foreign Key)

### Shipping Table

- `Shipping` table:
  - `shipping_id` (Primary Key)
  - `equipment_serial_number` (Foreign Key)
  - `shipping_date`
  - `shipping_from` (Foreign Key)
  - `shipping_method`
  - `tracking_number`
  - `shipping_status`

The `Shipping` table stores shipping details for equipment. It includes the following columns:

- `shipping_id`: A unique identifier for each shipping entry.
- `equipment_serial_number`: A foreign key referencing the serial number of the equipment from the `Equipment` table.
- `shipping_date`: The date when the equipment was shipped.
- `shipping_from`: A foreign key referencing the location from the `Location` table where the equipment was shipped from.
- `shipping_method`: The method used for shipping.
- `tracking_number`: The tracking number associated with the shipment.
- `shipping_status`: The status of the shipment.

Please note that this project is a work in progress, and the database structure may change in future iterations. We are continuously refining and improving the database to better serve the needs of Titan Equipment Repair.

Each entry in the `Equipment` table is associated with a specific `location_id` from the `Location` table for future workflow.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
