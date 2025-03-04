# SF-Account-Contacts-LWC

This repository contains the implementation of a Salesforce Developer case study. It includes:

- A Lightning Web Component (LWC) is used to display accounts and their related contacts.
- Business logic to enforce opportunity creation restrictions.
- Security configurations to control access to customer data.

## Table of Contents

- [Project Overview](#project-overview)
- [Requirements](#requirements)
  - [Requirement 1: Account-Contacts LWC](#requirement-1-account-contacts-lwc)
  - [Requirement 2: Opportunity Creation Restrictions](#requirement-2-opportunity-creation-restrictions)
  - [Requirement 3: Repository Structure](#requirement-3-repository-structure)
  - [Requirement 4: Security and Access Control](#requirement-4-security-and-access-control)
- [Setup Instructions](#setup-instructions)
- [Assumptions](#assumptions)

## Project Overview

This project addresses the following key functionalities:

1. **Account-Contacts LWC**: An LWC that displays account records in a picklist. Selecting an account renders its related contacts in a table. Each contact has an "Edit" button that opens a modal for editing without leaving the page.

2. **Opportunity Creation Restrictions**: Business logic ensures that sales team members can create only one opportunity per week. If a user attempts to create more than one opportunity in a week, the prior open opportunity must be closed as Won or Lost. If an open opportunity exists, an error message prompts the user to close the existing opportunity, providing a link to it.

3. **Security and Access Control**: Configurations ensure that only relationship managers can view financial details (transactions) and customer service agents can only access customer records assigned to them.

## Requirements

### Requirement 1: Account-Contacts LWC

- **Component**: `accountContactsLWC`
- **Functionality**:
  - Displays account records in a picklist.
  - Upon selection, the related contacts are rendered in a table.
  - Each contact row includes an "Edit" button that opens a modal for editing without page navigation.

### Requirement 2: Opportunity Creation Restrictions

- **Logic**:
  - Enforces a rule where sales team members can create only one opportunity per week.
  - If a user tries to create an additional opportunity within the same week, the system checks for existing open opportunities.
  - If an open opportunity exists, the user is prompted to close it (Won or Lost) before creating a new one, with an error message providing a link to the existing opportunity.

### Requirement 3: Repository Structure

- **Branching Strategy**:
  - Implementations are organized into branches corresponding to each requirement.
  - Merges are performed into the `main` branch after validation.

### Requirement 4: Security and Access Control

- **Objectives**:
  - Ensure only relationship managers can view financial details (transactions).
  - Ensure agents only see customer records (transactions) assigned to them.

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/SurbhiB62/SF-Account-Contacts-LWC.git
   ```
2. **Navigate to the Project Directory**:
   ```bash
   cd SF-Account-Contacts-LWC
   ```
3. **Authorize Org and Set Default**:
   ```bash
   sfdx auth:web:login
   sfdx config:set defaultusername=YOUR_ORG_ALIAS
   ```
4. **Deploy Components**:
   ```bash
   sfdx force:source:deploy -p force-app/main/default
   ```
5. **Assign Permissions**:
   - Assign the necessary permission sets to users to enforce security controls.

## Assumptions

- Users have the necessary permissions to deploy and test the solutions.
- The data model for `Account`, `Contact`, and `Opportunity` follows standard Salesforce structures.
- Security roles (Relationship Manager, Customer Service Agent) are predefined in the system.
