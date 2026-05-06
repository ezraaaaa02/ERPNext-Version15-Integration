Step 1: Install Frappe Bench

Run:

pip install frappe-bench
Wait until installation completes.

Verify installation with:

bench --version

Expected output: e.g., 5.15.0 (depending on version)

Note: If you see “command not recognized,” make sure the Python Scripts path is added to Environment Variables.

Step 2: Create a new Bench folder

Choose a folder for your ERPNext workspace, e.g.:

mkdir C:\frappe-bench
cd C:\frappe-bench

Initialize a new bench:

bench init my-bench --frappe-branch version-15
Wait for the process to finish. This will download the Frappe Framework and create the my-bench folder.
Step 3: Next Steps

After bench is ready, you can create a new site and install ERPNext:

cd my-bench
bench new-site site1.local
bench get-app erpnext --branch version-15
bench --site site1.local install-app erpnext
These steps will complete ERPNext v15 installation and make it ready for deployment.
