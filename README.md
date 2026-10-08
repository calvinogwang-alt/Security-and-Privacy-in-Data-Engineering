# Security and Privacy in Data Engineering

This repository contains simple Python examples demonstrating core security and privacy techniques used in data engineering projects.

## Overview

The examples cover:
- Hashing
- Encryption
- Data masking
- Data anonymization
- Pseudonymization
- Access control

## Setup

Install the required packages:

```bash
pip install cryptography pandas
```

## 1. Hashing in Python

Example: Password hashing using SHA-256.

```python
import hashlib

password = "MySecurePassword123"
hashed_password = hashlib.sha256(password.encode()).hexdigest()

print("Original password:", password)
print("Hashed password:", hashed_password)
```

## 2. Encryption Using Python

Example: symmetric encryption with Fernet.

```python
from cryptography.fernet import Fernet

key = Fernet.generate_key()
cipher = Fernet(key)

message = b"Confidential patient information"
encrypted = cipher.encrypt(message)

decrypted = cipher.decrypt(encrypted)

print("Key:", key)
print("Encrypted:", encrypted)
print("Decrypted:", decrypted)
```

## 3. Data Masking

Example: masking a phone number while preserving partial visibility.

```python
phone = "0772123456"
masked_phone = phone[:4] + "******"

print("Original phone:", phone)
print("Masked phone:", masked_phone)
```

## 4. Data Anonymization

Example: removing direct identifiers from a dataset.

```python
import pandas as pd

data = pd.DataFrame({
    "Name": ["John", "Mary", "Peter"],
    "Age": [35, 28, 42],
    "Diagnosis": ["HIV", "TB", "HIV"]
})

data["Patient_ID"] = ["P001", "P002", "P003"]

anonymized = data.drop(columns=["Name"])

print(anonymized)
```

## 5. Pseudonymization

Example: creating a pseudonymous identifier using a hash.

```python
import hashlib

patient_id = "P12345678"
pseudonym = hashlib.sha256(patient_id.encode()).hexdigest()

print("Patient ID:", patient_id)
print("Pseudonym:", pseudonym)
```

## 6. Access Control

Example: role-based access checks.

```python
user_role = "analyst"

if user_role == "admin":
    print("Full access granted")
elif user_role == "analyst":
    print("Access to analytical data granted")
else:
    print("Access denied")
```


