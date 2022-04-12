# Move On Integration API

## Objective
- Allow Move On app to register a Cun Cun account while signing up in Move On app. If success the user will also automatically enrolled to Move On's VIP Community.

## Authorization
- Client IPs need to be whitelisted, please contact us to whitelist your IPs.
- Production and Testing can have different set of IPs.

## API Base URL
- Production server: https://member.cuncun2u.com/api/v1/tp/
- Testing server: https://staging.cuncun2u.com/api/v1/tp/

## Available Endpoints
- `mo/register`

## Usage
1. Make a HTTP POST request to the endpoint.
2. Set the `Content-Type` and `accept` header to `application/json`.

```sh
curl --request POST \
  --url https://cuncun.test/api/v1/tp/mo/register \
  --header 'Content-Type: application/json' \
  --header 'accept: application/json' \
  --data '{   
    "email": "jennifer90@gmail.com",
    "date_of_birth": "1990-01-31",
    "race": 1,
    "ext": 133, 
    "contact_number": "123456789",
    "gender": 2, 
    "name": "Jennifer d/o Collins",  
    "nationality": 1, 
    "national_id_type": 1,
    "national_id": "900131-10-1234",
    "industry": 3,
    "occupation": 18
}'
'

```

## Required Data
```js
{   
    // string, required
    "email": "jennifer90@gmail.com",

    // string, date, required
    // format (php date format): Y-m-d 
    "date_of_birth": "1990-01-31",

    // integer, optional
    // please refer to the enumerations sections of this documentation
    // omitting this field, zero, empty string, null, or any value other than specify in the enums will means not saving this field in our server
    "race": 1,

    // integer, required
    // please refer to the enumerations sections of this documentation
    "ext": 133, 

    // string, required
    // mobile phone number without country code. For example, "+60 12 - 345 6789" will be "123456789"
    "contact_number": "123456789",

    // integer, required
    // please refer to the enumerations sections of this documentation
    "gender": 2, 

    // string, required
    // Full name like in user's legal identification document
    "name": "Jennifer d/o Collins",  

    // integer, required
    // Please refer to the enumerations sections of this documentation
    // To tell user is Malaysian or Non-Malaysian
    "nationality": 1, 

    // integer, required
    // please refer to the enumerations sections of this documentation
    "national_id_type": 1,

    // integer, required
    // please refer to the enumerations sections of this documentation    
    "national_id": "900131-10-1234",

    // integer, required
    // please refer to the enumerations sections of this documentation
    "industry": 3,

    // integer, required
    // please refer to the enumerations sections of this documentation
    "occupation": 18
}
```

## Response
```js
{
    "message": "Operation Success"
}
```


## Enumerations
```js
{
    "gender": { 
        "1": "Male",
        "2": "Female"
    },
    "race": {
        "1": "Malay",
        "2": "Chinese",
        "3": "Indian",
        "99": "Other",
    },
    "ext": { // Contact number country extension
        "133": "+60", // Malaysia
        "216": "+66"  // Thailand
    },
    "nationality": {
        "1": "Malaysian",
        "2": "Non-Malaysian"
    },
    "national_id_type": {
        "1": "NRIC",
        "2": "Passport",
        "3": "Army ID",
        "4": "Police ID"
    },
    "industry": {
        "1": "Administrative",
        "2": "Clerical",
        "3": "Executive",
        "4": "Heavy Machinery",
        "5": "Manual Labour",
        "6": "Professional",
        "7": "Skilled Work",
        "8": "Semi-Skilled Work",
        "9": "Others"
    },
    "occupation": {
        "1": "Accountants",
        "2": "Actors & Actresses",
        "3": "Acupuncturists",
        "4": "Advertising Professionals",
        "5": "Agents (Financial products)",
        "6": "Agents (Insurance, property or tour)",
        "7": "Air Con Repairmen",
        "8": "Analysts",
        "9": "Appliance",
        "10": "Architects",
        "11": "Artists",
        "12": "Assembly Line Work (Not using tools or machinery)",
        "13": "Auditors",
        "14": "Authors",
        "15": "Bakers",
        "16": "Banking Professionals",
        "17": "Barbers",
        "18": "Bartenders",
        "19": "Beauticians",
        "20": "Boat Drivers / Operators",
        "21": "Bowling Attendants",
        "22": "Brokers",
        "23": "Buyers",
        "24": "Car Park Attendants",
        "25": "Car Washers",
        "26": "Carpenters",
        "27": "Cashiers",
        "28": "Caterers (Cooking)",
        "29": "Caterers (Not Cooking)",
        "30": "Chefs",
        "31": "Chemists",
        "32": "Chiropractors",
        "33": "Cleaners",
        "34": "Clerks",
        "35": "Coaches/Instructors (Any sports except airborne, car, deep sea diving, extreme sports or skiing)",
        "36": "Contractors",
        "37": "Coroners",
        "38": "Couriers",
        "39": "Dealers (Financial products & cars)",
        "40": "Deliverymen",
        "41": "Dentists",
        "42": "Designers",
        "43": "Doctors",
        "44": "Domestic Helpers",
        "45": "Drivers (Personal, taxi or bus requiring class 3 licenses)",
        "46": "Driving Instructors (Teaching class 3 vehicles)",
        "47": "Editors",
        "48": "Electricians",
        "49": "Executives",
        "50": "Factory Workers",
        "51": "Florists",
        "52": "Food/Drink Stall Owners/Assistants",
        "53": "Foreman (Construction)",
        "54": "Foreman (Non-Construction)",
        "55": "Furniture Workers or Movers",
        "56": "Goldsmiths",
        "57": "Guides",
        "58": "Hairstylists",
        "59": "Hawkers (Cooking)",
        "60": "Hawkers (Not Cooking)",
        "61": "Home Makers",
        "62": "Insurance Professionals",
        "63": "IT Professionals",
        "64": "Jewellers (Retail Only)",
        "65": "Journalists (Not covering war)",
        "66": "Laboratory Staff Work",
        "67": "Lawyers",
        "68": "Lecturers",
        "69": "Librarians",
        "70": "Lifeguards",
        "71": "Managers",
        "72": "Manicurists & Pedicurists",
        "73": "Market Merchants (Selling drinks, fruits or dried foodstuff)",
        "74": "Market Merchants (Selling pork, poultry or seafood)",
        "75": "Marketing Professionals",
        "76": "Masseuse",
        "77": "Mechanics",
        "78": "Models",
        "79": "Money Changers",
        "80": "MRT Staff (except technicians and doing underground work)",
        "81": "Music Industry Professionals",
        "82": "Nurses",
        "83": "Nurses (Based in IMH)",
        "84": "Opticians",
        "85": "Painters (interior of building or house only)",
        "86": "Paramedics",
        "87": "Pet Shop Dealers/Owners/Assistants",
        "88": "Photographers",
        "89": "Physios",
        "90": "Plumbers",
        "91": "Principals",
        "92": "Receptionists",
        "93": "Referees (All sports)",
        "94": "Repairmen Engineers (Except worksite/offshore work)",
        "95": "Retirees",
        "96": "Sales Executives",
        "97": "Seamstresses",
        "98": "Security Guard (Unarmed)",
        "99": "Social Workers",
        "100": "Students",
        "101": "Surveyors",
        "102": "Tailors",
        "103": "Teachers",
        "104": "Technicians",
        "105": "Veterinarian",
        "106": "Waiters/Waitresses",
        "107": "Welfare Professionals",
        "108": "Zookeepers",
        "109": "Others"
    },
}
```
