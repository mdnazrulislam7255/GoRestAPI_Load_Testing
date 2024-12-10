# Go Rest API Load Testing
This project assesses the performance and reliability of the Go Rest API under different conditions. The test plan, designed with Apache JMeter, simulates various HTTP requests, including GET, POST, PUT, PATCH, and DELETE, aimed at key API endpoints.

_**This test suite is designed to:**_
- Assess the system's responsiveness by measuring metrics like response time and throughput.
- Identify performance bottlenecks under increasing levels of concurrent user traffic.
- Ensure the API can handle typical operations like creating, updating, and retrieving user efficiently.

**Prerequisites**
1. _**System Requirements:**_
   - Operating System: Windows, Linux, or macOS
   - Java 8 or higher installed (required for JMeter)
2. _**Tools**_
   - Apache JMeter:  If you haven't already, [download and install Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi).
3. _**Setup and Execution**_
   - Step 1: Clone the Repository:
     ``` clone
     git clone https://github.com/mdnazrulislam7255/Booikng_API_Load_Testing.git
     ```
   - Step 2: Configure JMeter
     Open the GoRestAPI.jmx file in Apache JMeter.
     Update the HTTP Request Defaults element to set the API base URL and authentication details (if applicable).
3. **_Import collection:_**
   - Open Jmeter.
   - Click on the Import button.
   - Select the file from the repository.

**Usage**
_**Select Environment:**_
      In Apache JMeter, select the appropriate environment from the top-right dropdown.
_**Run Collection:**_
      Select the imported collection.
      Select any one of the listener .
      Select the desired environment.
      Click Start Test to run the project.
_**View Results:**_
     Once the tests are complete, view the results in the listener like View Results Tree or Aggregate Report.
     Detailed test results can be viewed for each request.

## The script includes:
- Thread Groups: Configured with variable user loads and ramp-up times to simulate real-world usage patterns.
- HTTP Requests: Precisely configured for each API endpoint to validate CRUD operations.
- Assertions: Validates response status codes, response times, and data integrity.
- Listeners: Collect detailed test metrics and generate visual performance reports.

## Key API operations tested:
- GET //public/v2/users/: Retrieve all users.
- POST //public/v2/users/: Create a new user with randomized data.
- GET //public/v2/users//{id}: Fetch details of a specific user.
- PUT //public/v2/users//{id}: Update a user's information.
- PATCH //public/v2/users//{id}: Modify specific fields of a user.

# Base URL
The base URL is: https://restful-booker.herokuapp.com
