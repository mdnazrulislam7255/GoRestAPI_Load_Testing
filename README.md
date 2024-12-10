# Go Rest API Load Testing
This project assesses the performance and reliability of the Go Rest API under different conditions. The test plan, designed with Apache JMeter, simulates various HTTP requests, including GET, POST, PUT,and PATCH aimed at key API endpoints.

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
     https://github.com/mdnazrulislam7255/GoRestAPI_Load_Testing.git
     ```
   - Step 2: Configure JMeter
     Open the GoRestAPI.jmx file in Apache JMeter.
     Update the HTTP Request Defaults element to set the API base URL and authentication details (if applicable).
3. **_Import collection:_**
   - Open Jmeter.
   - Click on the Import button.
   - Select the file from the repository.

_**Usage**_ <br>

_**Select Environment:**_ <br>
      In Apache JMeter, select the appropriate environment from the top-right dropdown. <br>

_**Run Collection:**_ <br>                         																				
      Select the imported collection. <br>
      Select any one of the listener . <br>
      Select the desired environment. <br>
      Click Start Test to run the project.<br>
_**View Results:**_ <br>
       Once the tests are complete, view the results in the listener like View Results Tree or Aggregate Report. <br>
       Detailed test results can be viewed for each request.

## The script includes:
- Thread Groups: Configured with variable user loads and ramp-up times to simulate real-world usage patterns.
- HTTP Requests: Precisely configured for each API endpoint to validate CRUD operations.
- Assertions: Validates response status codes, response times, and data integrity.
- Listeners: Collect detailed test metrics and generate visual performance reports.

## Key API operations tested:
- GET /public/v2/users/: Retrieve all users.
- POST /public/v2/users/: Create a new user with randomized data.
- GET /public/v2/users//{id}: Fetch details of a specific user.
- PUT /public/v2/users//{id}: Update a user's information.
- PATCH /public/v2/users//{id}: Modify specific fields of a user.

# Base URL
The base URL is: https://gorest.co.in

## _Create a New User_
Protocol : _https_                                                                                                                                                                        
Server Name or IP: _gorest.co.in_                                                                                                                                         
HTTP Request method: _POST_                                                                                                                                                               
Path: _/public/v2/users/_                                                                                                                                                                  
HTTP Header Manager:                                                                                                                                                                                                                                                
- Content-Type: _application/json_                                                                                                                                            
- _Authorization: Bearer fa169e1336c27a986a48660afc597ede875dbe07171318b8532f68e64f12baf5_

JSON Extractor:
- Variables: _id_                                                                                                                                                                 
- JSON path expression: _$.id_

Note:                                                                                                                                                                                                            
_TestUser${__RandomString(5,abcdefghijklmnopqrstuvwxyz,)}_                                                                                                                                                       
Function:_ __RandomString_                                                                                                                                                                                       
Purpose: Generates a random string of characters of a specified length.                                                                                                                    
Explanation:                                                                                                                                                                               
  - _5:_ Specifies the length of the random string (5 characters in this case).                                                                                                                
  - _abcdefghijklmnopqrstuvwxyz:_ The set of characters to choose from (lowercase alphabets).                                                                                                  
  - _The result will look like:_ TestUserabcde (where abcde is a random string)                                                                                                                 
  
Request body:                                                                                                                                                                             
``` console
{
	"name":"TestUser${__RandomString(5,abcdefghijklmnopqrstuvwxyz,)}",
	"email":"testuser${__time()}.email@test.com",
	"gender":"male",
	"status":"active"
}
```
Response body:
``` console
{
   "id":7577456,
   "name":"TestUseroyrrt",
   "email":"testuser1733837924477.email@test.com",
   "gender":"male",
   "status":"active"
}
```
## _Get User Details_
Protocol : _https_                                                                                                                                                                        
Server Name or IP: _gorest.co.in_                                                                                                                                         
HTTP Request method: _GET_                                                                                                                                                               
Path: _/public/v2/users/_                                                                                                                                                                  
HTTP Header Manager:                                                                                                                                                                                                                                                
- Content-Type: _application/json_                                                                                                                                            
- _Authorization: Bearer fa169e1336c27a986a48660afc597ede875dbe07171318b8532f68e64f12baf5_

Request body:
``` console
none
```
Response body:
``` console
[{"id":7577456,"name":"TestUseroyrrt","email":"testuser1733837924477.email@test.com","gender":"male","status":"active"},{"id":7577455,"name":"TestUserbacqi","email":"testuser1733837920273.email@test.com","gender":"female","status":"inactive"},{"id":7577451,"name":"TestUserktddn","email":"testuser1733837919651.email@test.com","gender":"female","status":"inactive"},{"id":7577454,"name":"TestUserjbxfb","email":"testuser1733837919763.email@test.com","gender":"female","status":"inactive"},{"id":7577452,"name":"TestUserlpwjp","email":"testuser1733837918998.email@test.com","gender":"female","status":"inactive"},{"id":7577453,"name":"TestUserlecwi","email":"testuser1733837919693.email@test.com","gender":"female","status":"inactive"},{"id":7577450,"name":"TestUsermdiyx","email":"testuser1733837919262.email@test.com","gender":"female","status":"inactive"},{"id":7577449,"name":"TestUseryumdx","email":"testuser1733837918582.email@test.com","gender":"female","status":"inactive"},{"id":7577448,"name":"TestUserkqkch","email":"testuser1733837918497.email@test.com","gender":"female","status":"inactive"},{"id":7577447,"name":"TestUservdmnj","email":"testuser1733837918281.email@test.com","gender":"female","status":"inactive"}]
```
## _Get a User Details By ID_
Protocol : _https_                                                                                                                                                                        
Server Name or IP: _gorest.co.in_                                                                                                                                         
HTTP Request method: _GET_                                                                                                                                                               
Path: _/public/v2/users/${id}_                                                                                                                                                                  
HTTP Header Manager:                                                                                                                                                                                                                                                
- Content-Type: _application/json_                                                                                                                                            
- _Authorization: Bearer fa169e1336c27a986a48660afc597ede875dbe07171318b8532f68e64f12baf5_

Request body:
``` console
none
```
Response body:
``` console
{"id":7577457,"name":"TestUserychny","email":"testuser1733837924691.email@test.com","gender":"male","status":"active"}
```
## _Update a User Details By ID_
Protocol : _https_                                                                                                                                                                        
Server Name or IP: _gorest.co.in_                                                                                                                                         
HTTP Request method: _PUT_                                                                                                                                                               
Path: _/public/v2/users/${id}_                                                                                                                                                                  
HTTP Header Manager:                                                                                                                                                                                                                                                
- Content-Type: _application/json_                                                                                                                                            
- _Authorization: Bearer fa169e1336c27a986a48660afc597ede875dbe07171318b8532f68e64f12baf5_

Request body:
``` console
{
	"name":"TestUser${__RandomString(5,abcdefghijklmnopqrstuvwxyz,)}",
	"email":"testuser${__time()}.email@test.com",
	"gender":"male",
	"status":"active"
}
```
Response body:
``` console
{"email":"testuser1733837925455.email@test.com","name":"TestUsermmjxg","gender":"male","status":"active","id":7577457}
```
## _Update a User Details Partially By ID_
Protocol : _https_                                                                                                                                                                        
Server Name or IP: _gorest.co.in_                                                                                                                                         
HTTP Request method: _PATCH_                                                                                                                                                               
Path: _/public/v2/users/${id}_                                                                                                                                                                  
HTTP Header Manager:                                                                                                                                                                                                                                                
- Content-Type: _application/json_                                                                                                                                            
- _Authorization: Bearer fa169e1336c27a986a48660afc597ede875dbe07171318b8532f68e64f12baf5_

Request body:
``` console
{
    "status": "inactive",
    "gender": "female"
}
```
Response body:
``` console
{"gender":"female","status":"inactive","id":7577456,"name":"TestUserxadso","email":"testuser1733837925292.email@test.com"}
```
### Run Command:
  Run Command for Report: Run from Jmeter bin folder where the project file is located. The first command is for creating a jtl file and second is for producing a html report.
``` console
jmeter -n -t GoRestAPI.jmx -l GoRsetAPI_report\GoRestAPI.jtl
```
``` console
jmeter -g GoRsetAPI_report\GoRestAPI.jtl -o GoRsetAPI_report\GoRestAPI.html
```
### Reports
Test 1: This site does not allow to send too many requests. So I use:
- Number of threads: _10_; 
- Ramo-up period(seconds): _2_ ; 
- Loop count: _1_

![image](https://github.com/user-attachments/assets/7aaec7af-b6ef-4290-9be7-0fa36707cfa7)
![image](https://github.com/user-attachments/assets/bc305187-cf3a-46bb-8330-dc944bd3d347)
![image](https://github.com/user-attachments/assets/ad6c9a5c-0342-42d3-96bb-85d408b95a27)

### Contact
For questions or support, contact the development team at: Email: _nazrul15-7255@diu.edu.bd_




                  
