# terraform-mini
Mini project - terraform EC2 Instance and AMI Creation


###  Working with Terraform: Logging into AWS and Connecting via SSH

<img width="1440" height="814" alt="Screenshot 2025-08-08 at 1 27 54 pm" src="https://github.com/user-attachments/assets/ef0372b8-698e-4c9e-a417-90e4753d1011" />

# SSH KEY
<img width="1425" height="749" alt="Screenshot 2025-08-08 at 1 29 56 pm" src="https://github.com/user-attachments/assets/d3f35b05-cd9d-49d1-ba8f-0e45a88fcac8" />

# connect
<img width="1432" height="341" alt="Screenshot 2025-08-08 at 1 34 05 pm" src="https://github.com/user-attachments/assets/cd762ab1-5ebb-4b58-bfe3-d2f7779eef15" />
<img width="1424" height="480" alt="Screenshot 2025-08-08 at 1 35 22 pm" src="https://github.com/user-attachments/assets/e812a1e4-80dd-40e8-82e7-7f44703de479" />

# connect to terminal
<img width="1440" height="900" alt="Screenshot 2025-08-08 at 1 37 53 pm" src="https://github.com/user-attachments/assets/3271c007-1860-4fd0-8925-25d51664eb65" />

Before installing the AWS Command Line Interface (AWS CLI), it’s important to make sure your system packages are up to date. This ensures that your installation goes smoothly and avoids compatibility issues.
run " sudo apt update "

<img width="852" height="254" alt="Screenshot 2025-08-08 at 1 49 33 pm" src="https://github.com/user-attachments/assets/e6fecb22-92c7-467e-94b6-48d7c72e847a" />

### Now we need to Download the latest package
### curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
<img width="1290" height="153" alt="Screenshot 2025-08-08 at 1 56 37 pm" src="https://github.com/user-attachments/assets/e13b6f86-872e-423d-9f13-f71b6190c7c9" />

### We have to install unzip by the follow you commmand sudo apt install unzip

<img width="1149" height="511" alt="Screenshot 2025-08-08 at 3 40 23 pm" src="https://github.com/user-attachments/assets/0dd572fd-6866-4bf2-b2fd-ae0c8182b5ea" />

### on this part we need to  unzip awscliv2.zip
run "unzip unzip awscliv2.zip " on your local terminal


<img width="933" height="632" alt="Screenshot 2025-08-08 at 3 47 27 pm" src="https://github.com/user-attachments/assets/daf3b1ea-acaa-45e0-a9bc-d8e2c0544e4c" />

### the next step is to install the awscli
run "sudo ./aws/install"
<img width="690" height="41" alt="Screenshot 2025-08-08 at 3 48 52 pm" src="https://github.com/user-attachments/assets/495522b3-b239-47f7-9a49-0f59bd8ff271" />

After installing AWS CLI, you should verify the installation by checking its version. If the installation was successful, this command will display the installed AWS CLI version along with Python version and OS details. This confirms that AWS CLI is ready to use on your system.
"aws --version"

<img width="704" height="38" alt="Screenshot 2025-08-08 at 3 49 45 pm" src="https://github.com/user-attachments/assets/463a279c-2e5c-4674-ab58-d141b47398e0" />

The next step is to install Terraform, but before we begin, we must update our system’s package list to ensure we get the latest versions of available packages.
"sudo apt update"


<img width="803" height="197" alt="Screenshot 2025-08-08 at 4 05 22 pm" src="https://github.com/user-attachments/assets/d3b4bf4d-f271-460a-8fdc-8b24976df57a" />

 Install Terraform on Linux (Ubuntu/Debian) Update system
"sudo apt update && sudo apt install -y gnupg software-properties-common curl"

<img width="1338" height="502" alt="Screenshot 2025-08-08 at 4 08 52 pm" src="https://github.com/user-attachments/assets/52ca6123-eea2-4585-a5f1-6e837960954a" />

# Add HashiCorp GPG key
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

<img width="1440" height="63" alt="Screenshot 2025-08-08 at 4 10 10 pm" src="https://github.com/user-attachments/assets/1c6c9b69-7b7f-4cfc-ba0b-68f167c5f4cf" />

# Add official HashiCorp repo
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
<img width="1440" height="57" alt="Screenshot 2025-08-08 at 4 11 38 pm" src="https://github.com/user-attachments/assets/5a530c1f-bb9f-4a33-8ab3-52ad9ad2bc44" />


# Install Terraform
sudo apt update && sudo apt install -y terraform

<img width="1111" height="769" alt="Screenshot 2025-08-08 at 4 12 59 pm" src="https://github.com/user-attachments/assets/aa31b58d-a50c-4327-8646-5af7a7b2db1a" />

Now we have to check the terraform vassion

"terraform --version

<img width="838" height="82" alt="Screenshot 2025-08-08 at 4 18 35 pm" src="https://github.com/user-attachments/assets/2e63a351-f7a3-4be8-9428-ea9b5169bef9" />

Now we have to create a directry for the terraform.

"mkdir terraform-ec2-ami"

<img width="957" height="25" alt="Screenshot 2025-08-08 at 4 28 50 pm" src="https://github.com/user-attachments/assets/6c4314bc-f28f-4c4d-9f39-80240ebff916" />

the next thing is to cd in to the directry 
"cd terraform-ec2-ami"
<img width="715" height="26" alt="Screenshot 2025-08-08 at 4 29 50 pm" src="https://github.com/user-attachments/assets/b1c6f399-f241-466d-b0ee-fb83aa9e1dc3" />

nano main.tf
<img width="840" height="28" alt="Screenshot 2025-08-08 at 4 39 08 pm" src="https://github.com/user-attachments/assets/f6e4b586-0a1c-4daf-a8d7-bed260df2f1e" />

ls to check the file main.tf

<img width="848" height="47" alt="Screenshot 2025-08-08 at 4 41 45 pm" src="https://github.com/user-attachments/assets/03f3e1b6-4427-4adb-b379-c6355d861080" />

cat main.tf

<img width="1440" height="204" alt="Screenshot 2025-08-08 at 4 42 40 pm" src="https://github.com/user-attachments/assets/5bf4653e-7e92-4295-a5ed-702913cfe18a" />











