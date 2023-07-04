## Database For Titan Equipment Repair (Work in Progress)

This repository contains the source code and documentation for a database designed for Titan Equipment Repair. The database manages various aspects of the company's operations, including authentication, PlaceA, and PlaceB information.

### Introduction

The Database For Titan Equipment Repair is a comprehensive solution for managing the data of Titan Equipment Repair. It provides functionalities for user authentication and storing information about different places. This database aims to streamline the company's operations, enhance data management, and improve overall efficiency.

Please note that this database is a work in progress, and additional tables and sections will be added to accommodate specific information.

### Authentication Table

The `authentication` table stores user authentication information, allowing authorized access to the database. It includes the following columns:

- `id`: The unique identifier for each user.
- `username`: The username associated with the user account.
- `password`: The hashed password for secure authentication.

### PlaceA Table

The `placeA` table stores information about PlaceA within Titan Equipment Repair. It includes the following columns:

- `id`: The unique identifier for each entry.
- `serial_number`: The serial number of the forklift at PlaceA.
- `last_service_date`: The date of the last service performed on the forklift at PlaceA.
- `last_service_done`: A description of the last service performed on the forklift at PlaceA.
- `next_pm_date`: The next preventive maintenance date (oil change) for the forklift at PlaceA.
- `needs_parts`: Indicates if the forklift at PlaceA needs parts. Possible values: "True", "False", "Part ordered" (ENUM).
- `parts_name`: The name of the parts required for the forklift at PlaceA.
- `parts_arrived`: Indicates if the required parts have arrived for the forklift at PlaceA. Possible values: "True", "False", "N/A" (ENUM).

### PlaceB Table

The `placeB` table stores information about PlaceB within Titan Equipment Repair. It includes the following columns:

- `id`: The unique identifier for each entry.
- `serial_number`: The serial number of the forklift at PlaceB.
- `last_service_date`: The date of the last service performed on the forklift at PlaceB.
- `last_service_done`: A description of the last service performed on the forklift at PlaceB.
- `next_pm_date`: The next preventive maintenance date (oil change) for the forklift at PlaceB.
- `needs_parts`: Indicates if the forklift at PlaceB needs parts. Possible values: "True", "False", "Part ordered" (ENUM).
- `parts_name`: The name of the parts required for the forklift at PlaceB.
- `parts_arrived`: Indicates if the required parts have arrived for the forklift at PlaceB. Possible values: "True", "False", "N/A" (ENUM).

### Trigger for Updating Needs Parts

A trigger has been implemented in the database to automatically update the `needs_parts` column in both the PlaceA and PlaceB tables. When the `parts_arrived` column is set to "True", the trigger will change the value of `needs_parts` to "False". This ensures that the database maintains accurate information about the parts status for each forklift.

### Additional Tables (Work in Progress)

This database is under development, and additional tables will be added to handle specific information and functionality. Stay tuned for updates.

### Contributing

Contributions to the Database For Titan Equipment Repair project are welcome! If you have suggestions, bug reports, or would like to add new features, please follow the guidelines outlined in the [Contribution Guidelines](CONTRIBUTING.md).

### License

The Database For Titan Equipment Repair is licensed under the [MIT License](LICENSE). Feel free to modify and distribute the code as per the terms of the license.
