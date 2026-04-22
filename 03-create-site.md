# Create ERPNext Site

1. Create a new bench folder:
   ```bash
   bench init frappe-bench

2. Navigate into the bench folder:
```bash
cd frappe-bench

3. Create a new site:
```bash
bench new-site mysite.local

4. Follow the setup:
- Enter MySQL root password
- Set administrator password

5. Get ERPNext app:
```bash
bench get-app erpnext

6. Install ERPNext on the site:
```bash
bench --site mysite.local install-app erpnext

7. Start the server:
```bash
bench start

8. Open browser:
   ```text
   http://localhost:8000

9. Login using:
   - Username: Administrator
   - Password: (the one you set during setup)