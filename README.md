Toss in F11 - Inventory Management System
Overview
Toss in F11 is a web-based inventory management application designed for pizza restaurants. The system provides real-time stock tracking, automated alerts for low inventory levels, and intelligent reporting capabilities. Built with modern web technologies, the application enables efficient inventory control while reducing manual tracking errors and administrative overhead.

If you have qurey about it ASKED to: zread
System Architecture
┌─────────────────────────────────────────────────────────────┐
│                         User Browser                         │
│  ┌────────────┐  ┌─────────────┐  ┌──────────────────────┐ │
│  │  Dashboard │  │   Search &  │  │   AI Command         │ │
│  │   Metrics  │  │   Filters   │  │   Interface          │ │
│  └────────────┘  └─────────────┘  └──────────────────────┘ │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │           Inventory List Component                    │   │
│  │  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐  │   │
│  │  │Item 1│  │Item 2│  │Item 3│  │Item 4│  │Item 5│  │   │
│  │  └──────┘  └──────┘  └──────┘  └──────┘  └──────┘  │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌────────────────────┐  ┌──────────────────────────────┐   │
│  │  Export Controls   │  │  Notification System         │   │
│  │  Excel  │  PDF     │  │  Browser Alerts              │   │
│  └────────────────────┘  └──────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
         │                           │
         ▼                           ▼
   React.js State              Local Storage
   (In-Memory)                 (Future)
Application Workflow
User Action
    │
    ▼
┌─────────────────────┐
│  Event Handler      │
│  (onClick, etc.)    │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  State Update       │
│  (useState/useEffect)│
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  React Re-render    │
│  (Component Update) │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  UI Reflects Change │
│  (Visual Update)    │
└─────────────────────┘
Key Features
🎯 Inventory Management
Track stock levels, costs, and values in real time. Each item maintains current quantity, unit of measurement, cost per unit, and customizable low-stock thresholds.

🔔 Intelligent Alerts
The system monitors inventory continuously and triggers visual alerts when items fall below designated thresholds. Browser notifications provide additional awareness.

🤖 Natural Language Interface
Process inventory updates using conversational commands such as "bought 5 kg of onions" or "used 2 liters of sauce."

🔍 Search and Filter
Real-time search filters inventory as you type. Multiple filter options display low-stock items, adequately stocked items, or high-value inventory.

📊 Professional Reporting
Export comprehensive reports to Excel with automatic summary calculations or generate print-ready PDF reports.

Technology Stack
Component	Technology	Purpose
Frontend Framework	React.js 18	Component-based UI architecture
Styling	Tailwind CSS	Responsive design and visual styling
Icons	Lucide React	Consistent icon library
Data Export	SheetJS (XLSX)	Excel spreadsheet generation
Build Tools	Create React App	Development environment and optimization
Version Control	Git	Code tracking and collaboration
Hosting	Vercel	Cloud deployment and CDN delivery
Deployment Architecture
Developer Workstation                 Cloud Infrastructure
┌──────────────────┐                 ┌──────────────────┐
│                  │                 │                  │
│  Local Dev       │    Git Push     │    GitHub        │
│  Environment     │────────────────▶│    Repository    │
│  (localhost)     │                 │                  │
│                  │                 └────────┬─────────┘
└──────────────────┘                          │
                                              │ Auto Deploy
                                              │
                                              ▼
                                   ┌──────────────────┐
                                   │                  │
                                   │     Vercel       │
                                   │   Build & Deploy │
                                   │                  │
                                   └────────┬─────────┘
                                            │
                                            │ Distribute
                                            │
                                            ▼
                                   ┌──────────────────┐
                                   │                  │
                                   │   Global CDN     │
                                   │   (Worldwide)    │
                                   │                  │
                                   └────────┬─────────┘
                                            │
                                            ▼
                                      End Users
Prerequisites
Node.js 14.0.0 or higher
NPM 6.0.0 or higher
Git 2.0.0 or higher
Modern web browser (Chrome, Firefox, Safari, Edge)
Installation
Local Development Setup
Clone the repository and install dependencies:

git clone https://github.com/yourusername/pizza-inventory.git
cd pizza-inventory
npm install
npm start
The application launches at http://localhost:3000 with hot reloading enabled.

Production Build
Create an optimized production build:

npm run build
The build files will be generated in the build directory.

Component Hierarchy
App (Main Container)
│
├── Dashboard
│   ├── Total Items Card
│   ├── Low Stock Alerts Card
│   └── Inventory Value Card
│
├── LowStockAlertPanel
│   └── Alert Items List
│
├── ExportButtons
│   ├── Excel Export
│   └── PDF Export
│
├── SearchAndFilter
│   ├── Search Input
│   ├── Filter Dropdown
│   └── Sort Dropdown
│
├── AIAgentInput
│   ├── Command Input
│   └── Feedback Display
│
├── InventoryList
│   └── InventoryItem (repeated)
│       ├── Item Details
│       ├── Stock Controls
│       └── Edit/Delete Actions
│
└── ItemForm (Modal)
    ├── Form Fields
    └── Save/Cancel Actions
Data Flow Diagram
┌─────────────────────────────────────────────────────────┐
│                    Browser Storage                       │
│                    (Session Only)                        │
└──────────────────────┬──────────────────────────────────┘
                       │
                       │ Read/Write
                       │
┌──────────────────────▼──────────────────────────────────┐
│                  React State                             │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐        │
│  │ Inventory  │  │ Filters    │  │ Alerts     │        │
│  │ Array      │  │ Settings   │  │ Status     │        │
│  └────────────┘  └────────────┘  └────────────┘        │
└──────────────────────┬──────────────────────────────────┘
                       │
                       │ Triggers Re-render
                       │
┌──────────────────────▼──────────────────────────────────┐
│                Component Tree                            │
│  ┌──────────────────────────────────────────────────┐   │
│  │            Virtual DOM                            │   │
│  └────────────────────┬─────────────────────────────┘   │
│                       │                                  │
│                       │ Reconciliation                   │
│                       │                                  │
│  ┌────────────────────▼─────────────────────────────┐   │
│  │            Real DOM                               │   │
│  │  (Visible User Interface)                         │   │
│  └───────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
Usage Guide
Managing Inventory Items
Adding Items: Click "Add New Item" button, fill in the form with item name, stock quantity, unit, threshold, and cost per unit.

Editing Items: Click the "Edit" button on any item to modify its details.

Adjusting Stock: Use the plus (+) and minus (-) buttons for quick stock adjustments.

Deleting Items: Click the "Delete" button and confirm the action.

Using AI Commands
Type natural language commands in the AI Agent Command Center:

"bought 10 kg of cheese"
"used 3 liters of sauce"
"received 20 units of dough"
Search and Filter
Search: Type in the search bar to filter items by name.

Filter Options:

All Items
Low Stock Only
In Stock
High Value (Rs. 50+, Rs. 100+, Rs. 200+)
Sort Options:

Name (A-Z or Z-A)
Stock (Low to High or High to Low)
Value (Low to High or High to Low)
Exporting Data
Excel Export: Click "Export to Excel" to download a spreadsheet with all inventory data and summary statistics.

PDF Export: Click "Export to PDF" to open a print dialog with a formatted report.

Deployment to Vercel
Step 1: Push to GitHub
git add .
git commit -m "Initial commit"
git push origin main
Step 2: Connect to Vercel
Sign up at vercel.com
Click "Add New Project"
Import your GitHub repository
Click "Deploy"
Step 3: Continuous Deployment
Every push to the main branch automatically triggers a new deployment. Changes go live within 2-3 minutes.

Project Structure
pizza-inventory/
├── public/
│   ├── index.html           # Main HTML file with Tailwind CDN
│   ├── favicon.ico          # App icon
│   ├── logo192.png          # PWA icon (192x192)
│   ├── logo512.png          # PWA icon (512x512)
│   └── manifest.json        # PWA configuration
├── src/
│   ├── App.js              # Main application component
│   ├── index.js            # React entry point
│   └── index.css           # Global styles
├── node_modules/           # Dependencies (auto-generated)
├── package.json            # Project configuration
├── .gitignore             # Git ignore rules
└── README.md              # Documentation
Development Workflow
┌──────────────┐
│ 1. Code      │ → Write code in VS Code
└──────┬───────┘
       │
┌──────▼───────┐
│ 2. Test      │ → Run npm start, test at localhost:3000
└──────┬───────┘
       │
┌──────▼───────┐
│ 3. Commit    │ → git add . && git commit -m "message"
└──────┬───────┘
       │
┌──────▼───────┐
│ 4. Push      │ → git push origin main
└──────┬───────┘
       │
┌──────▼───────┐
│ 5. Deploy    │ → Vercel auto-deploys (2-3 minutes)
└──────┬───────┘
       │
┌──────▼───────┐
│ 6. Live      │ → Changes visible at your-app.vercel.app
└──────────────┘
Browser Compatibility
Browser	Minimum Version
Chrome	90+
Firefox	88+
Safari	14+
Edge	90+
Mobile browsers (Chrome for Android, Safari for iOS) are fully supported.

Configuration
Customizing Initial Data
Edit src/App.js and modify the INITIAL_INVENTORY constant:

const INITIAL_INVENTORY = [
  { id: '1', name: "Item Name", stock: 50, unit: "units", threshold: 10, cost: 0.80 },
  // Add more items...
];
Changing App Name and Icon
Update Title: Edit public/index.html line 27:

<title>Your App Name</title>
Update Icon: Replace files in public/ folder:

favicon.ico
logo192.png
logo512.png
Update Manifest: Edit public/manifest.json:

{
  "short_name": "Your App",
  "name": "Your App Full Name"
}
Troubleshooting
Application Won't Start
# Delete node_modules and reinstall
rm -rf node_modules
npm install
npm start
Styles Not Loading
Verify Tailwind CDN link exists in public/index.html:

<script src="https://cdn.tailwindcss.com"></script>
Notifications Not Working
Check browser notification permissions in settings and grant access.

Export Not Working
Disable popup blockers for localhost during development or your production domain.

Performance Notes
Handles up to 1000 inventory items efficiently
Search and filter execute instantly (client-side processing)
Export operations complete within seconds
Memory usage remains minimal during extended sessions
Security Considerations
The application runs entirely client-side with no backend server. All data exists only in browser memory and disappears on page reload.

For production deployment requiring data persistence, consider integrating:

Firebase Firestore for database
Firebase Authentication for user management
Proper API security with authentication tokens
Future Enhancements
Database Integration: Firebase or PostgreSQL for data persistence
User Authentication: Multi-user support with role-based access
Purchase Orders: Automated reorder suggestions based on low stock
Analytics Dashboard: Consumption trends and predictive inventory
Mobile App: React Native version with offline support
Barcode Scanning: Camera-based inventory updates
Multi-location Support: Manage inventory across multiple sites
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request
License
This project is open source and available for educational and commercial use. Modify and distribute freely while retaining attribution to the original authors.

Support
For questions or issues, please open an issue on the GitHub repository.

Version: 1.0.0
Last Updated: January 2026
Repository: Pizza Inventory Live Demo: Vercel.app

Quick Reference Commands
# Install dependencies
npm install

# Start development server
npm start

# Create production build
npm run build

# Deploy to GitHub
git add .
git commit -m "Your message"
git push origin main

# Clear cache and restart
rm -rf node_modules/.cache
npm start
Made with ❤️ for pizza restaurant managers worldwide 🍕

