Application: Burger King Mobile App
Module: Profile / Account Details
Severity: High
Type: Functional / Validation Defect

## 🐞 Defect Title

- Phone number field accepts invalid input formats and behaves inconsistently.

## 📌 Description

- The phone number input field accepts invalid formats such as:
- Less than required digits (e.g., fewer than 10 digits)
- Random characters
- Mixed character input

However:

- A string consisting only of zeros (e.g., 0000000000) is rejected.
- This creates inconsistent validation behavior where clearly invalid formats are accepted, while other equally invalid formats are rejected.

## 🔁 Steps to Reproduce

- Navigate to Profile section.
- Edit phone number field.
- Enter fewer than 6 digits (e.g., 12345).
- Save changes.
- Enter mixed characters (e.g., abc123).
- Save changes.
- Enter 0000000000.

## ❌ Actual Result

- Short or mixed invalid inputs are accepted.
- All-zero input is rejected.

## ✅ Expected Result

- The phone number field should:
- Accept only numeric input.
- Enforce exact required length (e.g., 10 digits depending on region).
- Apply consistent validation rules across all invalid cases.
- The phone number field should enforce consistent validation rules aligned with the intended regional or international requirements.

Provide clear error messaging.

## 🎯 Impact

- Data integrity issues.
- Potential backend failures or SMS delivery issues.
- Poor user trust due to inconsistent validation logic.

## Updata
Phone Number Formatting Bug

During exploratory testing, I discovered that the system did not automatically format South African phone numbers correctly. Numbers entered with a leading 0 were not converted to the international +27 format.

✅ Status: Bug caught 
✅ Current behavior: After the fix, phone numbers are now automatically formatted to +27 when a 0 is entered.

https://github.com/user-attachments/assets/a72fb753-9406-4f4e-8499-47683dc3e923


  
