# No Active User Metering Values Displayed when Running the Metering Scenario End-to-End Locally

1. Mybee you loged in last month? Select the fitting month & year in the Day2 UI.
2. Check that the Day2 Services is up and healthy
   1. Open http://localhost:8091 in the browser. If this URL can't be reached repeat [Build and Test Run the Day2 Service Locally](../../meter/run-apps-locally/README.md#build-and-test-run-the-day2-service-locally)
   2. Validate the response of the ```user/metric``` API. This is the URL the Metering UI is getting its data from.

      ```
      curl --request GET 'http://localhost:8091/user/metric?year=<CURRENT-YEAR>&month=<CURRENT-MONTH-NUMBER>' 
      ```
      If you get data, check if you forgot to update the ```Vue.prototype.$backendApi``` in the Day2 Ui sources. (read [Run the Day2 UI](../../meter/run-apps-locally/README.md#run-the-day2-ui)) 

      If the rest call is ok, but returns an empty array repeat [Call the APIs of the Locally Running Day2 Service](../../meter/run-apps-locally/README.md#call-the-apis-of-the-locally-running-day2-service)

3. Check if any of your Applications run on different ports than expected. This can happen, when one of the default ports are occupied by another Service on your local PC. If this is the case you need to reconfigure the acceding configurations files and build and restart the services. 
   
   |Service| port |
   |:--- | :--- |
   |Day2 Service| http://localhost:8091|
   |ef-service| http://localhost:8080|
   |bp-service| http://localhost:8100|
   |db-service|http://localhost:8090|
   |Easy Franchise UI| http://localhost:8081|

      
4. Use the chapter [Test the Easy Franchise Application Locally](https://github.com/SAP-samples/btp-kyma-multitenant-extension/blob/main/documentation/prepare/test-app-locally/README.md) of the related Mission **Develop a Multitenant Extension Application in SAP BTP, Kyma Runtime** to validate if all the Easy Franchise Application up and healthy.
5. Use the Browser Debug mode to gain more insights and analyse the logs of each services.
 
   
