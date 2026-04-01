Task 1 — Classify and Handle PII Fields
-----------------------------------------

1.) Classification of PII:
--------------------------
#Direct PII :
  full_name, email

#Indirect PII:
  date_of_birth, zip_code, job_title, diagnosis_notes

2.) Handling the PII:
---------------------
  full_name - pseudonymize
  email - pseudonymize
  date_of_birth - drop it
  zip_code - mask it
  job_title - drop it
  diagnosis_notes -

>In this data we should pseudonymize the full_name and email column, because they are direct PII which can reveal the users data.
>Zip_code should be masked because the combination of zip_cose, date_of_birth and email can lead us to trace back the user identity.
>We should drop the date_of_birth and job_title column beacuse job_title doesn't contribute anything to our analysis and date_of_birth can create unawnted Correlation.
===================================================================================================================================================================================

Task 2 — Audit the API Script for Ethical Compliance
------------------------------------------------------

"""
import requests

API_URL = "https://healthstats-api.example.com/records"
API_KEY = "free_tier_key_abc123"

records = []
for page in range(1, 101):
    response = requests.get(API_URL, params={"page": page, "key": API_KEY})
    data = response.json()
    records.extend(data["results"])

# Store all records permanently in company database
save_to_database(records)

"""

Ethical and TOS violations:
----------------------------
In this code we can see that they have stored the API_KEY openly which is accessible to everyone which can cause wrong usage of the data,
Another violation is excessive scraping with a free-tier API key.Most free-tier licenses explicitly limit how many requests you can make. This kind of bulk scraping violates the API provider’s TOS and can overload their servers.
So scraping over 100 pages can lead to overload.
The biggest violation is storing third-party health records permanently in a company database,it is completly unethical to store the data.
