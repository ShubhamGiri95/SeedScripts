# Azure SQL Seed Scripts for Master Data Initialization

This repository contains SQL seed scripts used for initializing *master data* in Azure-based environments. These scripts are used to automate user provisioning, officer assignments, user group mappings, and role configurations across both *Production* and *Non-Production* environments.

## Overview

These scripts support a streamlined and consistent setup of prerequisite data structures in Azure SQL databases for DevOps workflows. They are particularly useful for:

- Automated environment provisioning
- Setting up base users, officers, role mappings and geographical domain addresses
- Supporting testing, development, and production deployments

---

## Scripts

### 1. SeedScript_Prod_SingleUserMapping.sql
- Targets *Production* environments.
- Sets up multiple users derived from a master admin user.
- Updates Officer, UserGroupMappings, OfficerRoleMapping, and CrystalReportPermission.
- Handles role supervision and hierarchical relationships.

### 2. SeedScript_NonProd_ADO_SingleUserMapping.sql
- Targets *Non-Production* or *ADO* environments.
- Seeds sample users, user groups, and officer profiles.
- Maps users to groups and assigns roles.
- Inserts geographic domains and supervisory relationships.

---

## Features

- Resets and updates Officer and UserGroupMappings associations
- Dynamically builds supervisor-user chains
- Auto-generates user identifiers and officer codes
- Populates essential CrystalReportPermission entries
- Inserts GeographicDomain entries for use in location-based filtering

---

## Technologies Used

- Microsoft SQL Server / Azure SQL
- Azure DevOps Pipelines (intended integration)
- Infrastructure-as-Code (IaC) principles

---

## Usage

1. Open SQL Server Management Studio or Azure Data Studio.
2. Connect to your desired environment (NonProd or Prod).
3. Replace placeholder values like:
   - 'EnterAdminUser'
   - 'User', 'Description'
   - 'EnterPassword'
   - 'EnterReportCode', 'EnterPermissionId' and etc.
4. Execute the corresponding script file:
   - For production setup: SeedScript_Prod_SingleUserMapping.sql
   - For non-production setup: SeedScript_NonProd_ADO_SingleUserMapping.sql
