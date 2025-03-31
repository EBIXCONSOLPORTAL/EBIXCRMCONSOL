# EBIXCRMCONSOL
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Portal</title>
    <style>
        :root {
            --primary-color: #3498db;
            --dark-color: #2c3e50;
            --light-color: #ecf0f1;
            --danger-color: #e74c3c;
            --success-color: #2ecc71;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: white;
            color: #333;
            transition: all 0.3s ease;
        }

        body.dark-theme {
            background-color: #222;
            color: #f0f0f0;
        }

        .login-container {
            width: 400px;
            margin: 100px auto;
            background: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        }

        .login-container h2 {
            text-align: center;
            margin-bottom: 20px;
            color: var(--dark-color);
        }

        .login-form div {
            margin-bottom: 15px;
        }

        .login-form label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .login-form input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }

        .login-form button {
            width: 100%;
            padding: 12px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .login-form button:hover {
            background-color: var(--dark-color);
        }

        .footer {
            text-align: center;
            margin-top: 20px;
            font-size: 12px;
            color: #777;
        }

        /* Dashboard Styles */
        .dashboard {
            display: none;
            padding: 20px;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            background-color: var(--primary-color);
            color: white;
            margin-bottom: 20px;
        }

        .header.dark-theme {
            background-color: var(--dark-color);
        }

        .nav-menu {
            display: flex;
            background-color: #f8f9fa;
            padding: 10px;
            margin-bottom: 20px;
            border-radius: 5px;
        }

        .nav-menu.dark-theme {
            background-color: #444;
        }

        .nav-menu button {
            padding: 10px 15px;
            margin-right: 10px;
            border: none;
            background-color: transparent;
            cursor: pointer;
            border-radius: 4px;
            transition: all 0.3s;
        }

        .nav-menu button:hover, .nav-menu button.active {
            background-color: var(--primary-color);
            color: white;
        }

        .content-area {
            padding: 20px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }

        .content-area.dark-theme {
            background-color: #333;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }

        .form-group textarea {
            height: 100px;
            resize: vertical;
        }

        .form-row {
            display: flex;
            gap: 15px;
        }

        .form-row .form-group {
            flex: 1;
        }

        .btn {
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s;
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: white;
        }

        .btn-primary:hover {
            background-color: var(--dark-color);
        }

        .btn-danger {
            background-color: var(--danger-color);
            color: white;
        }

        .btn-success {
            background-color: var(--success-color);
            color: white;
        }

        .file-upload {
            margin: 15px 0;
        }

        .file-upload label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .live-clock {
            text-align: right;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .records-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        .records-table th, .records-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }

        .records-table th {
            background-color: #f8f9fa;
            font-weight: 600;
        }

        .records-table.dark-theme th {
            background-color: #444;
        }

        .records-table tr:hover {
            background-color: #f5f5f5;
        }

        .records-table.dark-theme tr:hover {
            background-color: #444;
        }

        .action-buttons button {
            padding: 5px 10px;
            margin-right: 5px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }

        .filter-section {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
        }

        .filter-section.dark-theme {
            background-color: #444;
        }

        .filter-row {
            display: flex;
            gap: 15px;
            margin-bottom: 10px;
        }

        .filter-group {
            flex: 1;
        }

        .filter-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
        }

        .filter-group select, .filter-group input {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        .settings-panel {
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 5px;
        }

        .settings-panel.dark-theme {
            background-color: #444;
        }

        .settings-option {
            margin-bottom: 20px;
        }

        .settings-option h3 {
            margin-bottom: 10px;
            border-bottom: 1px solid #ddd;
            padding-bottom: 5px;
        }

        .dashboard-footer {
            text-align: center;
            padding: 15px;
            font-size: 12px;
            color: #777;
            border-top: 1px solid #ddd;
            margin-top: 20px;
        }

        .dashboard-footer.dark-theme {
            border-top: 1px solid #555;
        }
    </style>
</head>
<body>
    <!-- Login Page -->
    <div id="login-page" class="login-container">
        <h2>Admin Login</h2>
        <form id="login-form" class="login-form">
            <div>
                <label for="username">User ID:</label>
                <input type="text" id="username" required>
            </div>
            <div>
                <label for="password">Password:</label>
                <input type="password" id="password" required>
            </div>
            <button type="submit">Login</button>
        </form>
        <div class="footer">
            <p>ALL RIGHTS RESERVED BY DEV MAKWANA AND EBIXCRMCONSOL PVL LTD SINGAPORE 2025</p>
        </div>
    </div>
    
    <!-- Dashboard (hidden until login) -->
    <div id="dashboard" class="dashboard">
        <div class="header" id="dashboard-header">
            <h2>Admin Portal</h2>
            <div class="live-clock" id="live-clock"></div>
        </div>
        
        <div class="nav-menu" id="nav-menu">
            <button class="active" data-section="job-requests">Job Requests</button>
            <button data-section="new-customer">New Customer</button>
            <button data-section="records-view">Records View</button>
            <button data-section="engineer-assignment">Engineer Assignment</button>
            <button data-section="settings">Settings</button>
            <button data-section="reports">Reports</button>
        </div>
        
        <!-- Job Requests Section -->
        <div id="job-requests" class="content-area section-content">
            <h3>Job Requests</h3>
            <div class="filter-section">
                <div class="filter-row">
                    <div class="filter-group">
                        <label for="status-filter">Status</label>
                        <select id="status-filter">
                            <option value="">All</option>
                            <option value="create">Create</option>
                            <option value="accept">Accept</option>
                            <option value="running">Running</option>
                            <option value="hold">Hold</option>
                            <option value="public-holiday">Public Holiday</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="warranty-filter">Warranty Status</label>
                        <select id="warranty-filter">
                            <option value="">All</option>
                            <option value="in-warranty">In Warranty</option>
                            <option value="out-warranty">Out of Warranty</option>
                            <option value="amc">AMC</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-primary" id="search-btn">Search</button>
                    </div>
                </div>
            </div>
            
            <table class="records-table">
                <thead>
                    <tr>
                        <th>Customer Name</th>
                        <th>Machine Name</th>
                        <th>Serial No.</th>
                        <th>Status</th>
                        <th>Warranty</th>
                        <th>Date</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody id="job-requests-table">
                    <!-- Dynamic content will be loaded here -->
                </tbody>
            </table>
        </div>
        
        <!-- New Customer Section -->
        <div id="new-customer" class="content-area section-content" style="display: none;">
            <h3>New Customer Information</h3>
            <form id="customer-form">
                <div class="form-row">
                    <div class="form-group">
                        <label for="customer-number">Customer Number</label>
                        <input type="text" id="customer-number" readonly>
                    </div>
                    <div class="form-group">
                        <label for="customer-name">Customer Name</label>
                        <input type="text" id="customer-name" required>
                    </div>
                    <div class="form-group">
                        <label for="customer-surname">Surname</label>
                        <input type="text" id="customer-surname" required>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="customer-email">Email ID</label>
                        <input type="email" id="customer-email" required>
                    </div>
                    <div class="form-group">
                        <label for="customer-phone">Contact Number</label>
                        <input type="tel" id="customer-phone" required>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="customer-address">Address</label>
                    <textarea id="customer-address" required></textarea>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="customer-pincode">Pin Code</label>
                        <input type="text" id="customer-pincode" required>
                    </div>
                    <div class="form-group">
                        <label for="customer-state">State</label>
                        <input type="text" id="customer-state" required>
                    </div>
                    <div class="form-group">
                        <label for="customer-country">Country</label>
                        <input type="text" id="customer-country" value="India" readonly>
                    </div>
                </div>
                
                <h4>Machine Information</h4>
                <div class="form-row">
                    <div class="form-group">
                        <label for="machine-name">Machine Name</label>
                        <input type="text" id="machine-name" required>
                    </div>
                    <div class="form-group">
                        <label for="machine-serial">Serial Number</label>
                        <input type="text" id="machine-serial" required>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="warranty-status">Warranty Status</label>
                    <select id="warranty-status" required>
                        <option value="">Select</option>
                        <option value="in-warranty">In Warranty</option>
                        <option value="out-warranty">Out of Warranty</option>
                        <option value="amc">AMC</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="record-status">Record Status</label>
                    <select id="record-status" required>
                        <option value="">Select</option>
                        <option value="create">Create</option>
                        <option value="accept">Accept</option>
                        <option value="running">Running</option>
                        <option value="hold">Hold</option>
                        <option value="public-holiday">Public Holiday</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="customer-remark">Customer Remarks</label>
                    <textarea id="customer-remark"></textarea>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="total-balance">Total Balance</label>
                        <input type="number" id="total-balance" step="0.01">
                    </div>
                    <div class="form-group">
                        <label for="payment-status">Payment Status</label>
                        <select id="payment-status">
                            <option value="pending">Pending</option>
                            <option value="partial">Partial</option>
                            <option value="completed">Completed</option>
                        </select>
                    </div>
                </div>
                
                <div class="file-upload">
                    <label for="image-upload">Upload Image</label>
                    <input type="file" id="image-upload" accept="image/*">
                </div>
                
                <div class="file-upload">
                    <label for="zip-upload">Upload ZIP File</label>
                    <input type="file" id="zip-upload" accept=".zip">
                </div>
                
                <div class="file-upload">
                    <label for="parts-upload">Upload Parts Code and Name (CSV)</label>
                    <input type="file" id="parts-upload" accept=".csv">
                </div>
                
                <div class="form-group">
                    <button type="submit" class="btn btn-primary">Save</button>
                    <button type="button" class="btn" id="print-pdf">Print PDF</button>
                </div>
            </form>
        </div>
        
        <!-- Records View Section -->
        <div id="records-view" class="content-area section-content" style="display: none;">
            <h3>All Records</h3>
            <div class="filter-section">
                <div class="filter-row">
                    <div class="filter-group">
                        <label for="view-status-filter">Status</label>
                        <select id="view-status-filter">
                            <option value="">All</option>
                            <option value="create">Create</option>
                            <option value="accept">Accept</option>
                            <option value="running">Running</option>
                            <option value="hold">Hold</option>
                            <option value="public-holiday">Public Holiday</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="date-from">From Date</label>
                        <input type="date" id="date-from">
                    </div>
                    <div class="filter-group">
                        <label for="date-to">To Date</label>
                        <input type="date" id="date-to">
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-primary" id="view-search-btn">Search</button>
                    </div>
                </div>
            </div>
            
            <table class="records-table">
                <thead>
                    <tr>
                        <th>Customer No.</th>
                        <th>Customer Name</th>
                        <th>Machine</th>
                        <th>Serial No.</th>
                        <th>Status</th>
                        <th>Warranty</th>
                        <th>Date</th>
                        <th>Assigned Engineer</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody id="all-records-table">
                    <!-- Dynamic content will be loaded here -->
                </tbody>
            </table>
        </div>
        
        <!-- Engineer Assignment Section -->
        <div id="engineer-assignment" class="content-area section-content" style="display: none;">
            <h3>Engineer Assignment</h3>
            <form id="assignment-form">
                <div class="form-row">
                    <div class="form-group">
                        <label for="record-select">Select Record</label>
                        <select id="record-select" required>
                            <option value="">Select Record</option>
                            <!-- Dynamic options will be loaded here -->
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="engineer-select">Assign Engineer</label>
                        <select id="engineer-select" required>
                            <option value="">Select Engineer</option>
                            <option value="EI102019004">Dev Makwana (EI102019004)</option>
                            <option value="EI112034005">Hanuman Bishnoi (EI112034005)</option>
                            <option value="EI4590778809">Mukesh Tanwar (EI4590778809)</option>
                            <option value="EI889906551">Dharmendra Singh (EI889906551)</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="assignment-remarks">Assignment Remarks</label>
                    <textarea id="assignment-remarks"></textarea>
                </div>
                
                <div class="form-group">
                    <button type="submit" class="btn btn-primary">Assign</button>
                </div>
            </form>
            
            <h4>Current Assignments</h4>
            <table class="records-table">
                <thead>
                    <tr>
                        <th>Record ID</th>
                        <th>Customer Name</th>
                        <th>Assigned Engineer</th>
                        <th>Assignment Date</th>
                        <th>Status</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody id="assignments-table">
                    <!-- Dynamic content will be loaded here -->
                </tbody>
            </table>
        </div>
        
        <!-- Settings Section -->
        <div id="settings" class="content-area section-content" style="display: none;">
            <h3>Settings</h3>
            <div class="settings-panel">
                <div class="settings-option">
                    <h3>Theme Settings</h3>
                    <div class="form-group">
                        <label for="theme-select">Select Theme</label>
                        <select id="theme-select">
                            <option value="light">Light Theme</option>
                            <option value="dark">Dark Theme</option>
                        </select>
                    </div>
                </div>
                
                <div class="settings-option">
                    <h3>Language Settings</h3>
                    <div class="form-group">
                        <label for="language-select">Select Language</label>
                        <select id="language-select">
                            <option value="english">English</option>
                            <option value="hindi">Hindi</option>
                            <!-- Add more languages as needed -->
                        </select>
                    </div>
                </div>
                
                <div class="settings-option">
                    <h3>Account Settings</h3>
                    <form id="account-form">
                        <div class="form-group">
                            <label for="current-username">Current Username</label>
                            <input type="text" id="current-username" value="eraj12" readonly>
                        </div>
                        <div class="form-group">
                            <label for="new-username">New Username</label>
                            <input type="text" id="new-username">
                        </div>
                        <div class="form-group">
                            <label for="current-password">Current Password</label>
                            <input type="password" id="current-password">
                        </div>
                        <div class="form-group">
                            <label for="new-password">New Password</label>
                            <input type="password" id="new-password">
                        </div>
                        <div class="form-group">
                            <label for="confirm-password">Confirm Password</label>
                            <input type="password" id="confirm-password">
                        </div>
                        <div class="form-group">
                            <button type="submit" class="btn btn-primary">Update Account</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
        
        <!-- Reports Section -->
        <div id="reports" class="content-area section-content" style="display: none;">
            <h3>Reports</h3>
            <div class="filter-section">
                <div class="filter-row">
                    <div class="filter-group">
                        <label for="report-type">Report Type</label>
                        <select id="report-type">
                            <option value="monthly">Monthly</option>
                            <option value="yearly">Yearly</option>
                            <option value="custom">Custom Date Range</option>
                        </select>
                    </div>
                    <div class="filter-group" id="month-select-group">
                        <label for="report-month">Month</label>
                        <select id="report-month">
                            <option value="1">January</option>
                            <option value="2">February</option>
                            <option value="3">March</option>
                            <option value="4">April</option>
                            <option value="5">May</option>
                            <option value="6">June</option>
                            <option value="7">July</option>
                            <option value="8">August</option>
                            <option value="9">September</option>
                            <option value="10">October</option>
                            <option value="11">November</option>
                            <option value="12">December</option>
                        </select>
                    </div>
                    <div class="filter-group" id="year-select-group">
                        <label for="report-year">Year</label>
                        <select id="report-year">
                            <!-- Dynamic years will be loaded here -->
                        </select>
                    </div>
                    <div class="filter-group" id="custom-date-group" style="display: none;">
                        <label for="custom-date-from">From Date</label>
                        <input type="date" id="custom-date-from">
                    </div>
                    <div class="filter-group" id="custom-date-to-group" style="display: none;">
                        <label for="custom-date-to">To Date</label>
                        <input type="date" id="custom-date-to">
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-primary" id="generate-report-btn">Generate Report</button>
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-success" id="print-report-btn">Print Report</button>
                    </div>
                </div>
            </div>
            
            <div id="report-results">
                <h4>Report Summary</h4>
                <div id="report-summary">
                    <!-- Report summary will be displayed here -->
                </div>
                
                <h4>Detailed Records</h4>
                <table class="records-table">
                    <thead>
                        <tr>
                            <th>Record ID</th>
                            <th>Customer Name</th>
                            <th>Machine</th>
                            <th>Status</th>
                            <th>Date</th>
                            <th>Engineer</th>
                        </tr>
                    </thead>
                    <tbody id="report-records-table">
                        <!-- Report records will be displayed here -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <div class="dashboard-footer" id="dashboard-footer">
            <p>ALL RIGHTS RESERVED BY DEV MAKWANA AND EBIXCRMCONSOL PVL LTD SINGAPORE 2025</p>
        </div>
    </div>

    <script>
        // Sample data for demonstration
        let records = [
            {
                id: 1,
                customerNumber: 'CUST001',
                customerName: 'John Doe',
                surname: 'Doe',
                email: 'john@example.com',
                phone: '9876543210',
                address: '123 Main St, Mumbai',
                pincode: '400001',
                state: 'Maharashtra',
                country: 'India',
                machineName: 'Printer XYZ',
                machineSerial: 'SN123456',
                warrantyStatus: 'in-warranty',
                recordStatus: 'create',
                date: '2023-05-15',
                assignedEngineer: '',
                remarks: '',
                balance: 0,
                paymentStatus: 'pending',
                images: [],
                files: []
            },
            {
                id: 2,
                customerNumber: 'CUST002',
                customerName: 'Jane Smith',
                surname: 'Smith',
                email: 'jane@example.com',
                phone: '9876543211',
                address: '456 Oak Ave, Delhi',
                pincode: '110001',
                state: 'Delhi',
                country: 'India',
                machineName: 'Scanner ABC',
                machineSerial: 'SN789012',
                warrantyStatus: 'out-warranty',
                recordStatus: 'accept',
                date: '2023-05-16',
                assignedEngineer: 'EI102019004',
                remarks: 'Urgent repair needed',
                balance: 2500,
                paymentStatus: 'partial',
                images: [],
                files: []
            }
        ];

        let assignments = [
            {
                recordId: 2,
                customerName: 'Jane Smith',
                engineerId: 'EI102019004',
                engineerName: 'Dev Makwana',
                assignmentDate: '2023-05-16',
                status: 'Assigned',
                remarks: 'Urgent repair needed'
            }
        ];

        // DOM Elements
        const loginPage = document.getElementById('login-page');
        const dashboard = document.getElementById('dashboard');
        const loginForm = document.getElementById('login-form');
        const usernameInput = document.getElementById('username');
        const passwordInput = document.getElementById('password');
        const navMenu = document.getElementById('nav-menu');
        const sectionContents = document.querySelectorAll('.section-content');
        const liveClock = document.getElementById('live-clock');
        const themeSelect = document.getElementById('theme-select');
        const body = document.body;
        const dashboardHeader = document.getElementById('dashboard-header');
        const dashboardFooter = document.getElementById('dashboard-footer');

        // Login functionality
        loginForm.addEventListener('submit', function(e) {
            e.preventDefault();
            const username = usernameInput.value;
            const password = passwordInput.value;
            
            if(username === 'eraj12' && password === '12345') {
                loginPage.style.display = 'none';
                dashboard.style.display = 'block';
                updateLiveClock();
                setInterval(updateLiveClock, 1000);
                loadJobRequests();
                generateCustomerNumber();
            } else {
                alert('Invalid credentials. Please try again.');
            }
        });

        // Navigation menu functionality
        navMenu.addEventListener('click', function(e) {
            if (e.target.tagName === 'BUTTON') {
                // Remove active class from all buttons
                const buttons = navMenu.querySelectorAll('button');
                buttons.forEach(btn => btn.classList.remove('active'));
                
                // Add active class to clicked button
                e.target.classList.add('active');
                
                // Hide all sections
                sectionContents.forEach(section => {
                    section.style.display = 'none';
                });
                
                // Show selected section
                const sectionId = e.target.getAttribute('data-section');
                document.getElementById(sectionId).style.display = 'block';
                
                // Load data for the section if needed
                if (sectionId === 'job-requests') {
                    loadJobRequests();
                } else if (sectionId === 'records-view') {
                    loadAllRecords();
                } else if (sectionId === 'engineer-assignment') {
                    loadAssignmentRecords();
                }
            }
        });

        // Update live clock
        function updateLiveClock() {
            const now = new Date();
            const options = { 
                timeZone: 'Asia/Kolkata',
                weekday: 'long',
                year: 'numeric',
                month: 'long',
                day: 'numeric',
                hour: '2-digit',
                minute: '2-digit',
                second: '2-digit',
                hour12: true
            };
            liveClock.textContent = now.toLocaleString('en-IN', options);
        }

        // Theme switcher
        themeSelect.addEventListener('change', function() {
            if (this.value === 'dark') {
                body.classList.add('dark-theme');
                dashboardHeader.classList.add('dark-theme');
                dashboardFooter.classList.add('dark-theme');
                document.querySelectorAll('.nav-menu').forEach(el => el.classList.add('dark-theme'));
                document.querySelectorAll('.content-area').forEach(el => el.classList.add('dark-theme'));
                document.querySelectorAll('.filter-section').forEach(el => el.classList.add('dark-theme'));
                document.querySelectorAll('.records-table').forEach(el => el.classList.add('dark-theme'));
                document.querySelectorAll('.settings-panel').forEach(el => el.classList.add('dark-theme'));
            } else {
                body.classList.remove('dark-theme');
                dashboardHeader.classList.remove('dark-theme');
                dashboardFooter.classList.remove('dark-theme');
                document.querySelectorAll('.nav-menu').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.content-area').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.filter-section').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.records-table').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.settings-panel').forEach(el => el.classList.remove('dark-theme'));
            }
        });

        // Generate customer number
        function generateCustomerNumber() {
            const customerNumber = document.getElementById('customer-number');
            const nextId = records.length > 0 ? 
                Math.max(...records.map(r => parseInt(r.customerNumber.replace('CUST', '')))) + 1 : 1;
            customerNumber.value = 'CUST' + nextId.toString().padStart(3, '0');
        }

        // Load job requests
        function loadJobRequests(filterStatus = '', filterWarranty = '') {
            const tableBody = document.getElementById('job-requests-table');
            tableBody.innerHTML = '';
            
            let filteredRecords = records;
            
            if (filterStatus) {
                filteredRecords = filteredRecords.filter(r => r.recordStatus === filterStatus);
            }
            
            if (filterWarranty) {
                filteredRecords = filteredRecords.filter(r => r.warrantyStatus === filterWarranty);
            }
            
            filteredRecords.forEach(record => {
                const row = document.createElement('tr');
                
                const statusClass = getStatusClass(record.recordStatus);
                const warrantyText = getWarrantyText(record.warrantyStatus);
                
                row.innerHTML = `
                    <td>${record.customerName} ${record.surname}</td>
                    <td>${record.machineName}</td>
                    <td>${record.machineSerial}</td>
                    <td><span class="${statusClass}">${record.recordStatus}</span></td>
                    <td>${warrantyText}</td>
                    <td>${record.date}</td>
                    <td class="action-buttons">
                        <button class="btn btn-primary edit-btn" data-id="${record.id}">Edit</button>
                        <button class="btn btn-danger delete-btn" data-id="${record.id}">Delete</button>
                    </td>
                `;
                
                tableBody.appendChild(row);
            });
            
            // Add event listeners to edit and delete buttons
            document.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    editRecord(recordId);
                });
            });
            
            document.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    if (confirm('Are you sure you want to delete this record?')) {
                        deleteRecord(recordId);
                    }
                });
            });
        }

        // Get status class for styling
        function getStatusClass(status) {
            switch(status) {
                case 'create': return 'status-create';
                case 'accept': return 'status-accept';
                case 'running': return 'status-running';
                case 'hold': return 'status-hold';
                case 'public-holiday': return 'status-holiday';
                default: return '';
            }
        }

        // Get warranty text
        function getWarrantyText(warrantyStatus) {
            switch(warrantyStatus) {
                case 'in-warranty': return 'In Warranty';
                case 'out-warranty': return 'Out of Warranty';
                case 'amc': return 'AMC';
                default: return '';
            }
        }

        // Edit record
        function editRecord(recordId) {
            const record = records.find(r => r.id === recordId);
            if (!record) return;
            
            // Switch to new customer section
            document.querySelector('[data-section="new-customer"]').click();
            
            // Fill the form with record data
            document.getElementById('customer-number').value = record.customerNumber;
            document.getElementById('customer-name').value = record.customerName;
            document.getElementById('customer-surname').value = record.surname;
            document.getElementById('customer-email').value = record.email;
            document.getElementById('customer-phone').value = record.phone;
            document.getElementById('customer-address').value = record.address;
            document.getElementById('customer-pincode').value = record.pincode;
            document.getElementById('customer-state').value = record.state;
            document.getElementById('machine-name').value = record.machineName;
            document.getElementById('machine-serial').value = record.machineSerial;
            document.getElementById('warranty-status').value = record.warrantyStatus;
            document.getElementById('record-status').value = record.recordStatus;
            document.getElementById('customer-remark').value = record.remarks;
            document.getElementById('total-balance').value = record.balance;
            document.getElementById('payment-status').value = record.paymentStatus;
            
            // Update form submit to handle edit instead of create
            const customerForm = document.getElementById('customer-form');
            customerForm.onsubmit = function(e) {
                e.preventDefault();
                updateRecord(recordId);
            };
            
            // Change save button text
            const saveBtn = customerForm.querySelector('button[type="submit"]');
            saveBtn.textContent = 'Update';
        }

        // Update record
        function updateRecord(recordId) {
            const recordIndex = records.findIndex(r => r.id === recordId);
            if (recordIndex === -1) return;
            
            // Get updated values from form
            records[recordIndex] = {
                ...records[recordIndex],
                customerName: document.getElementById('customer-name').value,
                surname: document.getElementById('customer-surname').value,
                email: document.getElementById('customer-email').value,
                phone: document.getElementById('customer-phone').value,
                address: document.getElementById('customer-address').value,
                pincode: document.getElementById('customer-pincode').value,
                state: document.getElementById('customer-state').value,
                machineName: document.getElementById('machine-name').value,
                machineSerial: document.getElementById('machine-serial').value,
                warrantyStatus: document.getElementById('warranty-status').value,
                recordStatus: document.getElementById('record-status').value,
                remarks: document.getElementById('customer-remark').value,
                balance: parseFloat(document.getElementById('total-balance').value) || 0,
                paymentStatus: document.getElementById('payment-status').value,
                date: new Date().toISOString().split('T')[0] // Update date to today
            };
            
            alert('Record updated successfully!');
            document.querySelector('[data-section="job-requests"]').click();
            resetCustomerForm();
        }

        // Delete record
        function deleteRecord(recordId) {
            records = records.filter(r => r.id !== recordId);
            loadJobRequests();
        }

        // Load all records
        function loadAllRecords(filterStatus = '') {
            const tableBody = document.getElementById('all-records-table');
            tableBody.innerHTML = '';
            
            let filteredRecords = records;
            
            if (filterStatus) {
                filteredRecords = filteredRecords.filter(r => r.recordStatus === filterStatus);
            }
            
            filteredRecords.forEach(record => {
                const assignedEngineer = assignments.find(a => a.recordId === record.id);
                const engineerName = assignedEngineer ? assignedEngineer.engineerName : 'Not Assigned';
                
                const row = document.createElement('tr');
                
                const statusClass = getStatusClass(record.recordStatus);
                const warrantyText = getWarrantyText(record.warrantyStatus);
                
                row.innerHTML = `
                    <td>${record.customerNumber}</td>
                    <td>${record.customerName} ${record.surname}</td>
                    <td>${record.machineName}</td>
                    <td>${record.machineSerial}</td>
                    <td><span class="${statusClass}">${record.recordStatus}</span></td>
                    <td>${warrantyText}</td>
                    <td>${record.date}</td>
                    <td>${engineerName}</td>
                    <td class="action-buttons">
                        <button class="btn btn-primary edit-btn" data-id="${record.id}">Edit</button>
                        <button class="btn btn-danger delete-btn" data-id="${record.id}">Delete</button>
                        <button class="btn btn-success view-btn" data-id="${record.id}">View</button>
                    </td>
                `;
                
                tableBody.appendChild(row);
            });
            
            // Add event listeners to buttons
            document.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    editRecord(recordId);
                });
            });
            
            document.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    if (confirm('Are you sure you want to delete this record?')) {
                        deleteRecord(recordId);
                        loadAllRecords();
                    }
                });
            });
            
            document.querySelectorAll('.view-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    viewRecord(recordId);
                });
            });
        }

        // View record details
        function viewRecord(recordId) {
            const record = records.find(r => r.id === recordId);
            if (!record) return;
            
            // You can implement a detailed view modal here
            let details = `
                <h3>Record Details</h3>
                <p><strong>Customer Number:</strong> ${record.customerNumber}</p>
                <p><strong>Customer Name:</strong> ${record.customerName} ${record.surname}</p>
                <p><strong>Email:</strong> ${record.email}</p>
                <p><strong>Contact:</strong> ${record.phone}</p>
                <p><strong>Address:</strong> ${record.address}, ${record.pincode}, ${record.state}, ${record.country}</p>
                <hr>
                <p><strong>Machine Name:</strong> ${record.machineName}</p>
                <p><strong>Serial Number:</strong> ${record.machineSerial}</p>
                <p><strong>Warranty Status:</strong> ${getWarrantyText(record.warrantyStatus)}</p>
                <p><strong>Record Status:</strong> ${record.recordStatus}</p>
                <p><strong>Date:</strong> ${record.date}</p>
                <p><strong>Remarks:</strong> ${record.remarks}</p>
                <p><strong>Balance:</strong> ₹${record.balance}</p>
                <p><strong>Payment Status:</strong> ${record.paymentStatus}</p>
            `;
            
            alert(details); // In a real app, you'd use a modal instead of alert
        }

        // Load assignment records
        function loadAssignmentRecords() {
            const recordSelect = document.getElementById('record-select');
            const assignmentsTable = document.getElementById('assignments-table');
            
            // Clear existing options
            recordSelect.innerHTML = '<option value="">Select Record</option>';
            assignmentsTable.innerHTML = '';
            
            // Add unassigned records to dropdown
            const unassignedRecords = records.filter(r => 
                !assignments.some(a => a.recordId === r.id)
            );
            
            unassignedRecords.forEach(record => {
                const option = document.createElement('option');
                option.value = record.id;
                option.textContent = `${record.customerNumber} - ${record.customerName} (${record.machineName})`;
                recordSelect.appendChild(option);
            });
            
            // Populate assignments table
            assignments.forEach(assignment => {
                const record = records.find(r => r.id === assignment.recordId);
                if (!record) return;
                
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${record.customerNumber}</td>
                    <td>${record.customerName}</td>
                    <td>${assignment.engineerName} (${assignment.engineerId})</td>
                    <td>${assignment.assignmentDate}</td>
                    <td>${assignment.status}</td>
                    <td class="action-buttons">
                        <button class="btn btn-primary view-assignment-btn" data-id="${assignment.recordId}">View</button>
                        <button class="btn btn-danger remove-assignment-btn" data-id="${assignment.recordId}">Remove</button>
                    </td>
                `;
                assignmentsTable.appendChild(row);
            });
            
            // Add event listeners
            document.querySelectorAll('.view-assignment-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    viewAssignment(recordId);
                });
            });
            
            document.querySelectorAll('.remove-assignment-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    if (confirm('Are you sure you want to remove this assignment?')) {
                        removeAssignment(recordId);
                    }
                });
            });
        }

        // View assignment details
        function viewAssignment(recordId) {
            const assignment = assignments.find(a => a.recordId === recordId);
            const record = records.find(r => r.id === recordId);
            
            if (!assignment || !record) return;
            
            let details = `
                <h3>Assignment Details</h3>
                <p><strong>Record ID:</strong> ${record.customerNumber}</p>
                <p><strong>Customer:</strong> ${record.customerName}</p>
                <p><strong>Machine:</strong> ${record.machineName} (${record.machineSerial})</p>
                <hr>
                <p><strong>Assigned Engineer:</strong> ${assignment.engineerName} (${assignment.engineerId})</p>
                <p><strong>Assignment Date:</strong> ${assignment.assignmentDate}</p>
                <p><strong>Status:</strong> ${assignment.status}</p>
                <p><strong>Remarks:</strong> ${assignment.remarks}</p>
            `;
            
            alert(details); // In a real app, use a modal
        }

        // Remove assignment
        function removeAssignment(recordId) {
            assignments = assignments.filter(a => a.recordId !== recordId);
            loadAssignmentRecords();
        }

        // Initialize form submissions
        function initForms() {
            // Customer form
            const customerForm = document.getElementById('customer-form');
            customerForm.addEventListener('submit', function(e) {
                e.preventDefault();
                saveNewCustomer();
            });
            
            // Assignment form
            const assignmentForm = document.getElementById('assignment-form');
            assignmentForm.addEventListener('submit', function(e) {
                e.preventDefault();
                saveAssignment();
            });
            
            // Account form
            const accountForm = document.getElementById('account-form');
            accountForm.addEventListener('submit', function(e) {
                e.preventDefault();
                updateAccount();
            });
            
            // Search buttons
            document.getElementById('search-btn').addEventListener('click', function() {
                const statusFilter = document.getElementById('status-filter').value;
                const warrantyFilter = document.getElementById('warranty-filter').value;
                loadJobRequests(statusFilter, warrantyFilter);
            });
            
            document.getElementById('view-search-btn').addEventListener('click', function() {
                const statusFilter = document.getElementById('view-status-filter').value;
                loadAllRecords(statusFilter);
            });
            
            // Report type change
            document.getElementById('report-type').addEventListener('change', function() {
                const reportType = this.value;
                document.getElementById('month-select-group').style.display = 
                    reportType === 'monthly' ? 'block' : 'none';
                document.getElementById('year-select-group').style.display = 
                    reportType === 'monthly' || reportType === 'yearly' ? 'block' : 'none';
                document.getElementById('custom-date-group').style.display = 
                    reportType === 'custom' ? 'block' : 'none';
                document.getElementById('custom-date-to-group').style.display = 
                    reportType === 'custom' ? 'block' : 'none';
            });
            
            // Generate report button
            document.getElementById('generate-report-btn').addEventListener('click', function() {
                generateReport();
            });
            
            // Print PDF button
            document.getElementById('print-pdf').addEventListener('click', function() {
                alert('PDF generation would be implemented here');
                // In a real app, this would generate a PDF of the current record
            });
        }

        // Save new customer
        function saveNewCustomer() {
            const newRecord = {
                id: records.length > 0 ? Math.max(...records.map(r => r.id)) + 1 : 1,
                customerNumber: document.getElementById('customer-number').value,
                customerName: document.getElementById('customer-name').value,
                surname: document.getElementById('customer-surname').value,
                email: document.getElementById('customer-email').value,
                phone: document.getElementById('customer-phone').value,
                address: document.getElementById('customer-address').value,
                pincode: document.getElementById('customer-pincode').value,
                state: document.getElementById('customer-state').value,
                country: document.getElementById('customer-country').value,
                machineName: document.getElementById('machine-name').value,
                machineSerial: document.getElementById('machine-serial').value,
                warrantyStatus: document.getElementById('warranty-status').value,
                recordStatus: document.getElementById('record-status').value,
                remarks: document.getElementById('customer-remark').value,
                balance: parseFloat(document.getElementById('total-balance').value) || 0,
                paymentStatus: document.getElementById('payment-status').value,
                date: new Date().toISOString().split('T')[0],
                assignedEngineer: '',
                images: [],
                files: []
            };
            
            records.push(newRecord);
            alert('Customer record saved successfully!');
            resetCustomerForm();
            generateCustomerNumber();
            document.querySelector('[data-section="job-requests"]').click();
        }

        // Reset customer form
        function resetCustomerForm() {
            document.getElementById('customer-form').reset();
            generateCustomerNumber();
            const saveBtn = document.querySelector('#customer-form button[type="submit"]');
            saveBtn.textContent = 'Save';
            document.getElementById('customer-form').onsubmit = function(e) {
                e.preventDefault();
                saveNewCustomer();
            };
        }

        // Save assignment
        function saveAssignment() {
            const recordId = parseInt(document.getElementById('record-select').value);
            const engineerId = document.getElementById('engineer-select').value;
            const remarks = document.getElementById('assignment-remarks').value;
            
            if (!recordId || !engineerId) {
                alert('Please select both record and engineer');
                return;
            }
            
            const engineerOption = document.getElementById('engineer-select').selectedOptions[0];
            const engineerName = engineerOption.textContent.split('(')[0].trim();
            
            const newAssignment = {
                recordId: recordId,
                engineerId: engineerId,
                engineerName: engineerName,
                assignmentDate: new Date().toISOString().split('T')[0],
                status: 'Assigned',
                remarks: remarks
            };
            
            assignments.push(newAssignment);
            alert('Engineer assigned successfully!');
            document.getElementById('assignment-form').reset();
            loadAssignmentRecords();
        }

        // Update account
        function updateAccount() {
            const currentPassword = document.getElementById('current-password').value;
            const newPassword = document.getElementById('new-password').value;
            const confirmPassword = document.getElementById('confirm-password').value;
            const newUsername = document.getElementById('new-username').value;
            
            if (currentPassword !== '12345') {
                alert('Current password is incorrect');
                return;
            }
            
            if (newPassword && newPassword !== confirmPassword) {
                alert('New passwords do not match');
                return;
            }
            
            if (newUsername) {
                usernameInput.value = newUsername;
                document.getElementById('current-username').value = newUsername;
                alert('Username updated successfully!');
            }
            
            if (newPassword) {
                passwordInput.value = newPassword;
                alert('Password updated successfully!');
            }
            
            document.getElementById('account-form').reset();
        }

        // Generate report
        function generateReport() {
            const reportType = document.getElementById('report-type').value;
            let filteredRecords = [...records];
            
            if (reportType === 'monthly') {
                const month = parseInt(document.getElementById('report-month').value);
                const year = parseInt(document.getElementById('report-year').value);
                
                filteredRecords = filteredRecords.filter(record => {
                    const recordDate = new Date(record.date);
                    return recordDate.getMonth() + 1 === month && recordDate.getFullYear() === year;
                });
            } else if (reportType === 'yearly') {
                const year = parseInt(document.getElementById('report-year').value);
                
                filteredRecords = filteredRecords.filter(record => {
                    const recordDate = new Date(record.date);
                    return recordDate.getFullYear() === year;
                });
            } else if (reportType === 'custom') {
                const dateFrom = document.getElementById('custom-date-from').value;
                const dateTo = document.getElementById('custom-date-to').value;
                
                if (dateFrom && dateTo) {
                    filteredRecords = filteredRecords.filter(record => {
                        return record.date >= dateFrom && record.date <= dateTo;
                    });
                }
            }
            
            // Display report summary
            const summary = document.getElementById('report-summary');
            summary.innerHTML = `
                <p><strong>Report Period:</strong> ${getReportPeriodText(reportType)}</p>
                <p><strong>Total Records:</strong> ${filteredRecords.length}</p>
                <p><strong>Create Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'create').length}</p>
                <p><strong>Accept Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'accept').length}</p>
                <p><strong>Running Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'running').length}</p>
                <p><strong>Hold Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'hold').length}</p>
                <p><strong>Public Holiday:</strong> ${filteredRecords.filter(r => r.recordStatus === 'public-holiday').length}</p>
            `;
            
            // Display report records
            const reportTable = document.getElementById('report-records-table');
            reportTable.innerHTML = '';
            
            filteredRecords.forEach(record => {
                const assignedEngineer = assignments.find(a => a.recordId === record.id);
                const engineerName = assignedEngineer ? assignedEngineer.engineerName : 'Not Assigned';
                
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${record.customerNumber}</td>
                    <td>${record.customerName} ${record.surname}</td>
                    <td>${record.machineName}</td>
                    <td>${record.recordStatus}</td>
                    <td>${record.date}</td>
                    <td>${engineerName}</td>
                `;
                reportTable.appendChild(row);
            });
        }

        // Get report period text
        function getReportPeriodText(reportType) {
            if (reportType === 'monthly') {
                const monthNames = ['January', 'February', 'March', 'April', 'May', 'June', 
                                  'July', 'August', 'September', 'October', 'November', 'December'];
                const month = parseInt(document.getElementById('report-month').value);
                const year = document.getElementById('report-year').value;
                return `${monthNames[month - 1]} ${year}`;
            } else if (reportType === 'yearly') {
                return document.getElementById('report-year').value;
            } else if (reportType === 'custom') {
                const dateFrom = document.getElementById('custom-date-from').value;
                const dateTo = document.getElementById('custom-date-to').value;
                return `${dateFrom} to ${dateTo}`;
            }
            return '';
        }

        // Initialize year dropdown
        function initYearDropdown() {
            const yearSelect = document.getElementById('report-year');
            const currentYear = new Date().getFullYear();
            
            for (let year = currentYear; year >= currentYear - 10; year--) {
                const option = document.createElement('option');
                option.value = year;
                option.textContent = year;
                yearSelect.appendChild(option);
            }
            
            yearSelect.value = currentYear;
        }

        // Initialize the application
        function init() {
            initForms();
            initYearDropdown();
        }

        // When DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
