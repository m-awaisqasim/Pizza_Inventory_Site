🍕 Toss in F11 - Pizza Inventory Manager

A sleek, real-time inventory management system built for small to medium-sized pizza restaurants, designed to keep track of essential ingredients and supplies. This application features an AI-assisted command interface and provides immediate low-stock alerts and advanced reporting capabilities.

✨ Key Features

This application is built as a single-page React component using modern functional practices and styled with a clean, responsive interface using Tailwind CSS.

🤖 AI Agent Command Center

Input commands in natural language to quickly update your inventory.

Add Stock: bought 5 kg of onions

Remove Stock: used 2 liters of sauce

📦 Real-Time Stock Management

Immediate Updates: Increase or decrease stock levels instantly using dedicated plus/minus buttons.

CRUD Operations: Easily add new items, edit existing details (name, unit, cost, threshold), and delete items.

🚨 Low Stock Alert System

Visual Warnings: Items below their set threshold are highlighted in red.

System Notifications: Sends native browser notifications (with user permission) when an item falls into low stock, ensuring you never miss a critical restock time.

🔍 Search, Filter, and Sort

Powerful tools to manage large inventories:

Search: Filter items by name.

Filter: View only Low Stock, In Stock, or High Value items.

Sort: Sort the list by Name (A-Z/Z-A), Stock Level, or Total Inventory Value.

📈 Dashboard and Reporting

Summary: View real-time metrics for total items, number of low stock items, and total inventory value (based on unit cost).

Export: Generate reports in two formats:

CSV (Comma Separated Values): Optimized for direct opening in Microsoft Excel or Google Sheets for advanced data analysis.

PDF: Generate a clean, printable report of the current inventory list.

🛠️ Usage Guide

1. Adding/Editing Items

Click the "Add New Item" button.

Fill in the details: Name, Current Stock, Unit (e.g., kg, liters, units), Low Stock Threshold, and the Cost per Unit (Rs.).

Click "Add Item" or "Save Changes".

2. Updating Stock

There are two ways to update stock:

Method

Description

Manual Adjustments

Use the + or - buttons next to each item to increment or decrement the stock by 1 unit.

AI Agent Command

Use the "AI Agent Command Center" input box for batch updates or specific amounts (e.g., received 10 kg of pizza dough).

3. Reporting

The export buttons provide immediate downloads:

Export to CSV: Downloads a file containing all columns (Item Name, Stock, Cost, Total Value, Status, etc.). This is the recommended format for data analysis.

Export to PDF: Opens a print-friendly window that formats the current inventory list as a static, readable report.

💻 Tech Stack

Frontend: React (Functional Components and Hooks)

Styling: Tailwind CSS (Utility-First Framework)

Icons: Lucide React

Data Handling: JavaScript (In-memory state management)

Note on Export: The application initially attempted to use the SheetJS library for complex Excel (XLSX) file generation. Due to security restrictions (Content Security Policy) in the hosting environment, this was replaced with a pure JavaScript CSV generator, which ensures reliable and instant downloads compatible with all spreadsheet software.
