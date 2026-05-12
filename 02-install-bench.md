## Step 1: Check Prerequisites
Make sure Python 3.10+ and pip are installed on your system. Also, Git, Docker & WSL2 must be installed.

## Step 2: Install Frappe Bench
Run:

```bash
pip install frappe-bench
```
verify installation:
```bash
bench --version
```
Expected output: e.g., 5.15.0 (depending on version)
Note: If you see “command not recognized,” make sure the Python Scripts path is added to Environment Variables.

Step 3: Create a new Bench folder

Choose a folder for your ERPNext workspace:
```bash
mkdir C:\frappe-bench
cd C:\frappe-bench
```
Initialize a new bench:
```bash
bench init my-bench --frappe-branch version-15
```
Wait for the process to finish. This will download the Frappe Framework and create the my-bench folder.

Step 4: Create a Site & Install ERPNext

After bench is ready, run:
```bash
cd my-bench
bench new-site site1.local
bench get-app erpnext --branch version-15
bench --site site1.local install-app erpnext
```
These steps will complete ERPNext v15 installation and make it ready for deployment.
