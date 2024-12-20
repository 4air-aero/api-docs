# API Documentation

> **Note:** This API is currently in **beta**. Functionality and endpoints may change without notice.

## Authorization

To access the endpoints, include the following header in your requests:

### Header:
```plaintext
x-api-key: x-provided-x
```
**Note**: The x-api-key value is subject to change. Please ensure you use the most up-to-date key provided.


## /co2-calculator/hours

<h3 class="yellow-text">POST</h3>

### URL: https://7any9g9wub.execute-api.us-east-2.amazonaws.com/v1/co2-calculator/hours

- Calculate CO2 emissions based flight hours.

#### Request Body:
```json
{
    "aircraftICAO": "string",    // Aircraft identifier (e.g., "C25B")
    "hoursFlown": "number"      // Hours flown (e.g., 0.93)
}
```
#### Example Request:
```json
{
    "aircraftICAO": "C25B",
    "hoursFlown": 0.93
}
```
#### Example Response:
<p class="green-text">200 OK</p>

```json
{
    "aircraftType": "C25B",
    "hoursFlown": 0.93,
    "fuelType": "JetA",
    "co2emissions": 1322.3,
    "co2unit": "kg"
}
```
## co2-calculator/route

<h3 class="yellow-text">POST</h3>

### URL: https://7any9g9wub.execute-api.us-east-2.amazonaws.com/v1/co2-calculator/route

- Calculate CO2 emissions based on flight route.

#### Request Body:
```json
{
    "aircraftICAO": "string",                  // Aircraft identifier (e.g., "C25B")
    "departureAirportICAO": "string",         // Departure airport ICAO code (e.g., "LIMC")
    "destinationAirportICAO": "string",       // Destination airport ICAO code (e.g., "LFPG")
    "departureDate": "string (YYYY-MM-DD)"    // Departure date (e.g., "2024-12-12")
}
```

#### Example Request:
```json
{
    "aircraftICAO": "C25B",
    "departureAirportICAO": "LIMC",
    "destinationAirportICAO": "LFPG",
    "departureDate": "2024-12-12"
}
```

#### Example Response:
<p class="green-text">200 OK</p>

```json
{
    "flightDistance": 599.3,
    "estFlightTime": 1.1,
    "estFuelConsumption": 157.1,
    "fuelType": "JetA",
    "fuelUnit": "gal",
    "co2emissions": 1508.7,
    "co2unit": "kg"
}
```

## co2-quote/hours

<h3 class="yellow-text">POST</h3>

### URL: https://w7sewt0ksk.execute-api.us-east-2.amazonaws.com/v1/co2-quote/hours

- Calculate CO2 emissions and cost based on flight hours.

#### Request Body:
```json
{
    "aircraftICAO": "string",    // Aircraft identifier (e.g., "C25B")
    "hoursFlown": "number"      // Hours flown (e.g., 0.93)
}
```

#### Example Request:
```json
{
    "aircraftICAO": "C25B",
    "hoursFlown": 0.93
}
```

#### Example Response:
<p class="green-text">200 OK</p>

```json
{
    "aircraftType": "C25B",
    "hoursFlown": 0.93,
    "fuelType": "JetA",
    "co2emissions": 1322.3,
    "co2unit": "kg",
    "level1cost": 20,
    "level2cost": 60,
    "level3cost": 114,
    "level4cost": 117
}
```

## co2-quote/route

<h3 class="yellow-text">POST</h3>

### URL: https://w7sewt0ksk.execute-api.us-east-2.amazonaws.com/v1/co2-quote/route

- Calculate CO2 emissions and cost based on a flight route.

#### Request Body:
```json
{
    "aircraftICAO": "string",                  // Aircraft identifier (e.g., "C25B")
    "departureAirportICAO": "string",         // Departure airport ICAO code (e.g., "LIMC")
    "destinationAirportICAO": "string",       // Destination airport ICAO code (e.g., "LFPG")
    "departureDate": "string (YYYY-MM-DD)"    // Departure date (e.g., "2024-12-12")
}
```

#### Example Request:
```json
{
    "aircraftICAO": "C25B",
    "departureAirportICAO": "LIMC",
    "destinationAirportICAO": "LFPG",
    "departureDate": "2024-12-12"
}
```

#### Example Response:
<p class="green-text">200 OK</p>

```json
{
    "flightDistance": 599.3,
    "estFlightTime": 1.1,
    "estFuelConsumption": 157.1,
    "fuelType": "JetA",
    "fuelUnit": "gal",
    "co2emissions": 1508.7,
    "co2unit": "kg",
    "level1cost": 23,
    "level2cost": 68,
    "level3cost": 130,
    "level4cost": 133
}
```

#

**Contact**

For any issues or questions regarding the API, please contact our support team at support@example.com.



<style>
/* .red-text { color: red; } */
/* .yellow-text { color: yellow; } */
.green-text { color: green; }
</style>
