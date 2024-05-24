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

3. **Install T-Pot**
   - Update the package list and install required dependencies:
     ```sh
     sudo apt update && sudo apt upgrade -y
     ```
     sudo apt update && sudo apt upgrade -y: <br/>
     <img src="https://imgur.com/yRtwONQ" height="80%" width="80%"/>
     <br />
   - Follow the [official T-Pot installation guide](https://github.com/telekom-security/tpotce) to install T-Pot.

4. **Configure Network Security Group**
   - Add inbound port rules for necessary ports (e.g., 64295 for SSH, 80 and 443 for web access) in the Azure Portal.

5. **Access T-Pot Web Interface**
   - After installation, reboot the VM and access the T-Pot web interface using the VM's public IP address and the appropriate port (default is `64297`).

6. **Analyze Threat Data**
   - Use the T-Pot dashboard to monitor and analyze incoming attack data.

## Troubleshooting

- **SSH Access**: Verify the correct SSH port and ensure your private key has appropriate permissions.

## Conclusion

By completing this project, you have successfully deployed a honeypot on a cloud platform, gained valuable cybersecurity skills, and understood the importance of threat analysis in protecting against cyber attacks.

---

Feel free to contribute to this project by forking the repository and submitting pull requests!

## License

This project is licensed under the MIT License. See the LICENSE file for details.


