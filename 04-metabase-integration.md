# Metabase Integration with ERPNext v15

## 1. Run Metabase using Docker

```bash
docker run -d -p 3000:3000 --name metabase metabase/metabase
```

---

## 2. Access Metabase

Open your browser and go to:
http://localhost:3000

---

## 3. Add ERPNext Database in Metabase

Configure the following:

* **Database type**: MySQL
* **Host**: pwd-db-1
* **Port**: 3306

---

## 4. Retrieve ERPNext Database Credentials

Access the ERPNext backend container:

```bash
docker exec -it pwd-backend-1 bash
cd sites
cat mysite.local/site_config.json
```

Example output:

```json
{
  "db_name": "<your_db_name>",
  "db_password": "<your_db_password>"
}
```

> ⚠️ Do not expose real credentials in public repositories.

---

## 5. Configure Database in Metabase

Use the retrieved values:

* **Database name**: `<your_db_name>`
* **Username**: `<your_db_name>`
* **Password**: `<your_db_password>`

---

## 6. Grant Database Access (if required)

```bash
docker exec -it pwd-db-1 bash
mysql -u root -p
```

```sql
CREATE USER '<your_db_name>'@'%' IDENTIFIED BY '<your_db_password>';
GRANT ALL PRIVILEGES ON `<your_db_name>`.* TO '<your_db_name>'@'%';
FLUSH PRIVILEGES;
```

---

## 7. Verification

After saving the connection in Metabase:

* Connection status should display **Connected**
* Database schema should be successfully synced
* ERPNext tables (e.g., `tabCustomer`, `tabSales Invoice`) should be visible

---

## 8. Outcome

This integration enables:

* Real-time data analytics
* Dashboard and reporting capabilities
* Better business insights from ERPNext data

---

## Conclusion

Metabase has been successfully integrated with ERPNext v15 in a Docker-based environment, allowing efficient data visualization and analysis.
