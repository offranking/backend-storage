## backend-storage
terraform Modules - VPC and S3 Bucket with Backend Storage

## Connect to your AWS instance. This is typically done using SSH from your terminal, with the path to your private key file (.pem) and the public DNS or IP address of your EC2 instance. The command will look something like this, but you'll need to replace the placeholder values with your own: 
"mkdir terraform-modules-vpc-s3" and cd terraform-modules-vpc-s3

<img width="822" height="39" alt="Screenshot 2025-09-18 at 12 13 03 pm" src="https://github.com/user-attachments/assets/4f26dedb-2eca-4904-a37b-b72f69218614" />


### make an other directory called "mkdir -p modules/vpc
                               "mkdir -p modules/s3

<img width="892" height="94" alt="Screenshot 2025-09-18 at 12 14 09 pm" src="https://github.com/user-attachments/assets/2ff12bfa-55d1-4fd9-a832-1f44ba862e86" />

### Open the main.tf file in the frontend directory using Nano, then paste the code into it

<img width="1436" height="900" alt="Screenshot 2025-09-18 at 9 55 07 pm" src="https://github.com/user-attachments/assets/f0f840f0-abd7-4cb3-8296-bd4ecca3a99d" />

### create your s3 burket
<img width="1417" height="738" alt="Screenshot 2025-09-17 at 2 39 53 pm" src="https://github.com/user-attachments/assets/54f6de58-163b-471a-986e-2ad789f05670" />

<img width="1436" height="779" alt="Screenshot 2025-09-17 at 2 45 38 pm" src="https://github.com/user-attachments/assets/1b03a5ca-c4de-4104-a719-9e0f6e4799c3" />

### add your file and upload it in the s3 

<img width="1433" height="727" alt="Screenshot 2025-09-17 at 2 44 43 pm" src="https://github.com/user-attachments/assets/8ec85c9c-c0ee-445d-b4b3-544cf4aa14ba" />

### s3 is successful created 
<img width="1440" height="900" alt="Screenshot 2025-09-17 at 2 42 29 pm" src="https://github.com/user-attachments/assets/fc0363cd-b7df-4e2a-b621-9ad25830247c" />

### after that you need to open your backend file using backend.tf save it with "wq"

<img width="1436" height="900" alt="Screenshot 2025-09-18 at 10 06 16 pm" src="https://github.com/user-attachments/assets/33ce783a-b27b-4e42-9f89-24957e5e1f4a" />



### Next, run terraform validate to check your configuration files. This command verifies that the syntax is correct, all required arguments are provided, and the configuration is internally consistent. It doesn’t access remote services but ensures your Terraform code is properly structured before applying
<img width="838" height="56" alt="Screenshot 2025-09-18 at 10 15 27 pm" src="https://github.com/user-attachments/assets/d50a31c0-c7ce-4be3-856a-b71112d8c590" />

### Now run terraform plan to create an execution plan. This command compares your configuration against the real infrastructure, determines what actions need to be taken (create, update, or destroy resources), and displays them for review. It doesn’t make any changes yet — it only shows what Terraform would do if you run terraform appl

<img width="1436" height="900" alt="Screenshot 2025-09-18 at 10 16 47 pm" src="https://github.com/user-attachments/assets/a42f0e93-921d-489e-b1cf-52d793f39bec" />

### Finally, run terraform apply to provision your infrastructure. This command executes the changes shown in the plan by creating, updating, or destroying resources as required. Terraform will display the proposed actions again and prompt you with Do you want to perform these actions? (yes/no). Type yes to confirm, and Terraform will apply the changes. Once complete, it will show the details of the resources created or modified


<img width="1436" height="852" alt="Screenshot 2025-09-18 at 10 17 28 pm" src="https://github.com/user-attachments/assets/5b2eed44-a934-429c-96dc-d962fac3fb82" />



### After applying, copy the public IP address of your deployed resource (such as an EC2 instance or load balancer) and paste it into your web browser’s address bar. Press Enter, and you should see the application or webpage running on that server
ip "http://54.83.184.30/"
<img width="1362" height="333" alt="Screenshot 2025-09-18 at 10 18 43 pm" src="https://github.com/user-attachments/assets/05b501e3-7384-4109-9354-1c2eebd29aae" />

### After opening the public IP in your web browser, you should see the application’s default webpage confirming that your infrastructure was successfully deployed


<img width="1436" height="813" alt="Screenshot 2025-09-18 at 3 06 33 pm" src="https://github.com/user-attachments/assets/7fc95bc0-447f-4dda-9827-a9a3d05c4c62" />

### Finally, run terraform destroy to tear down the infrastructure you created. This command scans your state file, determines all the resources currently being managed by Terraform, and generates a destruction plan. It will then prompt you with Do you really want to destroy all resources? (yes/no). Type yes to confirm, and Terraform will proceed to delete every resource it created, such as EC2 instances, VPCs, S3 buckets, etc. Once complete, your environment will be fully removed, and you’ll see confirmation in the terminal.

<img width="1436" height="852" alt="Screenshot 2025-09-19 at 3 35 46 pm" src="https://github.com/user-attachments/assets/7f0e5619-53b3-4b73-b96b-e66ed30cbe55" />

### Now run terraform init to initialize your Terraform project. This command downloads the required provider plugins, configures the backend, and prepares the working directory so Terraform can run properly

<img width="1162" height="249" alt="Screenshot 2025-09-18 at 10 14 41 pm" src="https://github.com/user-attachments/assets/1449e1fd-7c2c-4f09-a529-0ea5a66723c1" />

### After completing the frontend setup, you now need to reconfigure Terraform’s backend. To do this, edit the backend configuration in your Terraform files (for example, update the S3 bucket name, key, region, or DynamoDB table in the terraform block). Once you’ve saved the changes, run the command terraform init -reconfigure. This command forces Terraform to reinitialize the working directory, reconfigure the backend with the new settings, and migrate or refresh the state as required. It ensures Terraform uses the updated backend configuration instead of the previous one

<img width="1064" height="307" alt="Screenshot 2025-09-19 at 2 50 00 pm" src="https://github.com/user-attachments/assets/a44c3040-ad6f-4064-ba36-2062f9081021" />

### After reinitializing the working directory and updating the backend with the new settings, run terraform init again. This command initializes the Terraform environment by downloading the necessary provider plugins, setting up the backend for state storage, and preparing the working directory for further commands. It ensures that Terraform is properly configured to use the updated backend and is ready for validation, planning, and applying

<img width="1437" height="311" alt="Screenshot 2025-09-19 at 3 45 21 pm" src="https://github.com/user-attachments/assets/4321dc17-ee51-46a7-98a9-ae410418b404" />

### After initialization, run terraform validate to check your configuration. This command parses all your .tf files, verifies that the syntax is correct, ensures all required arguments are present, and confirms that the configuration is internally consistent. It does not contact any remote services or APIs — it’s a local check to make sure your code is structurally sound before moving on to terraform plan or terraform apply. If everything is correct, Terraform will return Success! The configuration is valid.; if not, it will display errors that you need to fix

<img width="838" height="74" alt="Screenshot 2025-09-19 at 3 22 45 pm" src="https://github.com/user-attachments/assets/fe790dfb-9f3c-44c3-9818-642ca0f872b4" />

### After validation, run terraform plan to generate an execution plan. This command compares your configuration files with the current state of your infrastructure and determines what changes are required. It will show you whether Terraform needs to create new resources, update existing ones, or destroy any that are no longer defined. The plan output is a preview only — no resources are changed at this stage. If everything looks correct, you can proceed with terraform apply to make the changes

<img width="1355" height="115" alt="Screenshot 2025-09-19 at 3 25 03 pm" src="https://github.com/user-attachments/assets/2bb7b6e6-ec9f-4673-ae8c-30c867ad2829" />

### Once you’ve reviewed the execution plan, run terraform apply to provision your infrastructure. This command re-runs the plan, shows you the actions that will be taken, and then asks for confirmation with the prompt

<img width="1287" height="111" alt="Screenshot 2025-09-19 at 3 25 55 pm" src="https://github.com/user-attachments/assets/1fba2fa1-1b8e-4f64-a4a5-c86d06c13427" />





