## **pharmacy-management-system-in-php-with-source-code **via a sql injection in editPharmacist.

## NAME OF AFFECTED PRODUCT(S)

**pharmacy-management-system-in-php-with-source-code**

## Vendor Homepage

https://code-projects.org/pharmacy-management-system-in-php-with-source-code/

##  **Manufacturers sites:**

 https://code-projects.org/

# AFFECTED  VERSION(S)

## VERSION(S)

-  v1.0

## Software Link

 https://download-media.code-projects.org/2020/10/Pharmacy_Management_System_In_PHP_With_Source_Code.zip

## **AFFECTED FUNCION**

editPharmacist function

# PROBLEM TYPE

## Vulnerability Type

- sql injection

## Root Cause

- editPharmacist function

  A pharmacistID is obtained, and it is concatenated with the sql statement to generate and selectPharmacist to execute the sql statement, causing a vulnerability in SQL injection.

  ![image-20240816205102830](https://github.com/user-attachments/assets/db1f6310-8e6c-427e-a3e0-97351edd2c63)

# Description of the vulnerability

pharmacy_Management_System latest version has SQL injection via **editPharmacist**, which can get information about the database and even GetShell via SQL injection.

# **Vulnerability recurrence**

![image-20240723135616912](https://github.com/user-attachments/assets/93ad21ae-bac1-49a9-afa6-3ae6e70b7a7d)

POC

![image-20240723135729231](https://github.com/user-attachments/assets/f026de01-e9e3-4d0c-bb22-24d1149a3df7)



Result

![image-20240723135912443](https://github.com/user-attachments/assets/e5d84f6e-1c4d-4948-ad0b-8334084f36c7)

![image-20240723140004134](https://github.com/user-attachments/assets/a5073ac6-f787-4b07-973c-03f62d28cf8b)

# Discover

PingXinyao















