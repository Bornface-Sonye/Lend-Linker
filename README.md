# LendLinker

LendLinker is a web-based application designed to link women and youth groups and individuals in Awendo Constituency with financial resources. It enables seamless borrowing and lending among users while ensuring financial security and trustworthiness through integrated machine learning algorithms.

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Models](#models)
6. [Forms](#forms)
7. [Application Logic](#application-logic)
8. [License](#license)

## Introduction

LendLinker is built using the Django framework and provides a secure platform for financial transactions between borrowers and lenders. It includes interfaces for borrowers, lenders, group admins, and system admins, each with specific functionalities tailored to their roles.

## Features

- **User Authentication and Authorization**
  - User registration and login.
  - Role-based access control for borrowers, lenders, group admins, and system admins.

- **Borrower Functionality**
  - Borrower registration.
  - Loan application submission.
  - View loan status and repayment details.
  - Make loan repayments.

- **Lender Functionality**
  - Lender registration.
  - Allocate and disburse funds.
  - View and submit defaulters list.
  - Submit financial returns.

- **Group Admin Functionality**
  - Group registration.
  - Approve member loans.
  - Manage group funds and members.

- **System Admin Functionality**
  - Manage users and groups.
  - Monitor system activity and generate reports.

- **Machine Learning Integration**
  - Creditworthiness assessment.

## Installation

1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/lendlinker.git
    cd lendlinker
    ```

2. **Create and Activate a Virtual Environment**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4. **Apply Migrations**
    ```bash
    python manage.py migrate
    ```

5. **Create a Superuser**
    ```bash
    python manage.py createsuperuser
    ```

6. **Run the Development Server**
    ```bash
    python manage.py runserver
    ```

## Usage

1. **Access the Application**
    Open your web browser and go to `http://127.0.0.1:8000/`.

2. **Register and Login**
    Register as a new user and login to access the platform.

3. **Role-Based Access**
    Depending on your role (borrower, lender, group admin, or system admin), you will have access to different functionalities.

## Models

### User
- `username`
- `password`
- `email`
- `role`

### Borrower
- `user`
- `national_id`
- `full_name`
- `credit_score`
- `group`

### Lender
- `user`
- `lender_no`
- `funds_available`

### Group
- `group_name`
- `group_admin`
- `members`
- `funds`

### LoanApplication
- `borrower`
- `amount`
- `status`
- `security`

### LoanDisbursement
- `application`
- `lender`
- `amount`
- `disbursement_date`

### LoanRepayment
- `loan`
- `amount`
- `repayment_date`

### Default
- `borrower`
- `lender`
- `amount`
- `default_date`

## Forms

### User Registration Form
- `username`
- `password`
- `email`
- `role`

### User Login Form
- `username`
- `password`

### Borrower Registration Form
- `national_id`
- `full_name`
- `credit_score`
- `group`

### Lender Registration Form
- `lender_no`
- `funds_available`

### Group Registration Form
- `group_name`
- `group_admin`
- `members`
- `funds`

### Loan Application Form
- `amount`
- `security`

### Loan Disbursement Form
- `application`
- `amount`

### Loan Repayment Form
- `loan`
- `amount`

### Default Reporting Form
- `borrower`
- `lender`
- `amount`

### Admin Form
- Admin specific fields

## Application Logic

1. **User Authentication and Authorization**
    - Register and login users.
    - Implement role-based access control.

2. **Loan Application Process**
    - Borrowers apply for loans.
    - Loan applications are processed based on creditworthiness.

3. **Loan Disbursement Process**
    - Lenders allocate and disburse funds.
    - Ensure funds are available and disbursement is within the allocated amount.

4. **Loan Repayment Process**
    - Borrowers make repayments.
    - Update loan balance and repayment history.

5. **Default Reporting**
    - Lenders report defaulters.
    - Maintain default records.

6. **Admin Functions**
    - Manage users and groups.
    - Generate system reports.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
