# Deploy OpenShift Container Platform from Ansible Tower & AWX

Create the directories naming convention based on the version you are using.

### Set up directory structure
```bash
mkdir -p /root/ocp39/group_vars
```
add ansible-hosts /root/ocp39/ansible-hosts
add OSEv3 /root/ocp39/group_vars

These steps should already be done when you clone this repo. 
You should just have to clone this repo, then run the import command below.

### Import Inventory
For Ansible Tower, the steps are simple, log in to the Ansible Tower server, clone the repo and run this command:
```bash
tower-manage inventory_import --source=/root/ocp39 --inventory-name="OCP39" --overwrite --overwrite-vars
```

For Ansible AWX, ensure you log in to the awx_task container first.
```bash
docker exec -it awx_task bash
cd /root
awx-manage inventory_import --source=/root/ocp39 --inventory-name="OCP39" --overwrite --overwrite-vars
```
