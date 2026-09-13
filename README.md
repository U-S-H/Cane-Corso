<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Excel to Web Application - Prime Solutions Pro Demo</title>
    <style>
        :root {
            --bg-gradient: linear-gradient(-45deg, #0f172a, #1e1b4b, #065f46, #1e293b);
            --card-bg: rgba(30, 41, 59, 0.75);
            --text-color: #f8fafc;
            --border-color: rgba(255, 255, 255, 0.1);
            --primary: #0ea5e9;
            --primary-hover: #0284c7;
            --accent: #10b981;
            --accent-hover: #059669;
            --input-bg: #0f172a;
            --input-border: #334155;
        }

        .light-mode {
            --bg-gradient: linear-gradient(-45deg, #f8fafc, #e2e8f0, #ccfbf1, #f1f5f9);
            --card-bg: rgba(255, 255, 255, 0.85);
            --text-color: #0f172a;
            --border-color: rgba(0, 0, 0, 0.1);
            --primary: #0284c7;
            --primary-hover: #0369a1;
            --accent: #059669;
            --accent-hover: #047857;
            --input-bg: #ffffff;
            --input-border: #cbd5e1;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            transition: background 0.3s, color 0.3s;
        }

        body {
            background: var(--bg-gradient);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: var(--text-color);
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating Background Particles */
        .particles {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            overflow: hidden;
            z-index: -1;
        }

        .particle {
            position: absolute;
            display: block;
            list-style: none;
            width: 20px; height: 20px;
            background: rgba(14, 165, 233, 0.15);
            animation: floatUp 20s linear infinite;
            bottom: -150px;
            border-radius: 50%;
        }

        .particle:nth-child(1) { left: 10%; width: 40px; height: 40px; animation-duration: 12s; }
        .particle:nth-child(2) { left: 25%; width: 20px; height: 20px; animation-duration: 18s; animation-delay: 2s; }
        .particle:nth-child(3) { left: 70%; width: 50px; height: 50px; animation-duration: 15s; animation-delay: 4s; }
        .particle:nth-child(4) { left: 85%; width: 25px; height: 25px; animation-duration: 22s; animation-delay: 1s; }

        @keyframes floatUp {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-1000px) rotate(720deg); opacity: 0; }
        }

        .container {
            width: 100%;
            max-width: 1050px;
            background: var(--card-bg);
            backdrop-filter: blur(16px);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
            overflow: hidden;
            z-index: 1;
        }

        header {
            background: linear-gradient(135deg, #0284c7, #0d9488);
            padding: 20px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #fff;
        }

        header h1 {
            font-size: 22px;
            font-weight: 700;
        }

        header p {
            font-size: 12px;
            opacity: 0.9;
        }

        .theme-btn {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            padding: 8px 14px;
            border-radius: 8px;
            color: #fff;
            cursor: pointer;
            font-weight: 600;
            font-size: 13px;
        }

        .theme-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            padding: 25px;
        }

        @media(max-width: 768px) {
            .main-grid { grid-template-columns: 1fr; }
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            padding: 20px;
        }

        h2 {
            font-size: 15px;
            color: var(--primary);
            margin-bottom: 15px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 8px;
        }

        .input-group {
            margin-bottom: 12px;
        }

        label {
            display: block;
            font-size: 12px;
            margin-bottom: 4px;
            opacity: 0.9;
        }

        input {
            width: 100%;
            padding: 9px 12px;
            background: var(--input-bg);
            border: 1px solid var(--input-border);
            border-radius: 8px;
            color: var(--text-color);
            font-size: 13px;
        }

        input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 8px rgba(14, 165, 233, 0.3);
        }

        .invoice-preview {
            background: #ffffff;
            color: #0f172a;
            border-radius: 10px;
            padding: 18px;
            font-size: 13px;
        }

        .inv-header {
            display: flex;
            justify-content: space-between;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 8px;
            margin-bottom: 12px;
        }

        .inv-header h3 { color: #1e3a8a; font-size: 15px; }

        .inv-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 6px;
        }

        .inv-total {
            border-top: 2px solid #e2e8f0;
            padding-top: 8px;
            margin-top: 8px;
            font-weight: bold;
            font-size: 14px;
            color: #0d9488;
        }

        .actions {
            grid-column: 1 / -1;
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        button.action-btn {
            flex: 1;
            padding: 11px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            font-size: 13px;
            cursor: pointer;
        }

        .btn-calc { background: var(--primary); color: white; }
        .btn-calc:hover { background: var(--primary-hover); }

        .btn-save { background: var(--accent); color: white; }
        .btn-save:hover { background: var(--accent-hover); }

        .btn-pdf { background: #6366f1; color: white; }
        .btn-pdf:hover { background: #4f46e5; }

        .status {
            grid-column: 1 / -1;
            text-align: center;
            font-size: 12px;
            min-height: 18px;
            color: var(--primary);
        }

        /* Database History Table Section */
        .history-section {
            grid-column: 1 / -1;
            margin-top: 10px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            padding: 20px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 12px;
            margin-top: 10px;
        }

        th, td {
            padding: 8px 10px;
            text-align: left;
            border-bottom: 1px solid var(--border-color);
        }

        th { color: var(--primary); font-weight: 600; }
    </style>
</head>
<body>

    <!-- Floating Background Animation Particles -->
    <ul class="particles">
        <li class="particle"></li>
        <li class="particle"></li>
        <li class="particle"></li>
        <li class="particle"></li>
    </ul>

    <div class="container">
        <header>
            <div>
                <h1>Prime Solutions - Excel to Web Engine</h1>
                <p>Automated Calculations, Live Database & PDF Invoices</p>
            </div>
            <button class="theme-btn" onclick="toggleTheme()">Toggle Theme</button>
        </header>

        <div class="main-grid">
            <!-- Excel Form Inputs -->
            <div class="card">
                <h2>Excel Formula Inputs</h2>
                <div class="input-group">
                    <label>Client / Item Description</label>
                    <input type="text" id="desc" value="Custom Web App Service" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Quantity / Units</label>
                    <input type="number" id="qty" value="5" min="1" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Unit Price ($)</label>
                    <input type="number" id="price" value="120" min="0" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Discount Rate (%)</label>
                    <input type="number" id="discount" value="10" min="0" max="100" oninput="runExcelLogic()">
                </div>
            </div>

            <!-- Live Invoice Preview -->
            <div class="card">
                <h2>Generated Invoice Preview</h2>
                <div class="invoice-preview" id="invoiceArea">
                    <div class="inv-header">
                        <h3 id="invTitle">INVOICE #PS-902</h3>
                        <span id="invDate">2026-09-13</span>
                    </div>
                    <div class="inv-row">
                        <span id="pDesc">Custom Web App Service</span>
                        <span id="pQtyPrice">5 x $120.00</span>
                    </div>
                    <div class="inv-row">
                        <span>Subtotal:</span>
                        <span id="subtotal">$600.00</span>
                    </div>
                    <div class="inv-row">
                        <span>Discount Applied:</span>
                        <span id="discAmount">-$60.00</span>
                    </div>
                    <div class="inv-total inv-row">
                        <span>Total Balance:</span>
                        <span id="grandTotal">$540.00</span>
                    </div>
                </div>
            </div>

            <!-- Actions -->
            <div class="actions">
                <button class="action-btn btn-calc" onclick="runExcelLogic()">Run Auto-Calculation</button>
                <button class="action-btn btn-save" onclick="saveData()">Save to Database</button>
                <button class="action-btn btn-pdf" onclick="downloadPDF()">Download PDF Invoice</button>
            </div>

            <div class="status" id="statusMessage"></div>

            <!-- Database Records History Table -->
            <div class="history-section">
                <h2>Database Records (Live Saved Invoices)</h2>
                <table>
                    <thead>
                        <tr>
                            <th>Invoice ID</th>
                            <th>Description</th>
                            <th>Qty</th>
                            <th>Total</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody id="historyTableBody">
                        <tr>
                            <td>#PS-901</td>
                            <td>Excel Model Migration</td>
                            <td>2</td>
                            <td>$240.00</td>
                            <td style="color: #10b981;">Saved ✅</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <script>
        function runExcelLogic() {
            const desc = document.getElementById('desc').value;
            const qty = parseFloat(document.getElementById('qty').value) || 0;
            const price = parseFloat(document.getElementById('price').value) || 0;
            const discountRate = parseFloat(document.getElementById('discount').value) || 0;

            const subtotal = qty * price;
            const discAmount = (subtotal * discountRate) / 100;
            const grandTotal = subtotal - discAmount;

            document.getElementById('pDesc').innerText = desc || 'Item';
            document.getElementById('pQtyPrice').innerText = `${qty} x $${price.toFixed(2)}`;
            document.getElementById('subtotal').innerText = `$${subtotal.toFixed(2)}`;
            document.getElementById('discAmount').innerText = `-$${discAmount.toFixed(2)}`;
            document.getElementById('grandTotal').innerText = `$${grandTotal.toFixed(2)}`;
        }

        let invCounter = 902;
        function saveData() {
            const status = document.getElementById('statusMessage');
            const desc = document.getElementById('desc').value || 'Service';
            const qty = document.getElementById('qty').value || 1;
            const total = document.getElementById('grandTotal').innerText;

            status.innerHTML = "Syncing with Database (Firebase/SQL)...";
            status.style.color = "#f59e0b";

            setTimeout(() => {
                status.innerHTML = "Success! Data safely stored in database.";
                status.style.color = "#10b981";

                // Add to history table
                const tbody = document.getElementById('historyTableBody');
                const newRow = document.createElement('tr');
                newRow.innerHTML = `<td>#PS-${invCounter}</td><td>${desc}</td><td>${qty}</td><td>${total}</td><td style="color: #10b981;">Saved ✅</td>`;
                tbody.prepend(newRow);
                invCounter++;
            }, 1000);
        }

        function downloadPDF() {
            const status = document.getElementById('statusMessage');
            status.innerHTML = "Generating professional PDF invoice...";
            status.style.color = "#6366f1";

            setTimeout(() => {
                status.innerHTML = "PDF Invoice successfully downloaded!";
                status.style.color = "#10b981";
            }, 1200);
        }

        function toggleTheme() {
            document.body.classList.toggle('light-mode');
        }
    </script>
</body>
</html>
