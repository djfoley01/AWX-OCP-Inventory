mkdir -p /root/ocp37/group_vars
add ansible-hosts /root/ocp37/ansible-hosts
add OSEv3 /root/ocp37/group_vars

For Ansible Tower:
tower-manage inventory_import --source=/root/ocp37 --inventory-name="OCP37" --overwrite --overwrite-vars

For Ansible AWX:
awx-manage inventory_import --source=/root/ocp37 --inventory-name="OCP37" --overwrite --overwrite-vars

AWX runs as containers on a host server. Simply log in to the docker container and run the steps above.

docker exec -it awx_task bash
cd /root
