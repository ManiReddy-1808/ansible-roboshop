action = create
passing the instances names in list
1. create instances, loop instance names. item is the keyword
	register the output in variable -> ec2_output
	
	ec2_output.results -> output as list
	
2. loop ec2_output.results list of map
	item -> first map
	
	{{ item.item }} => name
	{{ item.instances[0].private_ip_address }}
	
	frontend-dev.daws88s.online -> private_ip_address
	
	roboshop-dev.daws88s.online -> public_ip_address
	loop: ec2_output.results
	when: 
	- item.item == "frontend"
	- action == "create"

curl http://localhost:8080/health

curl http://catalogue-dev.dawsmani.site:8080/health
curl http://cart-dev.dawsmani.site:8080/health
curl http://user-dev.dawsmani.site:8080/health
curl http://shipping-dev.dawsmani.site:8080/health
curl http://payment-dev.dawsmani.site:8080/health

curl http://mongodb-dev.dawsmani.site:27017/health
curl http://redis-dev.dawsmani.site:6379/health

TO run 1+ play book's at a time: ansible-playbook -i inventory.ini user.yaml; ansible-playbook -i inventory.ini cart.yaml
	

	
	