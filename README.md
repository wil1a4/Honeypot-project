# # T-Pot Cybersecurity Project on Microsoft Azure

## Overview

This project involves deploying the T-Pot honeypot on a Microsoft Azure virtual machine running Debian Bullseye OS. T-Pot is a comprehensive honeypot platform used to collect and analyze attack data, providing valuable insights into cybersecurity threats.

## Objectives

- Deploy T-Pot on a cloud-based virtual machine.
- Collect and analyze cybersecurity threat data.
- Understand the deployment and management of honeypots.
- Gain hands-on experience with cloud platforms and cybersecurity tools.

## Skills Gained

- Cloud computing with Microsoft Azure
- Virtual machine deployment and management
- Honeypot configuration and deployment
- Cybersecurity threat analysis
- Linux system administration

## Tools Used

- Microsoft Azure
- Debian Bullseye OS
- T-Pot Honeypot
- SSH for remote server management
- Windows local machine cmd

## Steps

1. **Create Azure VM**
   - Log in to the [Azure Portal](https://portal.azure.com).
   - Create a new virtual machine using Debian Bullseye as the operating system.
   - Configure the VM's network security group to allow inbound SSH connections on a custom port.

2. **Access VM via SSH**
   - Use the provided private key to access the VM:
     ```sh
     ssh -i mykey.pem azureuser@your_vm_ip
     ```
     ![1 01](https://github.com/wil1a4/Honeypot-project/assets/129964763/23b0614e-f271-4721-8daf-b7fa3c6babcd)

3. **Install T-Pot**
   - Update the package list and install required dependencies:
     ```sh
     sudo apt update && sudo apt upgrade -y
     ```
     ![1 1](https://github.com/wil1a4/Honeypot-project/assets/129964763/dc7fa752-2804-4a53-bd46-79cd8c6f0684)

   - Follow the [official T-Pot installation guide](https://github.com/telekom-security/tpotce) to install T-Pot.

5. **Configure Network Security Group**
   - Add inbound port rules for necessary ports (e.g., 64295 for SSH, 80 and 443 for web access) in the Azure Portal.
   ![2 3](https://github.com/wil1a4/Honeypot-project/assets/129964763/72c29766-6da3-4cf7-893e-15373765f99f)

6. **Remove lock files**
   ```sh
     sudo rm /var/lib/dpkg/lock-frontend
     sudo rm /var/lib/dpkg/lock
   
7. **Reconfigure Dpkg**
   ```sh
     sudo dpkg --configure -a

8. **Update the Package Lists and Installation of Packages using apt-get with Configuration Options**
    ```sh
      sudo apt update
      sudo /usr/bin/apt-get -y -o "Dpkg::Options::=--force-confdef" -o "Dpkg::Options::=--force-confold" install 'gnupg' 'grc' 'htop' 'micro'
    
9. **Access T-Pot Web Interface**
   - After installation, reboot the VM and access the T-Pot web interface using the VM's public IP address and the appropriate port (default is `64297`).
     

10. **Analyze Threat Data**
   - Use the T-Pot dashboard to monitor and analyze incoming attack data.
     ![1 6](https://github.com/wil1a4/Honeypot-project/assets/129964763/5ee09f6c-effc-4ce0-aaf4-3a6d285845d7)
    
11. **Attack map surface**
    ![1 8](https://github.com/wil1a4/Honeypot-project/assets/129964763/32e7737d-869d-4bc9-9a06-bdaafa977cc6)

12. **Honeytrap kibana dashboard** 
      ![2 5](https://github.com/wil1a4/Honeypot-project/assets/129964763/b4e0b042-0c2f-4b3b-a769-b66dcdad171c)

      ![2 6](https://github.com/wil1a4/Honeypot-project/assets/129964763/b9b0f7f5-d8ca-49ff-922d-92d5b3b9f596)

13.  **Security meter**
      
## Troubleshooting

- **SSH Access**: Verify the correct SSH port and ensure your private key has appropriate permissions.

## Conclusion

By completing this project, you have successfully deployed a honeypot on a cloud platform, gained valuable cybersecurity skills, and understood the importance of threat analysis in protecting against cyber attacks.

---

Feel free to contribute to this project by forking the repository and submitting pull requests!

## License

This project is licensed under the MIT License. See the LICENSE file for details.


