#Setting up a container using azure container instance

----------------------------------------------------


A container is basically a unit software that packages up code and all it's dependencies in one environment.
For instance: An Application that requires a web servers (Apache2 or Nginx) and a database (SQL) can be managed in the same environment.
Azure container instance is a simple way to run a container in Azure with out spinnign up a virtual machine.

This is a simple step by step guide on how to use a the Azure Container Instance
PS: There are documentatuions on how to do this , however this is my attempt on explaining it in my own words.
_____________________________________________________________
Step 1:
First step you would need to create an azure account and create a subscription

Step 2: 
In the search tab on azure, search for "Azure Cintainer Instances" 

<img width="631" alt="Screenshot 2022-01-11 at 03 56 53" src="https://user-images.githubusercontent.com/55625732/148878811-494ef6ef-f29a-4ac8-9166-e49d8d4974e1.png">

Create an instance and input details, here is an example:

<img width="808" alt="Screenshot 2022-01-11 at 02 26 34" src="https://user-images.githubusercontent.com/55625732/148878409-2f443892-78c2-4671-b4af-8efd3b3b6401.png">

Step 3: Select the docker image you intend to use
** For instance an alpine image can used from the docker from docker, but in this case the quick start images was used.
https://hub.docker.com/r/rancher/alpine-git

<img width="847" alt="Screenshot 2022-01-11 at 04 13 48" src="https://user-images.githubusercontent.com/55625732/148880019-42a673c9-22a0-4b7b-b24a-09935ac1fd0e.png">

<img width="713" alt="Screenshot 2022-01-11 at 04 09 22" src="https://user-images.githubusercontent.com/55625732/148879704-c48a7103-e2e3-4c8f-bcc8-ff1141b55709.png">

Step 4: Select the size of your container. For this example 1.5GB was used


<img width="285" alt="Screenshot 2022-01-11 at 04 32 00" src="https://user-images.githubusercontent.com/55625732/148881530-67cff041-a778-45ca-960f-1b9b88335ce7.png">

Select a DNS name and Expose the TCP port or any port you intend to use, for this example I exposed the TCP port 80.

<img width="809" alt="Screenshot 2022-01-11 at 02 32 39" src="https://user-images.githubusercontent.com/55625732/148881792-c17a42dd-524a-40f3-b9b9-3ed5fcc809cd.png">

Click next and if done properly the resource (ACL) should be created it usually takes a few seconds to create, the result should look like this:

<img width="848" alt="Screenshot 2022-01-11 at 02 39 10" src="https://user-images.githubusercontent.com/55625732/148882351-47ef69b7-47d2-456a-95cc-abe238e48ab6.png">

Step 5:
Test the your running container, if you used the microsoft image, input the Public IP Address or the DNS name into a tab, The output should look like this:
<img width="935" alt="Screenshot 2022-01-11 at 02 39 20" src="https://user-images.githubusercontent.com/55625732/148882456-6022acc6-771c-43ca-bcd3-f64b0ea47e30.png">
------------------------------------------------------

Alternatively to connect to you your container, you can use a docker app downloaded on your local devices

First 
Download and install application from : https://www.docker.com/get-started

Open your local terminal and input the command: docker run -d -p 80:80 docker/getting-started

Still on your local terminal input the command: docker login azure
(THis will open a browser tab, input the credential for your azure account this would log you into your container)

<img width="383" alt="Screenshot 2022-01-11 at 04 50 16" src="https://user-images.githubusercontent.com/55625732/148883118-ccd7b725-b08f-4148-ac64-4c17598cf3c0.png">

You can consult the official microsoft documentation if you require more information:
 https://docs.docker.com/cloud/aci-integration/
















