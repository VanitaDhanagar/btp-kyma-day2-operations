# No Active User Metering Values Displayed when Running the Metering Scenario End-to-End Locally

## Check the range filter
1. Open the Day2 UI.
2. Select the correct month and year. With **correct**, we mean the time range when you opened the Easy Franchise application.

## Check the availability of the Day2 service
1. Open http://localhost:8091 in the browser. 
2. If this URL can't be reached, repeat the documentation step [Build and Test Run the Day2 Service Locally](../../meter/run-apps-locally/README.md#build-and-test-run-the-day2-service-locally).

## Check the Day2 service API
1. Check the Day2 service is working by calling its API ```user/metric```. Open a terminal and add the following curl statement:
    ```
    curl --request GET 'http://localhost:8091/user/metric?year=<CURRENT-YEAR>&month=<CURRENT-MONTH-NUMBER>' 
    ```
2. If you get data, check if you forgot to update the ```Vue.prototype.$backendApi``` in the Day2 UI. Read [Run the Day2 UI](../../meter/run-apps-locally/README.md#run-the-day2-ui)) for more details.

3. If the rest call is ok, but returns an empty array, do again the steps described in [Call the APIs of the Locally Running Day2 Service](../../meter/run-apps-locally/README.md#call-the-apis-of-the-locally-running-day2-service).

## Check the ports 
1. Check if any of your locally running applications are using different ports than described in the documentation. This can happen, when one of the default ports are occupied by another Service on your local PC. 

1. If this is the case you need to reconfigure the according configuration files. Then build and restart the services. 
   
   |Service| port |
   |:--- | :--- |
   |Day2 Service| http://localhost:8091|
   |ef-service| http://localhost:8080|
   |bp-service| http://localhost:8100|
   |db-service|http://localhost:8090|
   |Easy Franchise UI| http://localhost:8081|

      
## Check that the Easy Franchise services are up and running
1. Check the chapter [Test the Easy Franchise Application Locally](https://github.com/SAP-samples/btp-kyma-multitenant-extension/blob/main/documentation/prepare/test-app-locally/README.md) of the related Mission **Develop a Multitenant Extension Application in SAP BTP, Kyma Runtime** to validate that all the Easy Franchise services are up and running.
