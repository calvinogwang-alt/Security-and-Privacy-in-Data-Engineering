# Security-and-Privacy-in-Data-Engineering
Python codes for Security and Privacy in Data Engineering
#Security and Privacy

#Hashing in Python

#Example: Password Hashing in Python
import hashlib

password = "MySecurePassword123"

hashed_password = hashlib.sha256(password.encode()).hexdigest()

print(hashed_password)

#Encryption Using Python

from cryptography.fernet import Fernet

key = Fernet.generate_key()
cipher = Fernet(key)

message = b"Confidential patient information"

encrypted = cipher.encrypt(message)

print(encrypted)

#Data Masking

phone = "0772123456"

masked_phone = phone[:4] + "******"

print(masked_phone)

#Data Anonymization

import pandas as pd

data = pd.DataFrame({
    "Name": ["John", "Mary", "Peter"],"Age": [35, 28, 42],"Diagnosis": ["HIV", "TB", "HIV"]})

data["Patient_ID"] = ["P001", "P002", "P003"]

anonymized = data.drop(columns=["Name"])

print(anonymized)

#Pseudonymization

import hashlib

patient_id = "P12345678"

pseudonym = hashlib.sha256(patient_id.encode()).hexdigest()

print(pseudonym)

#Access Control

user_role = "analyst"

if user_role == "admin":
    print("Full access granted")
elif user_role == "analyst":
    print("Access to analytical data granted")
else:
    print("Access denied")