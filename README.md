# Test_Airwallex


This repository contains a postman collection with series of tests to check an API service end point.

These checks have been created for use with Postman utility. Postman utility can be downloaded from https://www.getpostman.com/.

# Importing the files:

To run the tests, clone this repository to your local and then using postman utility, select the Import option to view the tests that are written within this collection.

Below are the steps:

Step 1:
git clone https://github.com/pavanrouthu/Test_Airwallex.git

Step 2:
Open the Postman utility and select the Import option. Select the “Import File” tab from the dialog and select Test_Airwallex_collection.json collection.

Step 3:
Also, import “environment.json” file into Postman utility to get access to the URL. URL has been externalized from the tests so that service endpoint url is configurable and same tests can be run in different environments just by changing the value of “host_name” and “host_port” fields.

To import environment.json follow the steps below:

1. From Postman utility, navigate to “Manage Environments”
2. Click on Import button
3. Choose environment.json file and the file gets imported into Postman. 

# Information about the tests

All tests are captured under the “Test_Airwallex” collection heading. Each testable scenario is captured as a separated POST request with a header, request body and tests under “Tests” tab that parse and validate the response. The assertions are easier to understand as it’s been written in Javascript.


#Running the tests:

There are two options to run the tests, either by using the “Collection Runner” utility from the GUI or by using Newman CLI (a command line test runner).

Option 1:

1. Using GUI Collection Runner: Once the collection is imported in Postman utility, you can expand the > accordion and click on the “Run” option to open the Collection Runner.

2. Click on the “Run <collection name>” to kick off the tests.

Option 2:

1. Install Newman CLI globally, then navigate to the where you saved the collection.

npm install –g newman

2. Go to the path where the files are cloned from git.
3. Run the postman collection using the command below:

newman run Test_Airwallex_collection.json -e environment.json --reporters cli,html --reporter-html-export Test_Report.htm

4. After the tests are done, the results can be viewed either on the command line or a report (Test_Report.htm) is created within the folder.

NOTE: Using Newman CLI, postman collections can be hooked up with build systems seamlessly.


