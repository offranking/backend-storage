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

### Now run terraform init to initialize your Terraform project. This command downloads the required provider plugins, configures the backend, and prepares the working directory so Terraform can run properly

<img width="1162" height="249" alt="Screenshot 2025-09-18 at 10 14 41 pm" src="https://github.com/user-attachments/assets/1449e1fd-7c2c-4f09-a529-0ea5a66723c1" />

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





