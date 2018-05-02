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

Ensure imported environment is selected when running the scripts. Otherwise the scripts will fail.

# Information about the tests

All tests are captured under the “Test_Airwallex” collection heading. Each testable scenario is captured as a separate POST request with a header, request body and tests under “Tests” tab that parse and validate the response. The assertions are easier to understand as it’s been written in Javascript.

The following 38 scenarios have been captured and validated as part of the postman collection:

* Save Bank Details - When country is AU and Payment Method is SWIFT
* Save Bank Details - When country is AU and Payment Method is LOCAL
* Save Bank Details - When country is US and Payment Method is SWIFT
* Save Bank Details - When country is US and Payment Method is LOCAL
* Save Bank Details - When country is CN and Payment Method is SWIFT
* Save Bank Details - When country is CN and Payment Method is LOCAL
* Scenario when country code is other than US, AU or CN and Payment Method is LOCAL
* Scenario when country code is other than US, AU or CN and Payment Method is SWIFT
* Scenario when Payment_Method field is blank
* Scenario when Bank Country Code field is blank
* Scenario to check when BSB is not available for AU
* Scenario to check when BSB is less than 6 characters
* Scenario to check when BSB is greater than 6 characters
* Scenario to check when ABA is not available for US
* Scenario to check when ABA is less than 9 characters
* Scenario to check when ABA is greater than 9 characters
* Scenario when swift code is less than 8 characters
* Scenario when swift code is exactly 8 characters
* Scenario when swift code is exactly 11 characters
* Scenario when swift code is between 8-11 characters
* Scenario when swift code is greater than 11 characters
* Scenario to check swift code is mandatory when payment method is SWIFT and is in CN
* Scenario to check swift code is mandatory when payment method is SWIFT and is in US
* Scenario to check swift code is mandatory when payment method is SWIFT and is in AU
* Verify the error message for AU, if 5th and 6th character of swift code doesn't match the country code
* Verify the error message for US, if 5th and 6th character of swift code doesn't match the country code
* Verify the error message for CN, if 5th and 6th character of swift code doesn't match the country code
* Scenario when Account Name field is blank
* Scenario when Account Name field has special characters
* Scenario when Account Name field is less than 2 characters long
* Scenario when Account Name field is greater than 10 characters
* Scenario when Account Number field is blank
* Scenario when Account Number field has special characters
* Scenario when Account Number field is greater than 17 characters and in US
* Scenario when Account Number field is less than 6 characters and in AU
* Scenario when Account Number field is greater than 9 characters and in AU
* Scenario when Account Number field is greater than 20 characters and in CN
* Scenario when Account Number field is less than 8 characters and in CN


# Running the tests:

There are two options to run the tests, either by using the “Collection Runner” utility from the GUI or by using Newman CLI (a command line test runner).

Option 1:

1. Using GUI Collection Runner: Once the collection is imported in Postman utility, you can expand the > accordion and click on the “Run” option to open the Collection Runner.

2. Click on the “Run ‘Name of the collection’” to kick off the tests.

Option 2:

1. Install Newman CLI globally, then navigate to the path where you have saved the collection.

	npm install –g newman

2. Go to the path where the files are cloned from git.
3. Run the postman collection using the command below:

	newman run Test_Airwallex_collection.json -e environment.json --	reporters cli,html --reporter-html-export Test_Report.htm

4. After the tests are executed, the results can be viewed either on the command line or a from the generated report (Test_Report.htm) within the folder.

NOTE: Using Newman CLI, postman collections can be hooked up with build systems like Jenkins seamlessly.

# Defects

All the observations are documented as part of the “Defects.docx” document that would be available in the path where the repository is cloned.
