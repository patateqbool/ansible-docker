# ansible-docker

Steps to run a role on a container docker :

Add yourself to docker group : 
* sudo usermod -aG <login>

Create a directory keys in container :
* mkdir keys
* ssh-keygen -t rsa -C "ansible@me.org" -f keys/id-rsa

Run the role on the container :
* ansible-playbook -v --ask-sudo-pass -e "container_name=container ports=['80'] role=laReponse" site.yml

If you have an error : 
* fatal: [localhost]: FAILED! => {"changed": false, "failed": true, "msg": "ConnectionError: ('Connection aborted.', error(2, 'No such file or directory'))"}

run the docker service, on archlinux "systemctl start docker.service"

If you have an error :
* "fatal: [localhost]: FAILED! => {"failed": true, "msg": "list object has no element 0"}"

run "docker kill container"
