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
- Windows Server or Ubuntu (depending on your VM OS choice)

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

_Add screenshots of your VM setup and Wireshark captures here._

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
