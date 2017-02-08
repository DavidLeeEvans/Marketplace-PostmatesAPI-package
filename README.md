[![](https://scdn.rapidapi.com/RapidAPI_banner.png)](https://rapidapi.com/package/PostmatesAPI/functions?utm_source=RapidAPIGitHub_PostmatesFunctions&utm_medium=button&utm_content=RapidAPI_GitHub)

# PostmatesAPI Package
Integrate on-demand local delivery service into your app.
* Domain: postmates.com
* Credentials: customerId, apiKey

## How to get credentials: 
0. Go to the [Postmates web site](https://postmates.com/developer) 
1. Log in or [register your app](https://postmates.com/partner/welcome)
2. Go to [your apps area](https://postmates.com/partner/dashboard/apps/general)
3. At the Authentication Keys area you can find your customerId key.
4. At the Delivery API Keys area you can find your API key.

## PostmatesAPI.getDeliveryQuote
This allows you to make decisions about the appropriate cost and availability for using the Postmates platform, which can vary based on distance and demand.

| Field         | Type       | Description
|---------------|------------|----------
| customerId    | credentials| Required: The customer id obtained from Postmates.
| apiKey        | credentials| Required: The API Key obtained from Postmates.
| pickupAddress | String     | Required: The pickup address for a potential delivery.
| dropoffAddress| String     | Required: The dropoff address for a potential delivery.

## PostmatesAPI.getDeliveryZones
This endpoint returns a list of GeoJSON-valid FeatureCollection objects representing all of our active delivery zones.

| Field     | Type       | Description
|-----------|------------|----------
| customerId| credentials| Required: The customer id obtained from Postmates.
| apiKey    | credentials| Required: The API Key obtained from Postmates.

## PostmatesAPI.createDelivery
This endpoint create a delivery.

| Field              | Type       | Description
|--------------------|------------|----------
| customerId         | credentials| Required: The customer id obtained from Postmates.
| apiKey             | credentials| Required: The API Key obtained from Postmates.
| quoteId            | String     | Optional: The ID of a previously generated delivery quote. Optional, but recommended.
| manifest           | String     | Required: A detailed description of what the courier will be delivering. Example: "A box of gray kittens".
| manifestReference  | String     | Optional: Optional reference that identifies the manifest. Example: "Order #690".
| pickupName         | String     | Required: Name of the place where the courier will make the pickup. Example: "Kitten Warehouse".
| pickupAddress      | String     | Required: The pickup address for the delivery. Example: "20 McAllister St, San Francisco, CA".
| pickupPhoneNumber  | String     | Required: The phone number of the pickup location. Example: "415-555-4242".
| pickupBusinessName | String     | Optional: Optional business name of the pickup location. Example: "Feline Enterprises, Inc.".
| pickupNotes        | String     | Optional: Additional instructions for the courier at the pickup location. Example: "Ring the doorbell twice, and only delivery the package if a human answers.".
| dropoffName        | String     | Required: Name of the place where the courier will make the dropoff. Example: "Alice".
| dropoffAddress     | String     | Required: The dropoff address for the delivery. Example: "678 Green St, San Francisco, CA".
| dropoffPhoneNumber | String     | Required: The phone number of the dropoff location. Example: "415-555-8484".
| dropoffBusinessName| String     | Optional: Optional business name of the dropoff location. Example: "Alice's Cat Cafe".
| dropoffNotes       | String     | Optional: Additional instructions for the courier at the dropoff location. Example: "Tell the security guard that you're here to see Alice.".

## PostmatesAPI.getAllDeliveries
List all deliveries for a customer.

| Field     | Type       | Description
|-----------|------------|----------
| customerId| credentials| Required: The customer id obtained from Postmates.
| apiKey    | credentials| Required: The API Key obtained from Postmates.
| filter    | String     | Optional: This filter limits the results to only deliveries that are currently being delivered. Possible value "ongoing".

## PostmatesAPI.getDelivery
Retrieve updated details about a delivery.

| Field     | Type       | Description
|-----------|------------|----------
| customerId| credentials| Required: The customer id obtained from Postmates.
| apiKey    | credentials| Required: The API Key obtained from Postmates.
| deliveryId| String     | Required: The ID of the created delivery.

## PostmatesAPI.cancelDelivery
Cancel an ongoing delivery. A delivery can only be canceled prior to a courier completing pickup. Delivery fees still apply.

| Field     | Type       | Description
|-----------|------------|----------
| customerId| credentials| Required: The customer id obtained from Postmates.
| apiKey    | credentials| Required: The API Key obtained from Postmates.
| deliveryId| String     | Required: The ID of the created delivery.


