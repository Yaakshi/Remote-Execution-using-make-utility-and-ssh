### Please follow the below sub-tasks and complete the Task

### 1) Login as a root user.

![image](https://github.com/user-attachments/assets/1c69135a-4377-407c-bea5-a034985f686b)

### 2) Create two users yourrollnumberamrita(client) and yourrollnumbercoimbatore(server) with passwords.

![image](https://github.com/user-attachments/assets/1c03562f-fec3-4ffd-8dd2-d77edf6f207d)

### 3) Login as yourrollnumberamrita. Use ssh to create the private and public ids at the location /home/yourrollnumberamrita/.ssh

Checking is ssh is already installed:
![image](https://github.com/user-attachments/assets/4f8895e5-0ea6-4957-beb2-6411922c3bb6)

![image](https://github.com/user-attachments/assets/6992945e-e2aa-4d0d-b78f-2d5a30f57e6f)

### 4) Then copy the public id file to the /home/yourrollnumbercoimbatore/.ssh/authorized_keys

![image](https://github.com/user-attachments/assets/16f5ecd5-06f9-4e17-8e57-9fdc2d379a2e)

### 5) Do the necessary steps if required (editing ssh config files and restarting the service, providing permissions for .ssh and .ssh/ authorized_keys etc..)

Changing persmission of client ssh to 700 that ensures only the owner can access the .ssh directory.

Changing persmission of server ssh to 600 that ensures only the owner can view or modify the file, which stores the public keys for SSH authentication.

![image](https://github.com/user-attachments/assets/0844729d-fa35-4c8d-bd51-69e40eeecadd)

(text files do not have execute permissions)

![image](https://github.com/user-attachments/assets/60d86648-7ac5-46e8-abfa-1fdf9fe14766)

![image](https://github.com/user-attachments/assets/e92a2be9-0724-44e6-9fa2-c9fd24dd00d1)

Editing config files through sudo user account:
![image](https://github.com/user-attachments/assets/ee8bdfda-18e0-4b1d-b430-297e8de36741)

Uncommenting the lines to permit authentication via public keys and not using passwords.

![image](https://github.com/user-attachments/assets/b0cd8887-f54b-4ce9-a359-5704c0921532)
![image](https://github.com/user-attachments/assets/1745712e-0166-457c-a9d1-7a217b73e976)

Restarting ssh to for changes to take effect:

![image](https://github.com/user-attachments/assets/ae30729e-7a63-4456-8225-cac5b5029c52)

### 6) Check are you able to login without a password from yourrollnumberamrita to yourrollnumbercoimbatore using ssh

![image](https://github.com/user-attachments/assets/be81766f-1db6-47ed-8eaf-1b6466946a8e)

### 7) Then switch user to yourrollnumberamrita.

![image](https://github.com/user-attachments/assets/933f193f-1c77-4ebb-9c6e-94fe6ab5c259)

### 8) Write a script remoteshell.sh which will do the following sub-tasks:
  - ### a) Printing the name of current login user
  - ### b) This step is done based on your roll number. Run a makefile that prints the number is (Prime (odd roll number)/Palindrome (even roll number)) using a binary file (Prime/Palindrome). Write C program according to your roll number and include the linking steps in the makefile.
  - ### c) Copy the binary file (Prime/Palindrome) to the home directory of user yourrollnumbercoimbatore using scp.
  - ### d) Using ssh, log in to yourrollnumbercoimbatore and remotely execute the commands for printing the name of current login user and executing the binary file (Prime/Palindrome).

remoteshell.sh:

![image](https://github.com/user-attachments/assets/5ab9a4aa-0acb-451f-895e-204012dff3f8)

Adding execute permission to remoteshell.sh:
![image](https://github.com/user-attachments/assets/336bb603-1113-4787-8119-8c04890d16a6)

C program to determine whether the roll number is prime or not:
![image](https://github.com/user-attachments/assets/296da4ae-0a2e-4823-aa96-17eb00ff590e)

Makefile to link the prime.c file to executable binary file:

![image](https://github.com/user-attachments/assets/65fa5da8-9413-4ecb-a490-4f246a02a3cc)

Remote execution:

![image](https://github.com/user-attachments/assets/f3e95739-1c28-473d-99d6-857871cf5ae0)

In order to not display the welcome messages:

Switch to sudo user account:

![image](https://github.com/user-attachments/assets/9ec2c221-4212-4a15-b3bf-4b054ffff2a8)

Remove execute permissions to the below directory and restart ssh for the changes to take effect:
![image](https://github.com/user-attachments/assets/e3346409-8d94-4a5d-a3f2-6144528b087f)

Switch to client user and execute the remoteshell:
![image](https://github.com/user-attachments/assets/6e047705-64ae-4700-9304-f912c9bc51f0)
