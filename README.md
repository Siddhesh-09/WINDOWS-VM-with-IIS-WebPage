# IIS Web Server Deployment

This repository contains a responsive web application designed for deployment on a Windows VM with Internet Information Services (IIS).

## Overview

The included `index.html` file is a static webpage that demonstrates a successful IIS deployment on a Windows virtual machine. It features a modern design using Tailwind CSS and showcases cloud deployment capabilities.

## Prerequisites

Before deploying this application, ensure you have:

- A Windows virtual machine (VM) instance
- Internet Information Services (IIS) installed and configured
- Administrative access to the VM

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Siddhesh-09/WINDOWS-VM-with-IIS-WebPage.git
cd WINDOWS-VM-with-IIS-WebPage
```

### 2. IIS Configuration

1. **Install IIS** (if not already installed):
   - Open **Server Manager**
   - Click **Add roles and features**
   - Select **Web Server (IIS)** role
   - Complete the installation

2. **Deploy to IIS** (Choose one of the following methods):

    **Method A: Use Default Website (Simplest)**
   - Navigate to `C:\inetpub\wwwroot`
   - Delete the already existing html and png image file
   - Copy the `index.html` file directly into this folder
   - The default IIS website will automatically serve files from this location

   **Method B: Create a New Website**
   - Open **IIS Manager**
   - Right-click **Sites** > **Add Website**
   - Set the following:
     - Site name: Your choice (e.g., "MyWebApp")
     - Physical path: Path to the directory containing `index.html`
     - Port: 80 (or your preferred port)
   - Click **OK**



### 3. Deploy the Application

1. Copy the `index.html` file to your IIS website's physical directory
2. Ensure the IIS_IUSRS group has read permissions on the file
3. Start the website in IIS Manager if it's not already running

## Accessing the Application

Once deployed, access your application by navigating to:
- **Local access**: `http://localhost` (or `http://localhost:<port>` if using a custom port)
- **Remote access**: `http://<your-vm-public-ip>` (ensure port 80 is open in your VM's firewall/network security group)

## Features

- **Responsive Design**: Optimized for desktop and mobile devices
- **Modern UI**: Built with Tailwind CSS for clean, professional appearance
- **Static Hosting**: No server-side processing required
- **Production Ready**: Includes status indicators and deployment information

## Customization

To customize the webpage:

1. Edit the `index.html` file
2. Modify the content, styling, or add additional features as needed
3. Test locally before redeploying to IIS

## Troubleshooting

- **403 Forbidden**: Check file permissions and ensure IIS_IUSRS has access
- **404 Not Found**: Verify the physical path in IIS is correct
- **Port issues**: Ensure port 80 is open in Windows Firewall and VM network security
- **Styling issues**: Check internet connectivity for CDN resources (Tailwind CSS, Google Fonts)

## Security Considerations

- Keep IIS updated with latest security patches
- Configure appropriate firewall rules
- Use HTTPS in production environments
- Regularly monitor IIS logs for suspicious activity

## Support

For issues or questions regarding this deployment, please check:
- IIS documentation: https://docs.microsoft.com/en-us/iis/
- Windows Server documentation
- Repository issues section

---

*This application demonstrates cloud deployment capabilities on Windows IIS infrastructure.*