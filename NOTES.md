# MCP Notes

## Overview
This document serves as a living record of notes, observations, and documentation. It will be updated regularly to maintain a comprehensive collection of information.

## Table of Contents
1. [General Notes](#general-notes)
2. [Important References](#important-references)
3. [Updates Log](#updates-log)
4. [Invoice Generator Structure](#invoice-generator-structure)

## General Notes
- Created repository on: April 1, 2025

## Important References
### Invoice Generation Resources
1. [Nayan-Shrivastava/invoice-generator](https://github.com/Nayan-Shrivastava/invoice-generator)
   - Node.js/Express based solution
   - Features:
     - PDF generation using html-pdf
     - Email sending via SendGrid
     - User authentication
     - MongoDB database
     - EJS templating

## Invoice Generator Structure
### Project Architecture
```
invoice-generator/
├── src/                      # Source code directory
│   ├── index.js             # Application entry point
│   ├── app.js               # Express app configuration
│   ├── models/              # Database models
│   │   ├── user.js         # User model (authentication)
│   │   └── invoice.js      # Invoice model
│   ├── middleware/          # Custom middleware
│   │   ├── auth.js         # Authentication middleware
│   │   └── roles.js        # Role-based access control
│   ├── routes/             # API routes
│   │   ├── user.js         # User management routes
│   │   └── invoice.js      # Invoice operations routes
│   ├── templates/          # PDF and email templates
│   │   ├── invoice.ejs     # Invoice PDF template
│   │   └── email.ejs       # Email body template
│   └── utils/              # Utility functions
│       ├── pdf.js          # PDF generation logic
│       └── email.js        # Email sending logic
├── config/                  # Configuration files
│   └── dev.env             # Environment variables
└── package.json            # Project dependencies
```

### Key Components Breakdown

1. **Database Models**
   - User Model:
     - Authentication details
     - Role information
     - Personal/business info
   - Invoice Model:
     - Invoice number
     - Customer details
     - Items and pricing
     - Payment status
     - Generated PDF link

2. **API Routes**
   - User Routes:
     - Registration
     - Login
     - Profile management
   - Invoice Routes:
     - Create invoice
     - Generate PDF
     - Send via email
     - List/Search invoices

3. **Templates**
   - Invoice Template (EJS):
     - Professional layout
     - Dynamic content areas
     - Styling for PDF output
   - Email Template:
     - Professional format
     - Invoice attachment
     - Custom message

4. **Utilities**
   - PDF Generation:
     - html-pdf configuration
     - Template rendering
     - File management
   - Email Service:
     - SendGrid integration
     - Template processing
     - Attachment handling

### Technology Stack
- **Backend**: Node.js + Express
- **Database**: MongoDB with Mongoose
- **Authentication**: JWT (jsonwebtoken)
- **PDF Generation**: html-pdf
- **Email Service**: SendGrid
- **Template Engine**: EJS
- **Logging**: Winston

### Key Dependencies
```json
{
  "@sendgrid/mail": "^7.4.5",
  "bcryptjs": "^2.4.3",
  "ejs": "^3.1.6",
  "express": "^4.17.1",
  "html-pdf": "^3.0.1",
  "jsonwebtoken": "^8.5.1",
  "mongoose": "^5.13.5"
}
```

## Updates Log
### April 1, 2025
- Initial repository creation
- Set up basic documentation structure
- Added invoice generator research and references
- Added detailed structure breakdown of invoice generator