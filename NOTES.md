URLs

https://7any9g9wub.execute-api.us-east-2.amazonaws.com/v1/co2-calculator/hours
https://7any9g9wub.execute-api.us-east-2.amazonaws.com/v1/co2-calculator/route
https://w7sewt0ksk.execute-api.us-east-2.amazonaws.com/v1/co2-quote/hours
https://w7sewt0ksk.execute-api.us-east-2.amazonaws.com/v1/co2-quote/route

Authorization
x-api-key: {{KEY}}
Key for co2-calculatory/
Key for co2-quote/

POST - co2-calculator/hours
Example body:
{
    "aircraftICAO": "C25B",
    "hoursFlown": 0.93
}
Example response:
{
    "aircraftType": "C25B",
    "hoursFlown": 0.93,
    "fuelType": "JetA",
    "co2emissions": 1322.3,
    "co2unit": "kg"
}

POST - co2-calculator/route
Exmaple body:
{
    "aircraftICAO": "C25B",
    "departureAirportICAO": "LIMC",
    "destinationAirportICAO": "LFPG",
    "departureDate": "12/12/2024"
}
Example response:
{
    "flightDistance": 599.3,
    "estFlightTime": 1.1,
    "estFuelConsumption": 157.1,
    "fuelType": "JetA",
    "fuelUnit": "gal",
    "co2emissions": 1508.7,
    "co2unit": "kg"
}

POST - co2-quote/hours
{
    "aircraftICAO": "C25B",
    "hoursFlown": 0.93
}
Example response:
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

POST - co2-quote/route
Example body:
{
    "aircraftICAO": "C25B",
    "departureAirportICAO": "LIMC",
    "destinationAirportICAO": "LFPG",
    "departureDate": "12/12/2024"
} 
Example response:
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