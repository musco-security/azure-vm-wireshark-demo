# azure-vm-wireshark-demo

This project demonstrates how to use Microsoft Azure to create and configure two virtual machines (VMs) for network packet capture using Wireshark. One VM acts as the monitoring station with Wireshark installed, and the other is used to simulate traffic for analysis.

## 🔧 What This Project Covers

- Provisioning two Azure virtual machines
- Setting up network rules and connectivity between the VMs
- Installing Wireshark on one VM
- Capturing and analyzing packets between the two VMs

## 📦 Tools and Services Used

- Microsoft Azure (Virtual Machines, Resource Groups, Network Security Groups)
- Remote Desktop Protocol (RDP)
- Wireshark
- Windows Server or Ubuntu 

## ✅ Learning Objectives

- Understand how to set up networked VMs in Azure
- Learn basic packet capture techniques with Wireshark
- Explore network communication and troubleshooting in a cloud environment

## 🚀 Getting Started

1. Create a new Azure resource group.
2. Deploy two VMs in the same virtual network.
3. Open necessary ports (RDP, ICMP, etc.) via Network Security Groups.
4. Install Wireshark on one VM.
5. Use the second VM to send pings or HTTP traffic.
6. Capture traffic on the first VM using Wireshark.

## 📸 Screenshots
Create an account with Microsoft Azure and choose a subscription to get to the home page of Azure
![Screenshot 2025-06-09 9 46 42 PM](https://github.com/user-attachments/assets/405c154a-b484-4272-a629-d2aaf3cb86f6)
Next we need to create a resource group to create our virtual machines in 
![Screenshot 2025-06-09 9 46 48 PM](https://github.com/user-attachments/assets/bfee635f-eb04-4673-bb60-8c772b261fa6)
Click the resource group link, and type in what the name you want to call the resource group and what subscription you're attaching it to, and lastly the region that you want to store it in
![Screenshot 2025-06-09 9 51 42 PM](https://github.com/user-attachments/assets/86f86388-0a6c-4818-860f-80ddbd4b5c10)
Next click on the review and create tab to process the resource group to complete it
![Screenshot 2025-06-09 9 52 20 PM](https://github.com/user-attachments/assets/6c0b7fa7-da9c-45fa-a4e0-d1ec5092278d)
After completing the request to have your resource group created, then go back to the resource group tab to make sure it is showing up. If not, just refresh your page to see it
![Screenshot 2025-06-09 9 52 53 PM](https://github.com/user-attachments/assets/4ebadcf7-27be-4df5-ac61-2d748fd6cda9)
Next, I clicked on virtual machines and then create so we can start the process for creating our windows virtual machine
![Screenshot 2025-06-09 9 54 06 PM](https://github.com/user-attachments/assets/78f3b209-aad7-4766-8037-33671c16e80c)
![Screenshot 2025-06-09 9 54 16 PM](https://github.com/user-attachments/assets/73da6bf8-5b85-44b7-a834-4ed30f4f4847)
Choose the subscription and resource group that we created and I chose to name the first virtual machine "windowsvm" and select the same region that we chose for the resource group
![Screenshot 2025-06-09 10 05 15 PM](https://github.com/user-attachments/assets/5290f89c-82a7-47a8-85dd-6f7552b28266)
The main thing in this screenshot; we selected the windows 10 Pro image for this vm and selected the available zones
![Screenshot 2025-06-09 10 05 26 PM](https://github.com/user-attachments/assets/295e174f-eaa6-4fbe-b739-53df8a76c107)
Click next, we chose image default OS disk size, and we chose Premium SSD for local redundant storage
![Screenshot 2025-06-09 10 07 04 PM](https://github.com/user-attachments/assets/1e264d51-8549-40b3-8030-bd63d1f0926a)
Here we went to the next tab to set up the networking details. I named the virtual network chose the subnet for this VM, then I chose to allow selected ports for this lab like RDP 3389
![Screenshot 2025-06-09 10 22 28 PM](https://github.com/user-attachments/assets/87d7cff2-3b35-4a2f-b90e-92995976a4c2)
After clicking review and create, wait for the validation pass and then click create to submit it for processing which should take a few minutes
![Screenshot 2025-06-09 10 24 19 PM](https://github.com/user-attachments/assets/1d95b85c-2107-4817-b333-4572e47f95d2)
I created a budget to keep track of the expense that the resource group grows monthly throughout the next two years
![Screenshot 2025-06-09 10 30 29 PM](https://github.com/user-attachments/assets/75458537-9e04-4ac9-b66b-c22c9cceab8a)
After making budget, I clicked review and create to process the creation of the windows vm
![Screenshot 2025-06-09 10 47 26 PM](https://github.com/user-attachments/assets/3d861778-1598-466e-9553-82bca8425d82)
Our Windows vm shows in the vitrual machine list
![Screenshot 2025-06-09 10 50 00 PM](https://github.com/user-attachments/assets/53001b94-062d-4602-9c76-bd92ac06cc35)
creating a second vm to monitor traffic between both virtual machines
![Screenshot 2025-06-09 10 50 41 PM](https://github.com/user-attachments/assets/e0514027-d1ff-4e1f-adea-e9215fadf978)
I created this new vm under the same subscription, resource group and region that I created the first vm
![Screenshot 2025-06-09 10 52 03 PM](https://github.com/user-attachments/assets/eeac7128-4c0f-4aaf-babe-ddcd4b2f19db)
I chose to make the vm image an ubuntu OS
![Screenshot 2025-06-09 11 14 21 PM](https://github.com/user-attachments/assets/173ec526-6b5e-4c62-ba13-cc6ca2b5f5ee)
Next, I created this vm in the same virtual network and subnet as my first vm
![Screenshot 2025-06-09 11 38 25 PM](https://github.com/user-attachments/assets/416554f9-adc1-4bb6-9489-46613fd3c535)
After clicking review and create the VM, I went back to the virtual machines tab to see that my Linux vm was created
![Screenshot 2025-06-09 11 42 17 PM](https://github.com/user-attachments/assets/a520ee87-db9b-472d-8b72-99b24b280c73)
From the virtual machine screen, I clicked on the WindowsVM to start it and begin the download of wireshark on this vm and start monitoring the network traffic wireshark picks up between both VMs 
![Screenshot 2025-06-10 12 23 38 AM](https://github.com/user-attachments/assets/f89d6f04-0881-4815-9087-9f406090a308)
I used both remote desktop app and bastion inside of Azure to remote login to the VMs
![Screenshot 2025-06-23 8 32 29 PM](https://github.com/user-attachments/assets/6c339787-c592-46d3-82e2-b98b83b90df6)
After logging into Wireshark, I clicked on the ethernet option because traffic was being picked up so I chose that option to start
![Screenshot 2025-06-23 8 46 34 PM](https://github.com/user-attachments/assets/a0d71a25-5453-4051-9d11-cb89dcb47767)
I opened powershell app to start with commands
![Screenshot 2025-06-23 9 06 27 PM](https://github.com/user-attachments/assets/59ad08f7-ecdd-4563-a961-01ba2a9277b5)
Listening for icmp traffic, I used a ping command to my other VM
![Screenshot 2025-06-23 9 09 41 PM](https://github.com/user-attachments/assets/a8f4f72a-489b-4764-851e-aaf4a9759d00)
I opened the network security group (firewall) on Azure to create a rule to drop the icmp traffic
![Screenshot 2025-06-24 8 24 42 PM](https://github.com/user-attachments/assets/aa63581f-491e-42e1-bc2c-598a5261a8e8)
After creating the firewall rule to drop the icmp traffic and now we see that the ping is timing out
![Screenshot 2025-06-24 8 32 13 PM](https://github.com/user-attachments/assets/4782b755-6888-4f1d-b6c1-7040af97ae9b)

![Screenshot 2025-06-24 10 04 30 PM](https://github.com/user-attachments/assets/585f8ccd-b5c5-4b85-b737-286079eb40ab)
I used the ssh command to connect to my other vm and monitored the traffic 
![Screenshot 2025-06-24 10 12 20 PM](https://github.com/user-attachments/assets/058e2be0-7db2-4191-a72c-c91bf23a1c72)
From Wireshark I have selected to listen for icmp traffic and I started a ping command 
![Screenshot 2025-06-24 10 26 32 PM](https://github.com/user-attachments/assets/170f2589-ba0e-43e6-9e1a-cec25629f0bc)
From Wireshark I selected to listen for dhcp traffic, and started a ipconfig /renew command 
![Screenshot 2025-06-24 10 46 59 PM](https://github.com/user-attachments/assets/113851a3-7876-4899-98c3-c21fad2da5d1)
I monitored the traffic when I used the nslookup command to find the ip address of disney.com
![Screenshot 2025-06-24 11 20 12 PM](https://github.com/user-attachments/assets/dfedee5b-ebd9-4c26-a157-c5ac56d123a5)
Used nslookup command to look up ip address for pixar website
![Screenshot 2025-06-24 11 23 06 PM](https://github.com/user-attachments/assets/836d2dba-ada5-4450-96b6-cb35bd11eb30)



## 🧠 Notes

- Ensure both VMs are in the same virtual network for packet visibility.
- You may need to run Wireshark as administrator to see all interfaces.
- Keep security in mind when exposing ports.

## 🗂️ Project Status

✅ Completed  
📅 Last updated: `June 2025`

## 📚 References

- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [Microsoft Azure Docs](https://learn.microsoft.com/en-us/azure/virtual-machines/)
