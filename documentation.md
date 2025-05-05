
# 🧾 Test Documentation for Breach Application

# 1. Overview
This document describes the testing process for the Breach web application, including testing methods, tools, environments, test coverage, and known issues.

# 2. Test Environment
- **Operating System:** Windows 10
- **Browsers Tested:** Chrome, Firefox, and Microsoft Edge
- **Test Devices:** HP Elitebook 1040 G3

# 3. Tools Used
- Apache Jmeter for for load testing
- Postman for API testing
- Google Sheets for bug tracking
- ScreenRec for video recordings


## 4. Test Execution Summary
- Total test cases executed: 51
- Passed: 30
- Failed: 21 ( 17 logged as bugs, while 1 is backend, and three relates to websocket )


## 5. Issues Observed - Load Testing

- Load testing was done on the login endpoint and server was able to generate successful response code between 200-500 users,and even more. However, the loop count was set to infinite.
  and the server broke down when concurrent users reached between 700–800. See attached Video link in the Readme
- The server for Blogs endpoint was stable up to 399 virtual users. The system began to experience failure at 400–500+ users, with failures occurring approximately every 5 seconds. Posts endpoint was stable for 299 concurrent users.Server broke when it got to 300 virtual users and above. See attached recorded video in the Readme link
- For interest endpoint, A performance drop was observed at 500 concurrent users during a test with a 10-second ramp-up. This may have been caused by a temporary network glitch, as subsequent tests showed the server handled up to 900 concurrent users successfully.See video recording in the Readme link 


## 6. Known Limitations
- Websocket was not sending back messages even though it connected successfully
- The frontend still need major fixes as it captures more than 95% of all bugs 

