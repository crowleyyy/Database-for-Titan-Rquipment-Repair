# Database For Titan Equipment Repair

Welcome to the Database For Titan Equipment Repair! This database is designed to manage information about forklift repairs and maintenance. It helps track forklifts, their service history, and the parts needed for repair.

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

Please note that the `Equipment` table includes the `serial_number` column and the corrected column names for `last_service_date`, `last_service_done`, and `next_pnm_date`.

Each entry in the `Equipment` table is associated with a specific `location_id` from the `Location` table for future workflow.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!
