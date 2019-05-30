![](./media/image1.png)

# Lab: Example Markdown Conversion

Lab Guide Mark Down Conversion Template Information:

# Contents

[Lab: Example Markdown Conversion 1](#lab-example-markdown-conversion)

[Overview 1](#overview)

[Module 1 2](#module-1)

[Module 2 3](#module-2)

[Module 3 6](#module-3)

[Conclusion 7](#conclusion)

## 

## Overview

This lab will introduce you to the product. Lorem ipsum dolor sit amet,
consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore
et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum
dolore eu fugiat nulla pariatur.

1.  Objective one

2.  Objective two

3.  Objective three

4.  Objective four

5.  Conclusion

**Requirements**

  - Add the requirements for your lab

  - Terminal application (Windows or Linux)

**Purpose and Rules**

A brief overview of what you expect the student to accomplish in your
lab. The purpose of this workshop is to familiarize attendees with the
feature functionality of the technology being presented. It is assumed
that attendees have a solid understanding of basic related concepts.

# Module 1

1.  Login to the Oracle Cloud. Your username and tenancy have been
    created in advance. Your login information will be sent via email.
    Look for an email from Oracle Cloud.

![](./media/image2.png)

*Figure 1: Sample email*

2.  Click the link in the email to access your services directly. Use
    the **userid** and **temporary** **password** from the email to
    login. You will be asked to change your password. Be prepared with a
    strong password that meets the security criteria.

![](./media/image3.png)

*Figure 2: Cloud Account login screen*

![](./media/image4.png)

*Figure 3: Password reset screen*

**Password Criteria:**

  - Password must have at least 12 characters

  - Password cannot exceed 40 characters

  - Password cannot contain the First or Last Name of the user

  - Password cannot contain the user name

  - Password must have at least 1 lower case character

  - Password must have at least 1 upper case character

  - Password must have at least 1 numeric character

  - Cannot repeat the last 4 passwords

**Note:** *If you haven’t received an introduction email you can login
directly. Open a browser and navigate to:
<https://cloud.oracle.com/en_US/sign-in>. Use the **Can’t Sign In** link
to reset your password, a password reset link will be sent to your
email.*

# Module 2

Compartments are used to isolate resources within your OCI tenant.
Creating resources in the root compartment is not a best practice.
During the lab exercises, we suggest that you create a compartment for
your team. You can create all required resources and apply user based
access policies within a compartment.

1.  Click the **hamburger icon** in the upper left corner to open the
    navigation menu. Under the **Identity** section of the menu, click
    **Compartments**

![](./media/image5.png)

*Figure 4: OCI Console Compartments menu*

2.  Click **Create Compartment**

![](./media/image6.png)

*Figure 5: Create compartment button*

3.  Choose a descriptive name and enter it in the name field. Enter a
    **Description** and click **Create Compartment**.

![](./media/image7.png)

*Figure 6: Create compartment dialog*

4.  The compartment name will show up in the list.

![](./media/image8.png)

*Figure 7: Compartment List*

**Note:** *If you want to view the compartment details, change the
compartment name, or delete the compartment, click the ellipses and
choose an option.*

![C:\\Users\\dkingsle\\AppData\\Local\\Temp\\SNAGHTML121a7a9.PNG](./media/image9.png)

*Figure 7: Compartment options*

# Module 3

A VCN is the basis for an OCI cloud environment. It provides your
customer with complete control over their network environment. The
network is the key to functionality and security within your cloud
solution. This includes assigning their own private IP address space,
creating subnets, creating route tables, and configuring stateful
firewalls. A single tenancy can have multiple VCNs, thereby providing
grouping and isolation of related resources. Your customer might use
multiple VCNs to separate the resources in different departments in your
company.

VCNs are located within specific regions and are normally defined within
Availability Domains (AD). ADs are isolated for high availability.

1.  Click the hamburger icon in the upper left corner and navigate to
    Networking \> Virtual Cloud Networks.

![](./media/image10.png)

*Figure 8: Menu Option*

2.  Make sure your compartment is selected from the list and click
    ‘Create Virtual Cloud Network’

![](./media/image11.png)

*Figure 9: Create Virtual Cloud Network*

  - Make sure your Compartment name is selected.

  - Name your VCN

  - Choose “Create virtual cloud network plus related resources’

  - Click Create Virtual Cloud Network

<!-- end list -->

3.  Checking the ‘Create virtual cloud network plus related resources’
    option automatically creates everything you need for a standard
    virtual cloud network based on a standard non-routable CIDR network
    numbering scheme. This includes …

<!-- end list -->

  - 3 subnets

  - 1 route table

  - 1 internet gateway

  - 1 security list

  - 1 DHCP option

# Conclusion

This lab introduced you to the Oracle Cloud Infrastructure service.
Let’s review what you did.

You created a virtual cloud network, a compute instance, and block
storage. You installed and configured Docker containers on the compute
instance you created. This lab was designed to introduce you to many of
the services you will use in the design of a customer solution and to
familiarize you with those services.

What you completed

  - Accessed your Oracle Cloud Account

  - Created a Compartment and a VCN

  - Created a compute instance
