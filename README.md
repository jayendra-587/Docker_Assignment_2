#Assignment  - Dockers and Containers
https://www.cs.utexas.edu/~vijay/cs378-f17/projects/assignment2.htm
Refer the above link
Introduction
The goal of this assignment is to get you familiarized with dockers. You will learn about how to dockerize any application by building a simple client and server containers using dockers.
What is to be done?
To install and get started with docker follow this link: Get Started with Dockers
You will be building two containers using docker. These containers can be built starting from an official base image. Official Images has a list of different official base images. Start from the image that is suitable for you.
•	Server :
o	Create a volume by name "servervol".
o	The server container will mount "servervol" in "/serverdata".
o	This container runs a server application which will create a file of size 1KB with random text data in "/serverdata" and then transfer the file to the client along with the checksum.
o	The server application itself can be built using any language you are comfortable with. But, the container should include all the packages that are required to run your application. Choose your base image wisely and install only the necessary packages.
o	The port on which the server runs must be specified as a command line argument when we run docker.
•	Client:
o	Create a volume by name "clientvol".
o	The client container will mount "clientvol" in "/clientdata".
o	The client container runs an application that connects to the server, recieves the file that the server sends and saves it in "/clientdata".
o	Verify that the file is received properly at the clientside by verifying the checksum.
o	The client application again can be wriiten in any language that you are comfortable with, but the container should include all the necessary packages. Choose your base image wisely and install only necessary packages.
You need to create a user-defined network in docker and run both these containers on the network created. The containers should run these applications by default (i.e, on run command). Mention in README as to what should be done to get into the container shell instead of running the applications by default (i.e, on run command).
NOTE: You should be able to get into the shell of the client container to physically check if the file has been recieved.
What to submit?
•	Create a new empty branch in your git repos named "assignment2".
•	You will be submitting the files that you use to build the server and client containers. Checkout the assignment2 branch and submit the files related to server and client in two folders named "server" and "client" respectively.
•	As you go about doing the assignment, you will learn that there are multiple ways to create volumes and to have the containers communicate to each other. So submit a README file that expains what method you use.
•	Create two scripts. one for the server("fileserver.sh") and the other for the client ("fileclient.sh") that has all the commands to build and run server and client containers respectively. These scripts should include the volume creation for client and server respectively. The server script should also include the creation of user-defined network before server runs.
•	The scripts and the README should be in the root of your branch (outside your server and client directories).
Grading
What is tested?
•	Run the "fileserver.sh" script on one terminal. It should create the user-defined network, the "servervol", start the server and wait for the client connection.
•	Run "fileclient.sh" in another terminal. This script should find out the server's IP, create the "clientvol" and run the client container by specifying server's IP and port as command line parameters.
•	When the client container is run, a connection between the server and client is established and the file is transferred from the server to the client.
•	Your code and scripts will be tested on creation of volumes, proper running of server and client and file transfer.
•	You should make sure that the server can transfer any file with random text and the checksum verification succeeds on the client when it receives the file.
Grade Distribution
•	Build and run server container - 30 points
•	Build and run client container - 30 points
•	Proper communication between the two - 15 points
•	Scripts to run the containers - 15 points
•	README file - 10 points

