# Database For Titan Equipment Repair

Welcome to the Database For Titan Equipment Repair! This database is designed to manage information about forklift repairs and maintenance. It helps track forklifts, their service history, and the parts needed for repair.

## Database Structure

The database consists of the following tables:

### Authentication Table

- `Users` table:
  - `user_id` (Primary Key)
  - `username`
  - `password`

### Place A Table

- `PlaceA` table:
  - `serial_number` (Primary Key)
  - `last_service_date`
  - `last_service_done`
  - `next_service_date`
  - `needs_parts` (ENUM: "True", "False", "Part ordered")
  - `parts_name`
  - `parts_arrived` (ENUM: "True", "False", "N/A")

### Place B Table

- `PlaceB` table:
  - `serial_number` (Primary Key)
  - `last_service_date`
  - `last_service_done`
  - `next_service_date`
  - `needs_parts` (ENUM: "True", "False", "Part ordered")
  - `parts_name`
  - `parts_arrived` (ENUM: "True", "False", "N/A")

### Place Details Table

- `PlaceDetails` table:
  - `name`
  - `location`
  - `phone_number`

Please note that this database is a work in progress, and each table will have its own specific table and section.

## Contributing

Thank you for considering contributing to the Database For Titan Equipment Repair project! We welcome any contributions that help improve the database and enhance its functionalities. To ensure a smooth collaboration, please review the guidelines outlined in the [Contributing](CONTRIBUTING.md) file.

## License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE).

We appreciate your interest and contributions to this project. Together, we can make the database more comprehensive and useful!

