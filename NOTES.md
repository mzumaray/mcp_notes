# MCP Notes

## Overview
This document serves as a living record of notes, observations, and documentation. It will be updated regularly to maintain a comprehensive collection of information.

## Table of Contents
1. [General Notes](#general-notes)
2. [Project Structure](#project-structure)
3. [Technology Stack](#technology-stack)
4. [Updates Log](#updates-log)

## General Notes
- Created repository on: April 1, 2025
- Using Lynx framework for cross-platform UI development
- SQLite for local database storage

## Project Structure
```
invoice-app/
├── src/
│   ├── components/           # Lynx UI components
│   │   ├── Invoice/         # Invoice related components
│   │   ├── Customer/        # Customer management components
│   │   └── common/         # Shared UI components
│   ├── database/
│   │   ├── schema.sql      # SQLite database schema
│   │   └── db.js           # Database operations
│   ├── services/
│   │   ├── pdf.js          # PDF generation service
│   │   └── email.js        # Email service
│   ├── styles/             # Lynx styles and themes
│   └── utils/              # Utility functions
├── public/                 # Static assets
├── database.sqlite         # SQLite database file
└── package.json           # Project dependencies
```

## Technology Stack
1. **Frontend Framework**
   - Lynx (v3.2.0-rc.1)
   - Features:
     - Native rendering on Android, iOS, and Web
     - Web-inspired design (CSS and React-like)
     - High performance multithreaded engine

2. **Database**
   - SQLite
   - Local storage
   - Schema design for:
     - Customers
     - Invoices
     - Products/Services
     - Settings

3. **Additional Technologies**
   - PDF Generation Library (to be determined)
   - Email Service Integration
   - SQLite3 Node.js bindings

## Database Schema
```sql
-- Customers table
CREATE TABLE customers (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    email TEXT NOT NULL,
    address TEXT,
    phone TEXT,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Invoices table
CREATE TABLE invoices (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    customer_id INTEGER,
    invoice_number TEXT NOT NULL,
    issue_date DATE NOT NULL,
    due_date DATE NOT NULL,
    status TEXT DEFAULT 'pending',
    total_amount DECIMAL(10,2),
    pdf_path TEXT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);

-- Invoice items table
CREATE TABLE invoice_items (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    invoice_id INTEGER,
    description TEXT NOT NULL,
    quantity INTEGER NOT NULL,
    unit_price DECIMAL(10,2) NOT NULL,
    FOREIGN KEY (invoice_id) REFERENCES invoices(id)
);
```

## Updates Log
### April 1, 2025
- Initial repository creation
- Set up basic documentation structure
- Added invoice generator research and references
- Updated project structure for Lynx framework implementation
- Defined SQLite database schema