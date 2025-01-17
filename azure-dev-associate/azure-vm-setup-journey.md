# Launching and Connecting to an Azure Virtual Machine (VM)

Today, I successfully launched a Virtual Machine (VM) on Azure. While the process is straightforward, I encountered a few challenges that taught me valuable lessons. Here's a step-by-step breakdown of what I did, where I made mistakes, and how I fixed them. This guide should save you time if you're setting up an Azure VM.
## Steps to Launch and Connect to an Azure VM

**Creating the Virtual Machine**
        Go to the **Azure Portal**.
        Navigate to **Virtual Machines** and click **Create**.
        Fill in all the necessary details like the VM name, region, image (e.g., Ubuntu), and size.
        After completing the setup, click **Review + Create**, then Create.

**Connecting to the Virtual Machine**
        Once the VM is created, there are multiple ways to connect to it.
        I chose **Azure Bastion**, as it doesn’t require additional software like *SSH clients*.
        **Bastion** is quick and convenient—just click on it in the Azure portal, and you can access your VM directly through your browser.

**Setting Up Apache to Test Connectivity**
        To check if everything was working, I decided to install Apache and host a test webpage.
        After installing Apache **(sudo apt install apache2)**, I tried accessing the **VM's public IP address** in my browser, but I got an error.

## Where I Went Wrong and How I Fixed It

Forgetting to Allow **HTTP** (Port 80)
        The problem was that Port 80 (HTTP) was not enabled in the VM's **network security group** (NSG).
        Fix:
            Go to your VM in the Azure portal.
            Navigate to Networking > **Inbound Port Rules**.
            Add a rule to allow Port 80 (HTTP) traffic.
        After adding this rule, the webpage became accessible.

 Ensuring **Apache** Is **Running**
        If the webpage still shows an error after allowing *Port* 80, make sure Apache is running.
        Use this command to check the status of Apache:

              sudo systemctl status apache2

If Apache is not running, start it using:

              sudo systemctl start apache2

Key Takeaways

    1. Port 80 is essential for HTTP traffic. Always ensure it is allowed in the VM's network security group.
    2. Check if Apache is running. Use the sudo systemctl status apache2 command to verify its status.
    3. Azure Bastion is a convenient way to connect to your VM. You don’t need any additional software, making it beginner-friendly.

I hope this helps anyone starting with Azure Virtual Machines. Remember to double-check your network settings and service statuses to avoid common errors. Happy learning! 😊