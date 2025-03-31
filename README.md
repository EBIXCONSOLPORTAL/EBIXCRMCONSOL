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
            --warning-color: #f39c12;
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
            flex-wrap: wrap;
        }

        .nav-menu.dark-theme {
            background-color: #444;
        }

        .nav-menu button {
            padding: 10px 15px;
            margin-right: 10px;
            margin-bottom: 5px;
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
            margin-right: 10px;
            margin-bottom: 10px;
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

        .btn-warning {
            background-color: var(--warning-color);
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
            flex-wrap: wrap;
        }

        .filter-group {
            flex: 1;
            min-width: 200px;
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

        .status-create {
            color: #3498db;
            font-weight: 600;
        }

        .status-accept {
            color: #2ecc71;
            font-weight: 600;
        }

        .status-running {
            color: #f39c12;
            font-weight: 600;
        }

        .status-hold {
            color: #e74c3c;
            font-weight: 600;
        }

        .status-holiday {
            color: #9b59b6;
            font-weight: 600;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
        }

        .modal-content {
            background-color: white;
            margin: 5% auto;
            padding: 20px;
            border-radius: 5px;
            width: 80%;
            max-width: 800px;
            max-height: 80vh;
            overflow-y: auto;
        }

        .modal.dark-theme .modal-content {
            background-color: #333;
            color: white;
        }

        .close-modal {
            float: right;
            font-size: 24px;
            font-weight: bold;
            cursor: pointer;
        }

        .pagination {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }

        .pagination button {
            padding: 8px 12px;
            margin: 0 5px;
            border: 1px solid #ddd;
            background-color: white;
            cursor: pointer;
        }

        .pagination button.active {
            background-color: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        .record-count {
            margin-top: 10px;
            font-size: 14px;
            color: #777;
        }

        .record-count.dark-theme {
            color: #aaa;
        }

        @media (max-width: 768px) {
            .login-container {
                width: 90%;
                margin: 50px auto;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            
            .filter-group {
                min-width: 100%;
            }
            
            .modal-content {
                width: 95%;
                margin: 10% auto;
            }
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
                        <label for="customer-name-filter">Customer Name</label>
                        <input type="text" id="customer-name-filter" placeholder="Search by name">
                    </div>
                    <div class="filter-group">
                        <label for="machine-filter">Machine Name</label>
                        <input type="text" id="machine-filter" placeholder="Search by machine">
                    </div>
                    <div class="filter-group">
                        <label for="date-range-filter">Date Range</label>
                        <select id="date-range-filter">
                            <option value="">All Time</option>
                            <option value="today">Today</option>
                            <option value="week">This Week</option>
                            <option value="month">This Month</option>
                            <option value="custom">Custom Range</option>
                        </select>
                    </div>
                    <div class="filter-group" id="custom-date-filter-group" style="display: none;">
                        <label for="custom-date-from-filter">From</label>
                        <input type="date" id="custom-date-from-filter">
                    </div>
                    <div class="filter-group" id="custom-date-to-filter-group" style="display: none;">
                        <label for="custom-date-to-filter">To</label>
                        <input type="date" id="custom-date-to-filter">
                    </div>
                </div>
                <div class="filter-row">
                    <div class="filter-group">
                        <button class="btn btn-primary" id="search-btn">Search</button>
                        <button class="btn btn-warning" id="reset-filters-btn">Reset Filters</button>
                        <button class="btn btn-success" id="export-csv-btn">Export to CSV</button>
                    </div>
                </div>
            </div>
            
            <div class="record-count" id="job-requests-count"></div>
            
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
            
            <div class="pagination" id="job-requests-pagination">
                <!-- Pagination will be loaded here -->
            </div>
        </div>
        
        <!-- New Customer Section -->
        <div id="new-customer" class="content-area section-content" style="display: none;">
            <h3 id="customer-form-title">New Customer Information</h3>
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
                    <div id="image-preview" style="margin-top: 10px;"></div>
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
                    <button type="submit" class="btn btn-primary" id="save-customer-btn">Save</button>
                    <button type="button" class="btn btn-warning" id="cancel-edit-btn" style="display: none;">Cancel</button>
                    <button type="button" class="btn btn-success" id="print-pdf">Print PDF</button>
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
                        <label for="view-warranty-filter">Warranty Status</label>
                        <select id="view-warranty-filter">
                            <option value="">All</option>
                            <option value="in-warranty">In Warranty</option>
                            <option value="out-warranty">Out of Warranty</option>
                            <option value="amc">AMC</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="view-engineer-filter">Assigned Engineer</label>
                        <select id="view-engineer-filter">
                            <option value="">All</option>
                            <option value="EI102019004">Dev Makwana</option>
                            <option value="EI112034005">Hanuman Bishnoi</option>
                            <option value="EI4590778809">Mukesh Tanwar</option>
                            <option value="EI889906551">Dharmendra Singh</option>
                            <option value="unassigned">Unassigned</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="view-payment-filter">Payment Status</label>
                        <select id="view-payment-filter">
                            <option value="">All</option>
                            <option value="pending">Pending</option>
                            <option value="partial">Partial</option>
                            <option value="completed">Completed</option>
                        </select>
                    </div>
                </div>
                <div class="filter-row">
                    <div class="filter-group">
                        <label for="date-from">From Date</label>
                        <input type="date" id="date-from">
                    </div>
                    <div class="filter-group">
                        <label for="date-to">To Date</label>
                        <input type="date" id="date-to">
                    </div>
                    <div class="filter-group">
                        <label for="search-text">Search Text</label>
                        <input type="text" id="search-text" placeholder="Search in all fields">
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-primary" id="view-search-btn">Search</button>
                        <button class="btn btn-warning" id="view-reset-btn">Reset</button>
                    </div>
                </div>
            </div>
            
            <div class="record-count" id="all-records-count"></div>
            
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
                        <th>Payment</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody id="all-records-table">
                    <!-- Dynamic content will be loaded here -->
                </tbody>
            </table>
            
            <div class="pagination" id="all-records-pagination">
                <!-- Pagination will be loaded here -->
            </div>
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
            <div class="filter-section">
                <div class="filter-row">
                    <div class="filter-group">
                        <label for="assignment-engineer-filter">Filter by Engineer</label>
                        <select id="assignment-engineer-filter">
                            <option value="">All Engineers</option>
                            <option value="EI102019004">Dev Makwana</option>
                            <option value="EI112034005">Hanuman Bishnoi</option>
                            <option value="EI4590778809">Mukesh Tanwar</option>
                            <option value="EI889906551">Dharmendra Singh</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <label for="assignment-status-filter">Filter by Status</label>
                        <select id="assignment-status-filter">
                            <option value="">All Statuses</option>
                            <option value="Assigned">Assigned</option>
                            <option value="In Progress">In Progress</option>
                            <option value="Completed">Completed</option>
                            <option value="On Hold">On Hold</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-primary" id="assignment-search-btn">Filter</button>
                    </div>
                </div>
            </div>
            
            <div class="record-count" id="assignments-count"></div>
            
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
            
            <div class="pagination" id="assignments-pagination">
                <!-- Pagination will be loaded here -->
            </div>
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
                        <label for="report-format">Report Format</label>
                        <select id="report-format">
                            <option value="summary">Summary</option>
                            <option value="detailed">Detailed</option>
                        </select>
                    </div>
                    <div class="filter-group">
                        <button class="btn btn-primary" id="generate-report-btn">Generate Report</button>
                        <button class="btn btn-success" id="print-report-btn">Print Report</button>
                        <button class="btn btn-warning" id="export-report-btn">Export Report</button>
                    </div>
                </div>
            </div>
            
            <div id="report-results">
                <h4>Report Summary</h4>
                <div id="report-summary">
                    <!-- Report summary will be displayed here -->
                </div>
                
                <h4 id="detailed-records-heading" style="display: none;">Detailed Records</h4>
                <table class="records-table" id="report-records-table" style="display: none;">
                    <thead>
                        <tr>
                            <th>Record ID</th>
                            <th>Customer Name</th>
                            <th>Machine</th>
                            <th>Status</th>
                            <th>Date</th>
                            <th>Engineer</th>
                            <th>Payment</th>
                        </tr>
                    </thead>
                    <tbody>
                        <!-- Report records will be displayed here -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <div class="dashboard-footer" id="dashboard-footer">
            <p>ALL RIGHTS RESERVED BY DEV MAKWANA AND EBIXCRMCONSOL PVL LTD SINGAPORE 2025</p>
        </div>
    </div>

    <!-- Record Details Modal -->
    <div id="record-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <div id="modal-content">
                <!-- Modal content will be loaded here -->
            </div>
        </div>
    </div>

    <script>
        // Enhanced sample data for demonstration
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
                date: new Date().toISOString().split('T')[0],
                assignedEngineer: '',
                remarks: 'Initial complaint registered',
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
                date: new Date().toISOString().split('T')[0],
                assignedEngineer: 'EI102019004',
                remarks: 'Urgent repair needed',
                balance: 2500,
                paymentStatus: 'partial',
                images: [],
                files: []
            },
            {
                id: 3,
                customerNumber: 'CUST003',
                customerName: 'Robert Johnson',
                surname: 'Johnson',
                email: 'robert@example.com',
                phone: '9876543212',
                address: '789 Pine Rd, Bangalore',
                pincode: '560001',
                state: 'Karnataka',
                country: 'India',
                machineName: 'Copier DEF',
                machineSerial: 'SN345678',
                warrantyStatus: 'amc',
                recordStatus: 'running',
                date: new Date().toISOString().split('T')[0],
                assignedEngineer: 'EI112034005',
                remarks: 'Regular maintenance',
                balance: 5000,
                paymentStatus: 'completed',
                images: [],
                files: []
            },
            {
                id: 4,
                customerNumber: 'CUST004',
                customerName: 'Emily Davis',
                surname: 'Davis',
                email: 'emily@example.com',
                phone: '9876543213',
                address: '321 Elm St, Chennai',
                pincode: '600001',
                state: 'Tamil Nadu',
                country: 'India',
                machineName: 'Fax Machine GHI',
                machineSerial: 'SN901234',
                warrantyStatus: 'in-warranty',
                recordStatus: 'hold',
                date: new Date().toISOString().split('T')[0],
                assignedEngineer: '',
                remarks: 'Waiting for parts',
                balance: 1500,
                paymentStatus: 'pending',
                images: [],
                files: []
            },
            {
                id: 5,
                customerNumber: 'CUST005',
                customerName: 'Michael Wilson',
                surname: 'Wilson',
                email: 'michael@example.com',
                phone: '9876543214',
                address: '654 Maple Ave, Kolkata',
                pincode: '700001',
                state: 'West Bengal',
                country: 'India',
                machineName: 'Printer JKL',
                machineSerial: 'SN567890',
                warrantyStatus: 'out-warranty',
                recordStatus: 'public-holiday',
                date: new Date().toISOString().split('T')[0],
                assignedEngineer: 'EI4590778809',
                remarks: 'Service scheduled after holiday',
                balance: 3000,
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
                assignmentDate: new Date().toISOString().split('T')[0],
                status: 'Assigned',
                remarks: 'Urgent repair needed'
            },
            {
                recordId: 3,
                customerName: 'Robert Johnson',
                engineerId: 'EI112034005',
                engineerName: 'Hanuman Bishnoi',
                assignmentDate: new Date().toISOString().split('T')[0],
                status: 'In Progress',
                remarks: 'Regular maintenance'
            },
            {
                recordId: 5,
                customerName: 'Michael Wilson',
                engineerId: 'EI4590778809',
                engineerName: 'Mukesh Tanwar',
                assignmentDate: new Date().toISOString().split('T')[0],
                status: 'On Hold',
                remarks: 'Service scheduled after holiday'
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
        const recordModal = document.getElementById('record-modal');
        const closeModal = document.querySelector('.close-modal');
        const modalContent = document.getElementById('modal-content');
        const customerFormTitle = document.getElementById('customer-form-title');
        const saveCustomerBtn = document.getElementById('save-customer-btn');
        const cancelEditBtn = document.getElementById('cancel-edit-btn');

        // Pagination variables
        const recordsPerPage = 5;
        let currentPage = {
            'job-requests': 1,
            'records-view': 1,
            'engineer-assignment': 1
        };

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
                } else if (sectionId === 'new-customer') {
                    resetCustomerForm();
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
                document.querySelectorAll('.record-count').forEach(el => el.classList.add('dark-theme'));
                document.querySelector('.modal-content').classList.add('dark-theme');
            } else {
                body.classList.remove('dark-theme');
                dashboardHeader.classList.remove('dark-theme');
                dashboardFooter.classList.remove('dark-theme');
                document.querySelectorAll('.nav-menu').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.content-area').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.filter-section').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.records-table').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.settings-panel').forEach(el => el.classList.remove('dark-theme'));
                document.querySelectorAll('.record-count').forEach(el => el.classList.remove('dark-theme'));
                document.querySelector('.modal-content').classList.remove('dark-theme');
            }
        });

        // Generate customer number
        function generateCustomerNumber() {
            const customerNumber = document.getElementById('customer-number');
            const nextId = records.length > 0 ? 
                Math.max(...records.map(r => parseInt(r.customerNumber.replace('CUST', '')))) + 1 : 1;
            customerNumber.value = 'CUST' + nextId.toString().padStart(3, '0');
        }

        // Load job requests with pagination
        function loadJobRequests(filterStatus = '', filterWarranty = '', customerName = '', machineName = '', dateRange = '', customFrom = '', customTo = '', page = 1) {
            const tableBody = document.getElementById('job-requests-table');
            tableBody.innerHTML = '';
            
            let filteredRecords = [...records];
            
            // Apply filters
            if (filterStatus) {
                filteredRecords = filteredRecords.filter(r => r.recordStatus === filterStatus);
            }
            
            if (filterWarranty) {
                filteredRecords = filteredRecords.filter(r => r.warrantyStatus === filterWarranty);
            }
            
            if (customerName) {
                const searchTerm = customerName.toLowerCase();
                filteredRecords = filteredRecords.filter(r => 
                    r.customerName.toLowerCase().includes(searchTerm) || 
                    r.surname.toLowerCase().includes(searchTerm)
                );
            }
            
            if (machineName) {
                const searchTerm = machineName.toLowerCase();
                filteredRecords = filteredRecords.filter(r => 
                    r.machineName.toLowerCase().includes(searchTerm)
                );
            }
            
            if (dateRange) {
                const today = new Date();
                today.setHours(0, 0, 0, 0);
                
                if (dateRange === 'today') {
                    filteredRecords = filteredRecords.filter(r => {
                        const recordDate = new Date(r.date);
                        return recordDate.toDateString() === today.toDateString();
                    });
                } else if (dateRange === 'week') {
                    const firstDay = new Date(today);
                    firstDay.setDate(firstDay.getDate() - firstDay.getDay());
                    
                    const lastDay = new Date(firstDay);
                    lastDay.setDate(lastDay.getDate() + 6);
                    
                    filteredRecords = filteredRecords.filter(r => {
                        const recordDate = new Date(r.date);
                        return recordDate >= firstDay && recordDate <= lastDay;
                    });
                } else if (dateRange === 'month') {
                    const firstDay = new Date(today.getFullYear(), today.getMonth(), 1);
                    const lastDay = new Date(today.getFullYear(), today.getMonth() + 1, 0);
                    
                    filteredRecords = filteredRecords.filter(r => {
                        const recordDate = new Date(r.date);
                        return recordDate >= firstDay && recordDate <= lastDay;
                    });
                } else if (dateRange === 'custom' && customFrom && customTo) {
                    filteredRecords = filteredRecords.filter(r => {
                        return r.date >= customFrom && r.date <= customTo;
                    });
                }
            }
            
            // Update record count
            const recordCount = filteredRecords.length;
            document.getElementById('job-requests-count').textContent = `Showing ${recordCount} records`;
            
            // Calculate pagination
            const totalPages = Math.ceil(recordCount / recordsPerPage);
            currentPage['job-requests'] = Math.min(page, totalPages);
            
            // Get records for current page
            const startIndex = (currentPage['job-requests'] - 1) * recordsPerPage;
            const endIndex = Math.min(startIndex + recordsPerPage, recordCount);
            const paginatedRecords = filteredRecords.slice(startIndex, endIndex);
            
            // Populate table
            paginatedRecords.forEach(record => {
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
                        <button class="btn btn-success view-btn" data-id="${record.id}">View</button>
                    </td>
                `;
                
                tableBody.appendChild(row);
            });
            
            // Add event listeners to buttons
            addRecordEventListeners();
            
            // Update pagination controls
            updatePagination('job-requests', totalPages);
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

        // Add event listeners to record buttons
        function addRecordEventListeners() {
            // Edit buttons
            document.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    editRecord(recordId);
                });
            });
            
            // Delete buttons
            document.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    if (confirm('Are you sure you want to delete this record?')) {
                        deleteRecord(recordId);
                    }
                });
            });
            
            // View buttons
            document.querySelectorAll('.view-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    viewRecordDetails(recordId);
                });
            });
        }

        // Update pagination controls
        function updatePagination(section, totalPages) {
            const paginationDiv = document.getElementById(`${section}-pagination`);
            paginationDiv.innerHTML = '';
            
            if (totalPages <= 1) return;
            
            // Previous button
            const prevBtn = document.createElement('button');
            prevBtn.textContent = 'Previous';
            prevBtn.disabled = currentPage[section] === 1;
            prevBtn.addEventListener('click', () => {
                if (currentPage[section] > 1) {
                    if (section === 'job-requests') {
                        loadJobRequests(
                            document.getElementById('status-filter').value,
                            document.getElementById('warranty-filter').value,
                            document.getElementById('customer-name-filter').value,
                            document.getElementById('machine-filter').value,
                            document.getElementById('date-range-filter').value,
                            document.getElementById('custom-date-from-filter').value,
                            document.getElementById('custom-date-to-filter').value,
                            currentPage[section] - 1
                        );
                    } else if (section === 'records-view') {
                        loadAllRecords(
                            document.getElementById('view-status-filter').value,
                            document.getElementById('view-warranty-filter').value,
                            document.getElementById('view-engineer-filter').value,
                            document.getElementById('view-payment-filter').value,
                            document.getElementById('date-from').value,
                            document.getElementById('date-to').value,
                            document.getElementById('search-text').value,
                            currentPage[section] - 1
                        );
                    } else if (section === 'engineer-assignment') {
                        loadAssignmentRecords(
                            document.getElementById('assignment-engineer-filter').value,
                            document.getElementById('assignment-status-filter').value,
                            currentPage[section] - 1
                        );
                    }
                }
            });
            paginationDiv.appendChild(prevBtn);
            
            // Page numbers
            for (let i = 1; i <= totalPages; i++) {
                const pageBtn = document.createElement('button');
                pageBtn.textContent = i;
                pageBtn.className = currentPage[section] === i ? 'active' : '';
                pageBtn.addEventListener('click', () => {
                    if (section === 'job-requests') {
                        loadJobRequests(
                            document.getElementById('status-filter').value,
                            document.getElementById('warranty-filter').value,
                            document.getElementById('customer-name-filter').value,
                            document.getElementById('machine-filter').value,
                            document.getElementById('date-range-filter').value,
                            document.getElementById('custom-date-from-filter').value,
                            document.getElementById('custom-date-to-filter').value,
                            i
                        );
                    } else if (section === 'records-view') {
                        loadAllRecords(
                            document.getElementById('view-status-filter').value,
                            document.getElementById('view-warranty-filter').value,
                            document.getElementById('view-engineer-filter').value,
                            document.getElementById('view-payment-filter').value,
                            document.getElementById('date-from').value,
                            document.getElementById('date-to').value,
                            document.getElementById('search-text').value,
                            i
                        );
                    } else if (section === 'engineer-assignment') {
                        loadAssignmentRecords(
                            document.getElementById('assignment-engineer-filter').value,
                            document.getElementById('assignment-status-filter').value,
                            i
                        );
                    }
                });
                paginationDiv.appendChild(pageBtn);
            }
            
            // Next button
            const nextBtn = document.createElement('button');
            nextBtn.textContent = 'Next';
            nextBtn.disabled = currentPage[section] === totalPages;
            nextBtn.addEventListener('click', () => {
                if (currentPage[section] < totalPages) {
                    if (section === 'job-requests') {
                        loadJobRequests(
                            document.getElementById('status-filter').value,
                            document.getElementById('warranty-filter').value,
                            document.getElementById('customer-name-filter').value,
                            document.getElementById('machine-filter').value,
                            document.getElementById('date-range-filter').value,
                            document.getElementById('custom-date-from-filter').value,
                            document.getElementById('custom-date-to-filter').value,
                            currentPage[section] + 1
                        );
                    } else if (section === 'records-view') {
                        loadAllRecords(
                            document.getElementById('view-status-filter').value,
                            document.getElementById('view-warranty-filter').value,
                            document.getElementById('view-engineer-filter').value,
                            document.getElementById('view-payment-filter').value,
                            document.getElementById('date-from').value,
                            document.getElementById('date-to').value,
                            document.getElementById('search-text').value,
                            currentPage[section] + 1
                        );
                    } else if (section === 'engineer-assignment') {
                        loadAssignmentRecords(
                            document.getElementById('assignment-engineer-filter').value,
                            document.getElementById('assignment-status-filter').value,
                            currentPage[section] + 1
                        );
                    }
                }
            });
            paginationDiv.appendChild(nextBtn);
        }

        // Edit record
        function editRecord(recordId) {
            const record = records.find(r => r.id === recordId);
            if (!record) return;
            
            // Switch to new customer section and update form title
            document.querySelector('[data-section="new-customer"]').click();
            customerFormTitle.textContent = 'Edit Customer Information';
            saveCustomerBtn.textContent = 'Update';
            cancelEditBtn.style.display = 'inline-block';
            
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
        }

        // Cancel edit
        cancelEditBtn.addEventListener('click', function() {
            resetCustomerForm();
        });

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
            resetCustomerForm();
            loadJobRequests();
            loadAllRecords();
        }

        // Delete record
        function deleteRecord(recordId) {
            records = records.filter(r => r.id !== recordId);
            assignments = assignments.filter(a => a.recordId !== recordId);
            loadJobRequests();
            loadAllRecords();
            loadAssignmentRecords();
        }

        // View record details in modal
        function viewRecordDetails(recordId) {
            const record = records.find(r => r.id === recordId);
            if (!record) return;
            
            const assignedEngineer = assignments.find(a => a.recordId === recordId);
            
            let details = `
                <h3>Record Details - ${record.customerNumber}</h3>
                <div class="form-row">
                    <div class="form-group">
                        <label>Customer Name</label>
                        <p>${record.customerName} ${record.surname}</p>
                    </div>
                    <div class="form-group">
                        <label>Contact Information</label>
                        <p>${record.phone}<br>${record.email}</p>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Address</label>
                    <p>${record.address}, ${record.pincode}, ${record.state}, ${record.country}</p>
                </div>
                
                <h4>Machine Information</h4>
                <div class="form-row">
                    <div class="form-group">
                        <label>Machine Name</label>
                        <p>${record.machineName}</p>
                    </div>
                    <div class="form-group">
                        <label>Serial Number</label>
                        <p>${record.machineSerial}</p>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label>Warranty Status</label>
                        <p>${getWarrantyText(record.warrantyStatus)}</p>
                    </div>
                    <div class="form-group">
                        <label>Record Status</label>
                        <p><span class="${getStatusClass(record.recordStatus)}">${record.recordStatus}</span></p>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label>Date</label>
                        <p>${record.date}</p>
                    </div>
                    <div class="form-group">
                        <label>Assigned Engineer</label>
                        <p>${assignedEngineer ? assignedEngineer.engineerName : 'Not assigned'}</p>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label>Payment Status</label>
                        <p>${record.paymentStatus}</p>
                    </div>
                    <div class="form-group">
                        <label>Balance</label>
                        <p>₹${record.balance}</p>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Remarks</label>
                    <p>${record.remarks || 'No remarks'}</p>
                </div>
                
                <div class="form-group">
                    <button class="btn btn-primary" onclick="editRecord(${record.id}); closeModalFunc();">Edit Record</button>
                    ${assignedEngineer ? `<button class="btn btn-warning" onclick="viewAssignmentDetails(${record.id});">View Assignment</button>` : ''}
                </div>
            `;
            
            modalContent.innerHTML = details;
            recordModal.style.display = 'block';
        }

        // View assignment details in modal
        function viewAssignmentDetails(recordId) {
            const assignment = assignments.find(a => a.recordId === recordId);
            const record = records.find(r => r.id === recordId);
            
            if (!assignment || !record) return;
            
            let details = `
                <h3>Assignment Details</h3>
                <div class="form-row">
                    <div class="form-group">
                        <label>Record ID</label>
                        <p>${record.customerNumber}</p>
                    </div>
                    <div class="form-group">
                        <label>Customer</label>
                        <p>${record.customerName}</p>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Machine</label>
                    <p>${record.machineName} (${record.machineSerial})</p>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label>Assigned Engineer</label>
                        <p>${assignment.engineerName} (${assignment.engineerId})</p>
                    </div>
                    <div class="form-group">
                        <label>Assignment Date</label>
                        <p>${assignment.assignmentDate}</p>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label>Status</label>
                        <p>${assignment.status}</p>
                    </div>
                </div>
                
                <div class="form-group">
                    <label>Remarks</label>
                    <p>${assignment.remarks || 'No remarks'}</p>
                </div>
                
                <div class="form-group">
                    <button class="btn btn-primary" onclick="editAssignment(${record.id})">Edit Assignment</button>
                    <button class="btn btn-danger" onclick="removeAssignment(${record.id}); closeModalFunc();">Remove Assignment</button>
                </div>
            `;
            
            modalContent.innerHTML = details;
            recordModal.style.display = 'block';
        }

        // Close modal function
        function closeModalFunc() {
            recordModal.style.display = 'none';
        }

        // Close modal when clicking X
        closeModal.addEventListener('click', closeModalFunc);

        // Close modal when clicking outside
        window.addEventListener('click', function(event) {
            if (event.target === recordModal) {
                closeModalFunc();
            }
        });

        // Load all records with pagination
        function loadAllRecords(filterStatus = '', filterWarranty = '', filterEngineer = '', filterPayment = '', dateFrom = '', dateTo = '', searchText = '', page = 1) {
            const tableBody = document.getElementById('all-records-table');
            tableBody.innerHTML = '';
            
            let filteredRecords = [...records];
            
            // Apply filters
            if (filterStatus) {
                filteredRecords = filteredRecords.filter(r => r.recordStatus === filterStatus);
            }
            
            if (filterWarranty) {
                filteredRecords = filteredRecords.filter(r => r.warrantyStatus === filterWarranty);
            }
            
            if (filterEngineer) {
                if (filterEngineer === 'unassigned') {
                    filteredRecords = filteredRecords.filter(r => !r.assignedEngineer);
                } else {
                    filteredRecords = filteredRecords.filter(r => r.assignedEngineer === filterEngineer);
                }
            }
            
            if (filterPayment) {
                filteredRecords = filteredRecords.filter(r => r.paymentStatus === filterPayment);
            }
            
            if (dateFrom && dateTo) {
                filteredRecords = filteredRecords.filter(r => r.date >= dateFrom && r.date <= dateTo);
            } else if (dateFrom) {
                filteredRecords = filteredRecords.filter(r => r.date >= dateFrom);
            } else if (dateTo) {
                filteredRecords = filteredRecords.filter(r => r.date <= dateTo);
            }
            
            if (searchText) {
                const searchTerm = searchText.toLowerCase();
                filteredRecords = filteredRecords.filter(r => 
                    r.customerNumber.toLowerCase().includes(searchTerm) ||
                    r.customerName.toLowerCase().includes(searchTerm) ||
                    r.surname.toLowerCase().includes(searchTerm) ||
                    r.email.toLowerCase().includes(searchTerm) ||
                    r.phone.toLowerCase().includes(searchTerm) ||
                    r.machineName.toLowerCase().includes(searchTerm) ||
                    r.machineSerial.toLowerCase().includes(searchTerm) ||
                    r.remarks.toLowerCase().includes(searchTerm)
                );
            }
            
            // Update record count
            const recordCount = filteredRecords.length;
            document.getElementById('all-records-count').textContent = `Showing ${recordCount} records`;
            
            // Calculate pagination
            const totalPages = Math.ceil(recordCount / recordsPerPage);
            currentPage['records-view'] = Math.min(page, totalPages);
            
            // Get records for current page
            const startIndex = (currentPage['records-view'] - 1) * recordsPerPage;
            const endIndex = Math.min(startIndex + recordsPerPage, recordCount);
            const paginatedRecords = filteredRecords.slice(startIndex, endIndex);
            
            // Populate table
            paginatedRecords.forEach(record => {
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
                    <td>${record.paymentStatus} (₹${record.balance})</td>
                    <td class="action-buttons">
                        <button class="btn btn-primary edit-btn" data-id="${record.id}">Edit</button>
                        <button class="btn btn-danger delete-btn" data-id="${record.id}">Delete</button>
                        <button class="btn btn-success view-btn" data-id="${record.id}">View</button>
                    </td>
                `;
                
                tableBody.appendChild(row);
            });
            
            // Add event listeners to buttons
            addRecordEventListeners();
            
            // Update pagination controls
            updatePagination('records-view', totalPages);
        }

        // Load assignment records with pagination
        function loadAssignmentRecords(filterEngineer = '', filterStatus = '', page = 1) {
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
            
            // Filter assignments
            let filteredAssignments = [...assignments];
            
            if (filterEngineer) {
                filteredAssignments = filteredAssignments.filter(a => a.engineerId === filterEngineer);
            }
            
            if (filterStatus) {
                filteredAssignments = filteredAssignments.filter(a => a.status === filterStatus);
            }
            
            // Update record count
            const assignmentCount = filteredAssignments.length;
            document.getElementById('assignments-count').textContent = `Showing ${assignmentCount} assignments`;
            
            // Calculate pagination
            const totalPages = Math.ceil(assignmentCount / recordsPerPage);
            currentPage['engineer-assignment'] = Math.min(page, totalPages);
            
            // Get assignments for current page
            const startIndex = (currentPage['engineer-assignment'] - 1) * recordsPerPage;
            const endIndex = Math.min(startIndex + recordsPerPage, assignmentCount);
            const paginatedAssignments = filteredAssignments.slice(startIndex, endIndex);
            
            // Populate assignments table
            paginatedAssignments.forEach(assignment => {
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
                        <button class="btn btn-warning edit-assignment-btn" data-id="${assignment.recordId}">Edit</button>
                    </td>
                `;
                assignmentsTable.appendChild(row);
            });
            
            // Add event listeners
            document.querySelectorAll('.view-assignment-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    viewAssignmentDetails(recordId);
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
            
            document.querySelectorAll('.edit-assignment-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const recordId = parseInt(this.getAttribute('data-id'));
                    editAssignment(recordId);
                });
            });
            
            // Update pagination controls
            updatePagination('engineer-assignment', totalPages);
        }

        // Edit assignment
        function editAssignment(recordId) {
            const assignment = assignments.find(a => a.recordId === recordId);
            if (!assignment) return;
            
            // Update modal with edit form
            modalContent.innerHTML = `
                <h3>Edit Assignment</h3>
                <form id="edit-assignment-form">
                    <div class="form-group">
                        <label for="edit-engineer-select">Engineer</label>
                        <select id="edit-engineer-select" required>
                            <option value="EI102019004" ${assignment.engineerId === 'EI102019004' ? 'selected' : ''}>Dev Makwana (EI102019004)</option>
                            <option value="EI112034005" ${assignment.engineerId === 'EI112034005' ? 'selected' : ''}>Hanuman Bishnoi (EI112034005)</option>
                            <option value="EI4590778809" ${assignment.engineerId === 'EI4590778809' ? 'selected' : ''}>Mukesh Tanwar (EI4590778809)</option>
                            <option value="EI889906551" ${assignment.engineerId === 'EI889906551' ? 'selected' : ''}>Dharmendra Singh (EI889906551)</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="edit-assignment-status">Status</label>
                        <select id="edit-assignment-status" required>
                            <option value="Assigned" ${assignment.status === 'Assigned' ? 'selected' : ''}>Assigned</option>
                            <option value="In Progress" ${assignment.status === 'In Progress' ? 'selected' : ''}>In Progress</option>
                            <option value="Completed" ${assignment.status === 'Completed' ? 'selected' : ''}>Completed</option>
                            <option value="On Hold" ${assignment.status === 'On Hold' ? 'selected' : ''}>On Hold</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="edit-assignment-remarks">Remarks</label>
                        <textarea id="edit-assignment-remarks">${assignment.remarks || ''}</textarea>
                    </div>
                    
                    <div class="form-group">
                        <button type="submit" class="btn btn-primary">Update Assignment</button>
                        <button type="button" class="btn btn-warning" onclick="closeModalFunc()">Cancel</button>
                    </div>
                </form>
            `;
            
            document.getElementById('edit-assignment-form').addEventListener('submit', function(e) {
                e.preventDefault();
                updateAssignment(recordId);
            });
            
            recordModal.style.display = 'block';
        }

        // Update assignment
        function updateAssignment(recordId) {
            const assignmentIndex = assignments.findIndex(a => a.recordId === recordId);
            if (assignmentIndex === -1) return;
            
            const engineerId = document.getElementById('edit-engineer-select').value;
            const engineerOption = document.getElementById('edit-engineer-select').selectedOptions[0];
            const engineerName = engineerOption.textContent.split('(')[0].trim();
            
            assignments[assignmentIndex] = {
                ...assignments[assignmentIndex],
                engineerId: engineerId,
                engineerName: engineerName,
                status: document.getElementById('edit-assignment-status').value,
                remarks: document.getElementById('edit-assignment-remarks').value
            };
            
            // Also update the assigned engineer in the record
            const recordIndex = records.findIndex(r => r.id === recordId);
            if (recordIndex !== -1) {
                records[recordIndex].assignedEngineer = engineerId;
            }
            
            alert('Assignment updated successfully!');
            closeModalFunc();
            loadAssignmentRecords();
            loadAllRecords();
        }

        // Remove assignment
        function removeAssignment(recordId) {
            assignments = assignments.filter(a => a.recordId !== recordId);
            
            // Also remove the assigned engineer from the record
            const recordIndex = records.findIndex(r => r.id === recordId);
            if (recordIndex !== -1) {
                records[recordIndex].assignedEngineer = '';
            }
            
            loadAssignmentRecords();
            loadAllRecords();
        }

        // Reset customer form
        function resetCustomerForm() {
            document.getElementById('customer-form').reset();
            generateCustomerNumber();
            customerFormTitle.textContent = 'New Customer Information';
            saveCustomerBtn.textContent = 'Save';
            cancelEditBtn.style.display = 'none';
            document.getElementById('image-preview').innerHTML = '';
            
            // Reset form submit to handle new customer
            document.getElementById('customer-form').onsubmit = function(e) {
                e.preventDefault();
                saveNewCustomer();
            };
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
            loadJobRequests();
            loadAllRecords();
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
            
            const record = records.find(r => r.id === recordId);
            if (!record) {
                alert('Selected record not found');
                return;
            }
            
            const engineerOption = document.getElementById('engineer-select').selectedOptions[0];
            const engineerName = engineerOption.textContent.split('(')[0].trim();
            
            const newAssignment = {
                recordId: recordId,
                customerName: record.customerName,
                engineerId: engineerId,
                engineerName: engineerName,
                assignmentDate: new Date().toISOString().split('T')[0],
                status: 'Assigned',
                remarks: remarks
            };
            
            assignments.push(newAssignment);
            
            // Update the record with assigned engineer
            record.assignedEngineer = engineerId;
            
            alert('Engineer assigned successfully!');
            document.getElementById('assignment-form').reset();
            loadAssignmentRecords();
            loadAllRecords();
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
            const reportFormat = document.getElementById('report-format').value;
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
                <div class="form-row">
                    <div class="form-group">
                        <p><strong>Create Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'create').length}</p>
                        <p><strong>Accept Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'accept').length}</p>
                    </div>
                    <div class="form-group">
                        <p><strong>Running Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'running').length}</p>
                        <p><strong>Hold Status:</strong> ${filteredRecords.filter(r => r.recordStatus === 'hold').length}</p>
                    </div>
                    <div class="form-group">
                        <p><strong>Public Holiday:</strong> ${filteredRecords.filter(r => r.recordStatus === 'public-holiday').length}</p>
                        <p><strong>Assigned Jobs:</strong> ${filteredRecords.filter(r => r.assignedEngineer).length}</p>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <p><strong>In Warranty:</strong> ${filteredRecords.filter(r => r.warrantyStatus === 'in-warranty').length}</p>
                    </div>
                    <div class="form-group">
                        <p><strong>Out of Warranty:</strong> ${filteredRecords.filter(r => r.warrantyStatus === 'out-warranty').length}</p>
                    </div>
                    <div class="form-group">
                        <p><strong>AMC:</strong> ${filteredRecords.filter(r => r.warrantyStatus === 'amc').length}</p>
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <p><strong>Pending Payments:</strong> ${filteredRecords.filter(r => r.paymentStatus === 'pending').length}</p>
                    </div>
                    <div class="form-group">
                        <p><strong>Partial Payments:</strong> ${filteredRecords.filter(r => r.paymentStatus === 'partial').length}</p>
                    </div>
                    <div class="form-group">
                        <p><strong>Completed Payments:</strong> ${filteredRecords.filter(r => r.paymentStatus === 'completed').length}</p>
                    </div>
                </div>
                <p><strong>Total Revenue:</strong> ₹${filteredRecords.reduce((sum, r) => sum + (r.balance || 0), 0)}</p>
            `;
            
            // Show/hide detailed records based on report format
            if (reportFormat === 'detailed') {
                document.getElementById('detailed-records-heading').style.display = 'block';
                const reportTable = document.getElementById('report-records-table');
                reportTable.style.display = 'table';
                const tbody = reportTable.querySelector('tbody');
                tbody.innerHTML = '';
                
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
                        <td>${record.paymentStatus} (₹${record.balance})</td>
                    `;
                    tbody.appendChild(row);
                });
            } else {
                document.getElementById('detailed-records-heading').style.display = 'none';
                document.getElementById('report-records-table').style.display = 'none';
            }
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

        // Image preview for upload
        document.getElementById('image-upload').addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (!file) return;
            
            const reader = new FileReader();
            reader.onload = function(event) {
                const img = document.createElement('img');
                img.src = event.target.result;
                img.style.maxWidth = '200px';
                img.style.maxHeight = '200px';
                document.getElementById('image-preview').innerHTML = '';
                document.getElementById('image-preview').appendChild(img);
            };
            reader.readAsDataURL(file);
        });

        // Date range filter toggle
        document.getElementById('date-range-filter').addEventListener('change', function() {
            const isCustom = this.value === 'custom';
            document.getElementById('custom-date-filter-group').style.display = isCustom ? 'block' : 'none';
            document.getElementById('custom-date-to-filter-group').style.display = isCustom ? 'block' : 'none';
        });

        // Report type filter toggle
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

        // Initialize the application
        function init() {
            // Job Requests filters
            document.getElementById('search-btn').addEventListener('click', function() {
                loadJobRequests(
                    document.getElementById('status-filter').value,
                    document.getElementById('warranty-filter').value,
                    document.getElementById('customer-name-filter').value,
                    document.getElementById('machine-filter').value,
                    document.getElementById('date-range-filter').value,
                    document.getElementById('custom-date-from-filter').value,
                    document.getElementById('custom-date-to-filter').value
                );
            });
            
            document.getElementById('reset-filters-btn').addEventListener('click', function() {
                document.getElementById('status-filter').value = '';
                document.getElementById('warranty-filter').value = '';
                document.getElementById('customer-name-filter').value = '';
                document.getElementById('machine-filter').value = '';
                document.getElementById('date-range-filter').value = '';
                document.getElementById('custom-date-from-filter').value = '';
                document.getElementById('custom-date-to-filter').value = '';
                loadJobRequests();
            });
            
            document.getElementById('export-csv-btn').addEventListener('click', function() {
                alert('CSV export functionality would be implemented here');
                // In a real app, this would generate a CSV file
            });
            
            // Records View filters
            document.getElementById('view-search-btn').addEventListener('click', function() {
                loadAllRecords(
                    document.getElementById('view-status-filter').value,
                    document.getElementById('view-warranty-filter').value,
                    document.getElementById('view-engineer-filter').value,
                    document.getElementById('view-payment-filter').value,
                    document.getElementById('date-from').value,
                    document.getElementById('date-to').value,
                    document.getElementById('search-text').value
                );
            });
            
            document.getElementById('view-reset-btn').addEventListener('click', function() {
                document.getElementById('view-status-filter').value = '';
                document.getElementById('view-warranty-filter').value = '';
                document.getElementById('view-engineer-filter').value = '';
                document.getElementById('view-payment-filter').value = '';
                document.getElementById('date-from').value = '';
                document.getElementById('date-to').value = '';
                document.getElementById('search-text').value = '';
                loadAllRecords();
            });
            
            // Engineer Assignment filters
            document.getElementById('assignment-search-btn').addEventListener('click', function() {
                loadAssignmentRecords(
                    document.getElementById('assignment-engineer-filter').value,
                    document.getElementById('assignment-status-filter').value
                );
            });
            
            // Assignment form
            document.getElementById('assignment-form').addEventListener('submit', function(e) {
                e.preventDefault();
                saveAssignment();
            });
            
            // Customer form
            document.getElementById('customer-form').addEventListener('submit', function(e) {
                e.preventDefault();
                saveNewCustomer();
            });
            
            // Account form
            document.getElementById('account-form').addEventListener('submit', function(e) {
                e.preventDefault();
                updateAccount();
            });
            
            // Print PDF button
            document.getElementById('print-pdf').addEventListener('click', function() {
                alert('PDF generation would be implemented here');
                // In a real app, this would generate a PDF of the current record
            });
            
            // Generate report button
            document.getElementById('generate-report-btn').addEventListener('click', function() {
                generateReport();
            });
            
            // Print report button
            document.getElementById('print-report-btn').addEventListener('click', function() {
                window.print();
            });
            
            // Export report button
            document.getElementById('export-report-btn').addEventListener('click', function() {
                alert('Report export functionality would be implemented here');
                // In a real app, this would export the report in selected format
            });
            
            initYearDropdown();
        }

        // When DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
