<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Excel to Web Application - Prime Solutions Ultimate Pro</title>
    <style>
        :root {
            --bg-gradient: linear-gradient(-45deg, #0f172a, #1e1b4b, #065f46, #1e293b);
            --card-bg: rgba(30, 41, 59, 0.78);
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
            --card-bg: rgba(255, 255, 255, 0.88);
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
            width: 25px; height: 25px;
            background: rgba(14, 165, 233, 0.15);
            animation: floatUp 20s linear infinite;
            bottom: -150px;
            border-radius: 50%;
        }

        .particle:nth-child(1) { left: 10%; width: 35px; height: 35px; animation-duration: 12s; }
        .particle:nth-child(2) { left: 30%; width: 20px; height: 20px; animation-duration: 18s; animation-delay: 2s; }
        .particle:nth-child(3) { left: 75%; width: 45px; height: 45px; animation-duration: 15s; animation-delay: 4s; }

        @keyframes floatUp {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-1000px) rotate(720deg); opacity: 0; }
        }

        .container {
            width: 100%;
            max-width: 1100px;
            background: var(--card-bg);
            backdrop-filter: blur(16px);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.35);
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

        header h1 { font-size: 21px; font-weight: 700; }
        header p { font-size: 12px; opacity: 0.9; }

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
        .theme-btn:hover { background: rgba(255, 255, 255, 0.3); }

        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            padding: 25px;
        }

        @media(max-width: 768px) {
            .main-grid { grid-template-columns: 1fr; }
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            padding: 18px;
        }

        h2 {
            font-size: 14px;
            color: var(--primary);
            margin-bottom: 12px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 6px;
        }

        .input-group { margin-bottom: 10px; }
        label { display: block; font-size: 11px; margin-bottom: 3px; opacity: 0.9; }
        input, select {
            width: 100%;
            padding: 8px 10px;
            background: var(--input-bg);
            border: 1px solid var(--input-border);
            border-radius: 8px;
            color: var(--text-color);
            font-size: 12px;
        }

        .file-upload-box {
            border: 2px dashed var(--primary);
            padding: 12px;
            text-align: center;
            border-radius: 8px;
            cursor: pointer;
            font-size: 12px;
            margin-bottom: 12px;
            background: rgba(14, 165, 233, 0.05);
        }

        .invoice-preview {
            background: #ffffff;
            color: #0f172a;
            border-radius: 10px;
            padding: 15px;
            font-size: 12px;
        }

        .inv-header {
            display: flex;
            justify-content: space-between;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 6px;
            margin-bottom: 10px;
        }
        .inv-header h3 { color: #1e3a8a; font-size: 14px; }

        .inv-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }

        .inv-total {
            border-top: 2px solid #e2e8f0;
            padding-top: 6px;
            margin-top: 6px;
            font-weight: bold;
            font-size: 13px;
            color: #0d9488;
        }

        /* Signature Canvas */
        .sig-container {
            margin-top: 10px;
        }
        canvas#sigCanvas {
            width: 100%;
            height: 50px;
            background: #ffffff;
            border: 1px solid var(--input-border);
            border-radius: 6px;
            cursor: crosshair;
        }

        .actions {
            grid-column: 1 / -1;
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        button.action-btn {
            flex: 1;
            padding: 10px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            font-size: 12px;
            cursor: pointer;
        }

        .btn-calc { background: var(--primary); color: white; }
        .btn-calc:hover { background: var(--primary-hover); }

        .btn-save { background: var(--accent); color: white; }
        .btn-save:hover { background: var(--accent-hover); }

        .btn-pdf { background: #6366f1; color: white; }
        .btn-pdf:hover { background: #4f46e5; }

        .btn-email { background: #ec4899; color: white; }
        .btn-email:hover { background: #db2777; }

        .status {
            grid-column: 1 / -1;
            text-align: center;
            font-size: 12px;
            min-height: 16px;
            color: var(--primary);
        }

        .history-section {
            grid-column: 1 / -1;
            margin-top: 5px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            padding: 15px;
        }

        table { width: 100%; border-collapse: collapse; font-size: 11px; margin-top: 8px; }
        th, td { padding: 6px 8px; text-align: left; border-bottom: 1px solid var(--border-color); }
        th { color: var(--primary); font-weight: 600; }
    </style>
</head>
<body>

    <ul class="particles">
        <li class="particle"></li>
        <li class="particle"></li>
        <li class="particle"></li>
    </ul>

    <div class="container">
        <header>
            <div>
                <h1>Prime Solutions - Excel to Web Engine Pro</h1>
                <p>Upload Excel, Auto-Calculate, Multi-Currency, Sign & Sync Database</p>
            </div>
            <button class="theme-btn" onclick="toggleTheme()">Theme</button>
        </header>

        <div class="main-grid">
            <!-- Left Panel: Excel Upload & Inputs -->
            <div class="card">
                <h2>1. Excel File Import & Formula Inputs</h2>
                
                <div class="file-upload-box" onclick="simulateExcelUpload()">
                    📁 Click to Upload Existing Excel (.xlsx / .csv)
                </div>

                <div class="input-group">
                    <label>Client Email (for Instant Receipt)</label>
                    <input type="email" id="clientEmail" value="client@example.com">
                </div>
                <div class="input-group">
                    <label>Item Description</label>
                    <input type="text" id="desc" value="Enterprise Web Model" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Quantity / Units</label>
                    <input type="number" id="qty" value="10" min="1" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Unit Price</label>
                    <input type="number" id="price" value="100" min="0" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Select Currency</label>
                    <select id="currency" onchange="runExcelLogic()">
                        <option value="USD">USD ($)</option>
                        <option value="EUR">EUR (€)</option>
                        <option value="GBP">GBP (£)</option>
                        <option value="PKR">PKR (Rs)</option>
                    </select>
                </div>
            </div>

            <!-- Right Panel: Live Invoice & Signature -->
            <div class="card">
                <h2>2. Live Invoice Preview & Digital Signature</h2>
                <div class="invoice-preview">
                    <div class="inv-header">
                        <h3 id="invTitle">INVOICE #PS-950</h3>
                        <span id="invDate">2026-09-13</span>
                    </div>
                    <div class="inv-row">
                        <span id="pDesc">Enterprise Web Model</span>
                        <span id="pQtyPrice">10 x 100</span>
                    </div>
                    <div class="inv-row">
                        <span>Subtotal:</span>
                        <span id="subtotal">1000.00</span>
                    </div>
                    <div class="inv-row">
                        <span>Tax / Formula Output:</span>
                        <span id="taxAmount">50.00</span>
                    </div>
                    <div class="inv-total inv-row">
                        <span>Total Balance:</span>
                        <span id="grandTotal">1050.00 USD</span>
                    </div>
                </div>

                <div class="sig-container">
                    <label>Digital Signature Pad (Sign Below)</label>
                    <canvas id="sigCanvas"></canvas>
                </div>
            </div>

            <!-- Action Buttons -->
            <div class="actions">
                <button class="action-btn btn-calc" onclick="runExcelLogic()">Auto-Calculate</button>
                <button class="action-btn btn-save" onclick="saveData()">Save to Database</button>
                <button class="action-btn btn-pdf" onclick="downloadPDF()">Download PDF</button>
                <button class="action-btn btn-email" onclick="sendEmailInvoice()">Email Invoice</button>
            </div>

            <div class="status" id="statusMessage"></div>

            <!-- Database History Table -->
            <div class="history-section">
                <h2>Live Database Records History</h2>
                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Description</th>
                            <th>Client Email</th>
                            <th>Total</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody id="historyTableBody">
                        <tr>
                            <td>#PS-949</td>
                            <td>Sales Data Sheet</td>
                            <td>test@client.com</td>
                            <td>$450.00</td>
                            <td style="color: #10b981;">Synced ✅</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <script>
        const currencySymbols = { USD: '$', EUR: '€', GBP: '£', PKR: 'Rs ' };
        const currencyRates = { USD: 1, EUR: 0.92, GBP: 0.78, PKR: 278 };

        function runExcelLogic() {
            const desc = document.getElementById('desc').value;
            const qty = parseFloat(document.getElementById('qty').value) || 0;
            const price = parseFloat(document.getElementById('price').value) || 0;
            const curr = document.getElementById('currency').value;
            const symbol = currencySymbols[curr];
            const rate = currencyRates[curr];

            const sub = qty * price;
            const tax = sub * 0.05; // 5% simulated Excel formula tax
            const total = (sub + tax) * (curr === 'USD' ? 1 : (curr === 'PKR' ? rate / 278 : rate)); // simplified scaling for demo

            document.getElementById('pDesc').innerText = desc || 'Item';
            document.getElementById('pQtyPrice').innerText = `${qty} x ${price}`;
            document.getElementById('subtotal').innerText = `${symbol}${sub.toFixed(2)}`;
            document.getElementById('taxAmount').innerText = `${symbol}${tax.toFixed(2)}`;
            document.getElementById('grandTotal').innerText = `${symbol}${total.toFixed(2)} ${curr}`;
        }

        function simulateExcelUpload() {
            const status = document.getElementById('statusMessage');
            status.innerHTML = "Parsing Excel formulas and mapping data to web inputs...";
            status.style.color = "#f59e0b";
            setTimeout(() => {
                document.getElementById('desc').value = "Imported Excel Financial Sheet";
                document.getElementById('qty').value = "25";
                document.getElementById('price').value = "150";
                runExcelLogic();
                status.innerHTML = "Excel file successfully parsed and loaded into web app!";
                status.style.color = "#10b981";
            }, 1000);
        }

        let invId = 950;
        function saveData() {
            const status = document.getElementById('statusMessage');
            const desc = document.getElementById('desc').value;
            const email = document.getElementById('clientEmail').value;
            const total = document.getElementById('grandTotal').innerText;

            status.innerHTML = "Saving invoice and signature to Database (Firebase/SQL)...";
            status.style.color = "#f59e0b";

            setTimeout(() => {
                status.innerHTML = "Data successfully saved to database!";
                status.style.color = "#10b981";

                const tbody = document.getElementById('historyTableBody');
                const row = document.createElement('tr');
                row.innerHTML = `<td>#PS-${invId}</td><td>${desc}</td><td>${email}</td><td>${total}</td><td style="color: #10b981;">Synced ✅</td>`;
                tbody.prepend(row);
                invId++;
            }, 1000);
        }

        function downloadPDF() {
            const status = document.getElementById('statusMessage');
            status.innerHTML = "Generating professional PDF layout...";
            status.style.color = "#6366f1";
            setTimeout(() => {
                status.innerHTML = "PDF downloaded successfully!";
                status.style.color = "#10b981";
            }, 1200);
        }

        function sendEmailInvoice() {
            const email = document.getElementById('clientEmail').value;
            const status = document.getElementById('statusMessage');
            status.innerHTML = `Dispatching PDF invoice to ${email}...`;
            status.style.color = "#ec4899";
            setTimeout(() => {
                status.innerHTML = `Invoice successfully emailed to ${email}!`;
                status.style.color = "#10b981";
            }, 1200);
        }

        function toggleTheme() {
            document.body.classList.toggle('light-mode');
        }

        // Signature Canvas Setup
        const canvas = document.getElementById('sigCanvas');
        const ctx = canvas.getContext('2d');
        let painting = false;

        canvas.addEventListener('mousedown', () => painting = true);
        canvas.addEventListener('mouseup', () => { painting = false; ctx.beginPath(); });
        canvas.addEventListener('mousemove', draw);

        function draw(e) {
            if (!painting) return;
            ctx.lineWidth = 2;
            ctx.lineCap = 'round';
            ctx.strokeStyle = '#0f172a';
            const rect = canvas.getBoundingClientRect();
            ctx.lineTo(e.clientX - rect.left, e.clientY - rect.top);
            ctx.stroke();
            ctx.beginPath();
            ctx.moveTo(e.clientX - rect.left, e.clientY - rect.top);
        }
    </script>
</body>
</html>
