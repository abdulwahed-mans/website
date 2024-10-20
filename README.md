# Backend Django Project - Profile Management

## Overview

This is a **Profile Management** system built using Django, which includes features for managing user profiles with comprehensive fields such as LinkedIn profile, experience years, availability, certifications, and more. The system also integrates fields from the `Member` model, including functionality to calculate a user's age and format dates like the joined date and last login time.

## Features

- **Profile Management**: Store and manage detailed user profiles including personal, professional, and financial information.
- **Member Fields**: Handle user membership details with fields like personal number, last login, and joined date.
- **City and Country Selection**: Predefined choices for Swedish cities and countries.
- **Dynamic Age Calculation**: Automatically calculates a user's age based on their personal number.
- **Date Formatting**: Methods for formatting joined dates and login timestamps.
- **Profile Picture Support**: Users can upload profile pictures.
- **Language Preferences**: Profiles can be set to either Swedish or English.
- **Tax and Payment Information**: Support for storing sensitive financial information such as tax IDs and bank account details.
  
## Model Overview

The `Profile` model contains the following key fields:

### Personal Information
- **First Name**: `first_name` (CharField, max_length=100)
- **Last Name**: `last_name` (CharField, max_length=100)
- **Email**: `email` (EmailField)
- **Personal Number**: `personal_number` (CharField, unique, format: YYYYMMDD-XXXX)
- **Phone Number**: `phone_number` (CharField, max_length=20)
- **Address**: `address` (TextField, optional)
- **Location**: `location` (CharField, max_length=255)
- **City**: Predefined choices of major Swedish cities
- **Country**: Defaults to "Sweden"
- **Language**: Can be set to either `Swedish` or `English`
  
### Professional Information
- **LinkedIn Profile**: `linkedin_profile` (URLField, optional)
- **Experience Years**: `experience_years` (PositiveIntegerField)
- **Hourly Rate**: `hourly_rate` (DecimalField)
- **Projects Completed**: `projects_completed` (PositiveIntegerField)
- **Availability**: `availability` (Choices: Full-time, Part-time, Freelance)
- **Industry**: `industry` (CharField, max_length=100)
- **Certifications**: `certifications` (TextField, optional)
- **Skills**: `skills` (TextField, optional)
- **Education**: `education` (TextField, optional)
- **Portfolio URL**: `portfolio_url` (URLField, optional)
  
### Financial Information
- **Tax ID**: `tax_id` (CharField, max_length=50)
- **Bank Account**: `bank_account` (CharField, max_length=100)
- **Payment Methods**: `payment_methods` (CharField, max_length=255)

### System Fields
- **Joined Date**: Automatically populated upon profile creation
- **Last Login**: Automatically set to current time, but can be updated

## Methods and Calculations

### Age Calculation
The `age()` method calculates the user's age based on the personal number (format: YYYYMMDD-XXXX).

### Date Formatting
The `formatted_joined_date()` and `formatted_last_login()` methods provide easy-to-read date formatting for displaying dates in templates.

### URL Methods
- **get_absolute_url()**: Returns the URL for viewing the profile details.
- **get_update_url()**: Returns the URL for updating the profile.

## Installation

### Prerequisites
- Python 3.8+
- Django 4.2+
- A virtual environment setup is recommended.

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/abdulwahed-mans/website.git
