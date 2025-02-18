# pc
troubleshooting msp


1.. Check currnt state of the PC cluster

cs | grep -v UP


2.. Find out the current state of the MSP controllers and the component health

mspctl cluster list
mspctl cluster get 
mspctl cluster health

if any component unhealthy run this:

mspctl cluster health -c addons/extensions (this is example)

3.. Find out the current state of the PC especially the pods.

sudo kubectl get pods -A
sudo kubectl logs -n ntnx-base cape-xx-xx /// get cape-xx-xx uuid from above command
sudo kubectl describe pod -n ntnx-base cape-c9c99d899-xx
sudo kubectl logs -n ntnx-base iam-user-auth
sudo kubectl logs -n ntnx-base iam-proxy-control-plane
sudo kubectl describe pod -n ntnx-base iam-user-auth
sudo kubectl describe pod -n ntnx-base iam-proxy-control-plane


4. make sure each pcvm communication to one another is ok also. sanity check such as sshing each other
