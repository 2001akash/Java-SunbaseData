# Java-SunbaseData
API Integration Documentation
1. Authentication API
Endpoint:
URL: https://qa2.sunbasedata.com/sunbase/portal/api/assignment_auth.jsp
Method: POST
Headers: Content-Type: application/json
Body:
{
    "login_id": "test@sunbasedata.com",
    "password": "Test@123"
}
![image](https://github.com/2001akash/Java-SunbaseData/assets/88871193/7e60d846-09ae-4ba0-b62b-bde9879d3ea5)

Response:
Success (200): JSON object containing a token.

2. Create a New Customer
Endpoint:
URL: https://qa2.sunbasedata.com/sunbase/portal/api/assignment.jsp
Method: POST
Headers:
Content-Type: application/json
Authorization: Bearer <token_received_in_authentication_API_call>
Parameters:
cmd: create
Body:
json
Copy code
{
    "first_name": "Jane",
    "last_name": "Doe",
    "street": "Elvnu Street",
    "address": "H no 2",
    "city": "Delhi",
    "state": "Delhi",
    "email": "sam@gmail.com",
    "phone": "12345678"
}
Response:
Success (201): Successfully Created
Failure (400): First Name or Last Name is missing

![image](https://github.com/2001akash/Java-SunbaseData/assets/88871193/a4896248-cfc3-459f-87b4-e24316270b48)



4. Get Customer List
Endpoint:
URL: https://qa2.sunbasedata.com/sunbase/portal/api/assignment.jsp
Method: GET
Headers:
Authorization: Bearer <token_received_in_authentication_API_call>
Parameters:
cmd: get_customer_list
Response:
Success (200): Array of customer objects.

![image](https://github.com/2001akash/Java-SunbaseData/assets/88871193/cadb9660-fea3-460a-8777-ded44e74b84e)


5. Delete a Customer
Endpoint:
URL: https://qa2.sunbasedata.com/sunbase/portal/api/assignment.jsp
Method: POST
Headers:
Authorization: Bearer <token_received_in_authentication_API_call>
Parameters:
cmd: delete
uuid: <uuid_of_a_specific_customer>
Response:
Success (200): Successfully deleted
Failure (400): UUID not found
Error (500): Error Not deleted


6. Update a Customer
Endpoint:
URL: https://qa2.sunbasedata.com/sunbase/portal/api/assignment.jsp
Method: POST
Headers:
Authorization: Bearer <token_received_in_authentication_API_call>
Parameters:
cmd: update
uuid: <uuid_of_a_specific_customer>
Body:
json
Copy code
{
    "first_name": "Jane",
    "last_name": "Doe",
    "street": "Elvnu Street",
    "address": "H no 2",
    "city": "Delhi",
    "state": "Delhi",
    "email": "sam@gmail.com",
    "phone": "12345678"
}
Response:
Success (200): Successfully Updated
Failure (400): Body is Empty
Error (500): UUID not found
User Interface (UI)


Screens:
Login Screen:

Basic login form with email and password fields.
"Login" button triggers API authentication.
Displays an error message if authentication fails.
Customer List Screen:

Displays a table of customer data.
Allows deletion of customers.
Provides a button to navigate to the Add Customer screen.
Displays an error message if authentication fails.
Add a New Customer Screen:

Basic form to input customer details.
"Add Customer" button triggers API call to create a new customer.
Displays success or failure messages.
Note: Replace placeholders such as <token_received_in_authentication_API_call> and <uuid_of_a_specific_customer> with actual values received from API calls.
You can also test these details in Postman.

