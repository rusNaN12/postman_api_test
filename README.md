# Postman Collection

This repository contains a collection of API requests created with Postman.

## Collection Description

The Postman collection provides a set of API requests for testing and interacting with the XYZ API.

## Getting Started

To get started with the collection, follow these steps:

1. Install Postman: Make sure you have Postman installed on your machine. You can download it from the official website: [postman.com](https://www.postman.com/).

2. Import the Collection: Download the collection JSON file from this repository and import it into your Postman application. You can import the collection by clicking on the "Import" button in Postman and selecting the JSON file.

3. Configure Environment: Set up the necessary environment variables for your API endpoints. If required, update the environment variables in the imported collection to match your specific configuration.

4. Run the Requests: Start running the requests in the collection to interact with the `https://gorest.co.in/public/v2` API. Each request is organized into folders based on functionality and can be executed individually or as part of a sequence.

## Collection Structure

The collection is organized into the following folders:

- **GET users**: Contains requests for authentication and authorization.
- **POST users**: Contains requests related to user management.
- **PATCH users**: Contains requests for managing products.
- **DELETE users**: Contains requests for placing and managing orders.

## Environment Variables

The collection uses the following environment variables:

- `{{baseURL}}`: The base URL of the e.g `https://gorest.co.in/public/v2` API.
- `{{token}}`: An API key for authentication.

Make sure to set the appropriate values for these variables in your environment configuration.


## Test scenarios

| NR  | Endpoint | Type   | test description                                           | expected result                                           | 
| --- | -------- | ------ | ---------------------------------------------------------- | --------------------------------------------------------- | 
| 1   | users    | GET    | Test basic scenario with no params                         | return first page with 10 results                         | 
| 2   | users    | GET    | Test pagination without numbers count per page             | return result 10 per page                                 | 
| 3   | users    | GET    | Test pagination 1 element per page                         | only one result per page is received                      | 
| 4   | users    | GET    | Test pagination with 20 elements per page                  | only 20 results per page is received                      | 
| 5   | users    | GET    | Test pagination with 100 elements per page                 | only 100 results per page are received                    | 
| 6   | users    | GET    | Test pagination with 101 elements per page                 | 10 results per page are return                            | 
| 7   | users    | GET    | Test pagination with 0 elements per page                   | 10 results per page are returned                          | 
| 8   | users    | GET    | Test pagination with -1 elements per page                  | 10 results per paage are returned                         | 
| 9   | users    | GET    | Test page max + 1 with 20 elements per page                | 0 elements are displayed                                  | 
| 10  | users    | GET    | Test page 0 with 100 elements per page                     | 10 elements are displayed                                 | 
| 11  | users    | GET    | Test Page 2 with 20 elements per page                      | 20 element are displayed and header is set to second page | 
| 12  | users    | GET    | Test Page -1 with 20 elements per page                     | Page 1 is displayed with 20 elements per page             | 
| 13  | users    | POST   | Test user create with empty body                           | Errors fields can't be empty                              | 
| 14  | users    | POST   | Test user create with correctly set body with empty values | Errors fields can't be emtpy                              | 
| 15  | users    | POST   | Test user create with correctly set data                   | response code 201 is recived                              | 
| 16  | users    | POST   | Test user create with wrong status field                   | Response code 422                                         | 
| 17  | users    | POST   | Test user create with wrong gender field                   | Response code 422                                         | 
| 18  | users    | POST   | Test user create with wrong email format                   | Response code 422                                         | 
| 19  | users    | POST   | Test user create with duplicate request sent               | Response code 422 email has already been taken            | 
| 20  | users    | PATCH  | Test user update with no change                            | Response code 200 no data was modified                    | 
| 21  | users    | PATCH  | Test user update with random int as value                  | Response code 404                                         | 
| 22  | users    | PATCH  | Test user update with wrong email format                   | Response code 422 with error message                      | 
| 23  | users    | PATCH  | Test user update with status wrong value                   | Response code 422                                         | 
| 24  | users    | PATCH  | Test user update name value                                | Response code 200                                         | 
| 25  | users    | PATCH  | Test user update email value                               | Response code 200                                         | 
| 26  | users    | DELETE | Test user delete success scenario                          | Response code 204                                         | 
| 27  | users    | DELETE | Test user delete non existing id                           | Response code 404                                         | 

**NOTE** Test in `GET users` will fail due to actual behavior is not as per description of functionality.
## Contributing

Contributions to the collection are welcome! If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This collection is released under the [MIT License](LICENSE).

