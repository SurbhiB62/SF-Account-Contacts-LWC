# SF-Account-Contacts-LWC

This repository contains the implementation of a Salesforce Developer case study. It includes a Lightning Web Component (LWC) for displaying accounts and related contacts, opportunity creation restrictions, and security access controls for customer data.

## Table of Contents
- [Project Overview](#project-overview)
- [Requirements](#requirements)
  - [Requirement 1: Account-Contacts LWC](#requirement-1-account-contacts-lwc)
  - [Requirement 2: Opportunity Restrictions](#requirement-2-opportunity-restrictions)
  - [Requirement 3: Repository Structure](#requirement-3-repository-structure)
  - [Requirement 4: Security and Access Control](#requirement-4-security-and-access-control)
- [Setup Instructions](#setup-instructions)
- [Assumptions](#assumptions)
- [License](#license)

## Project Overview
This project implements the required solutions in a Salesforce Developer Org. The key functionalities include:
- A Lightning Web Component to display accounts in a picklist and render related contacts.
- An opportunity creation restriction to ensure sales team members create only one opportunity per week.
- Security measures to prevent unauthorized access to customer financial data.

## Requirements

### Requirement 1: Account-Contacts LWC
- A Lightning Web Component (LWC) displays account records in a picklist.
- Selecting an account shows its related contacts in a table below.
- Each contact has an "Edit" button to open an edit modal without leaving the page.

### Requirement 2: Opportunity Restrictions
- Sales team members can create only one opportunity per week.
- If a user tries to create more than one opportunity, the prior open opportunity must be closed as Won or Lost.
- If an open opportunity exists, an error is displayed with a link to the existing opportunity.

### Requirement 3: Repository Structure
- The implemented solutions are committed to this GitHub repository.
- Each feature is developed in a separate branch and merged into `main`.

### Requirement 4: Security and Access Control
- Only Relationship Managers can view financial details (transactions).
- Customer service agents can only access customer records assigned to them.

## Setup Instructions
1. Create a new Salesforce Developer Org.
2. Clone this repository:
   ```sh
   git clone https://github.com/SurbhiB62/SF-Account-Contacts-LWC.git
   ```
3. Deploy the LWC components and Apex classes to your Salesforce Org using Salesforce CLI or Workbench.
4. Assign necessary permissions for security restrictions.

## Assumptions
- Users have necessary permissions to deploy and test the solutions.
- The data model for `Account`, `Contact`, and `Opportunity` follows standard Salesforce structure.
- Security roles (Relationship Manager, Customer Service Agent) are predefined in the system.

## License
This project is for educational and demonstration purposes.
