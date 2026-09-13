<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prime Solutions - App Demo</title>
    <style>
        :root {
            --bg-gradient: linear-gradient(-45deg, #0f172a, #1e1b4b, #065f46, #1e293b);
            --card-bg: rgba(30, 41, 59, 0.82);
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
            --card-bg: rgba(255, 255, 255, 0.9);
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

        /* Splash Screen / App Loading */
        #splash-screen {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: #0f172a;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            color: #fff;
            transition: opacity 0.5s ease;
        }

        .app-logo-icon {
            font-size: 50px;
            margin-bottom: 15px;
            animation: bounce 1.5s infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        #splash-screen h1 { font-size: 22px; font-weight: 700; color: #38bdf8; margin-bottom: 5px; }
        #splash-screen p { font-size: 13px; opacity: 0.8; margin-bottom: 20px; }

        .loader-bar {
            width: 200px;
            height: 4px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            overflow: hidden;
        }

        .loader-progress {
            width: 0%;
            height: 100%;
            background: #0ea5e9;
            animation: loadProgress 1.8s forwards;
        }

        @keyframes loadProgress {
            0% { width: 0%; }
            100% { width: 100%; }
        }

        body {
            background: var(--bg-gradient);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: var(--text-color);
            min-height: 100vh;
            padding: 15px 15px 70px 15px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            width: 100%;
            max-width: 950px;
            background: var(--card-bg);
            backdrop-filter: blur(16px);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.35);
            overflow: hidden;
            margin-bottom: 20px;
        }

        header {
            background: linear-gradient(135deg, #0284c7, #0d9488);
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #fff;
        }

        .app-title-area { display: flex; align-items: center; gap: 10px; }
        .app-icon { font-size: 24px; }
        header h1 { font-size: 18px; font-weight: 700; }
        header p { font-size: 11px; opacity: 0.9; }

        .theme-btn {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            padding: 6px 12px;
            border-radius: 8px;
            color: #fff;
            cursor: pointer;
            font-weight: 600;
            font-size: 12px;
        }
        .theme-btn:hover { background: rgba(255, 255, 255, 0.3); }

        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            padding: 20px;
        }

        @media(max-width: 768px) {
            .main-grid { grid-template-columns: 1fr; }
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 15px;
        }

        h2 {
            font-size: 13px;
            color: var(--primary);
            margin-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 5px;
        }

        .input-group { margin-bottom: 8px; }
        label { display: block; font-size: 11px; margin-bottom: 2px; opacity: 0.9; }
        input, select {
            width: 100%;
            padding: 7px 10px;
            background: var(--input-bg);
            border: 1px solid var(--input-border);
            border-radius: 8px;
            color: var(--text-color);
            font-size: 12px;
        }

        .file-upload-box {
            border: 2px dashed var(--primary);
            padding: 10px;
            text-align: center;
            border-radius: 8px;
            cursor: pointer;
            font-size: 11px;
            margin-bottom: 10px;
            background: rgba(14, 165, 233, 0.05);
        }

        .invoice-preview {
            background: #ffffff;
            color: #0f172a;
            border-radius: 8px;
            padding: 12px;
            font-size: 11px;
        }

        .inv-header {
            display: flex;
            justify-content: space-between;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 5px;
            margin-bottom: 8px;
        }
        .inv-header h3 { color: #1e3a8a; font-size: 13px; }

        .inv-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 4px;
        }

        .inv-total {
            border-top: 2px solid #e2e8f0;
            padding-top: 5px;
            margin-top: 5px;
            font-weight: bold;
            font-size: 12px;
            color: #0d9488;
        }

        .sig-container { margin-top: 8px; }
        canvas#sigCanvas {
            width: 100%;
            height: 45px;
            background: #ffffff;
            border: 1px solid var(--input-border);
            border-radius: 6px;
            cursor: crosshair;
        }

        .actions {
            grid-column: 1 / -1;
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
        }

        button.action-btn {
            flex: 1;
            padding: 9px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            font-size: 11px;
            cursor: pointer;
        }

        .btn-calc { background: var(--primary); color: white; }
        .btn-save { background: var(--accent); color: white; }
        .btn-pdf { background: #6366f1; color: white; }
        .btn-email { background: #ec4899; color: white; }

        .status {
            grid-column: 1 / -1;
            text-align: center;
            font-size: 11px;
            min-height: 15px;
            color: var(--primary);
        }

        .history-section {
            grid-column: 1 / -1;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 12px;
        }

        table { width: 100%; border-collapse: collapse; font-size: 11px; margin-top: 6px; }
        th, td { padding: 5px 6px; text-align: left; border-bottom: 1px solid var(--border-color); }
        th { color: var(--primary); font-weight: 600; }

        /* Mobile App Bottom Navigation Bar */
        .bottom-nav {
            position: fixed;
            bottom: 0; left: 0; width: 100%;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
            z-index: 1000;
        }

        .nav-item {
            text-align: center;
            color: #94a3b8;
            font-size: 10px;
            cursor: pointer;
            text-decoration: none;
        }

        .nav-item span { display: block; font-size: 16px; margin-bottom: 2px; }
        .nav-item.active { color: #38bdf8; }
    </style>
</head>
<body>

    <!-- Splash Screen / App Loading Simulator -->
    <div id="splash-screen">
        <div class="app-logo-icon">📊</div>
        <h1>Prime Solutions</h1>
        <p>Welcome to Excel-to-Web Mobile App Engine</p>
        <div class="loader-bar">
            <div class="loader-progress"></div>
        </div>
    </div>

    <div class="container">
        <header>
            <div class="app-title-area">
                <span class="app-icon">⚡</span>
                <div>
                    <h1>Prime Solutions App</h1>
                    <p>Excel to Web & Database Hub</p>
                </div>
            </div>
            <button class="theme-btn" onclick="toggleTheme()">Theme</button>
        </header>

        <div class="main-grid">
            <!-- Left Panel: Excel & Inputs -->
            <div class="card">
                <h2>📱 1. Excel File & Inputs</h2>
                
                <div class="file-upload-box" onclick="simulateExcelUpload()">
                    📂 Tap to Import Excel (.xlsx / .csv)
                </div>

                <div class="input-group">
                    <label>Client Email</label>
                    <input type="email" id="clientEmail" value="user@client.com">
                </div>
                <div class="input-group">
                    <label>Item Description</label>
                    <input type="text" id="desc" value="Calculation Web Model" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Quantity</label>
                    <input type="number" id="qty" value="8" min="1" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Unit Price</label>
                    <input type="number" id="price" value="75" min="0" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Currency</label>
                    <select id="currency" onchange="runExcelLogic()">
                        <option value="USD">USD ($)</option>
                        <option value="EUR">EUR (€)</option>
                        <option value="GBP">GBP (£)</option>
                        <option value="PKR">PKR (Rs)</option>
                    </select>
                </div>
            </div>

            <!-- Right Panel: Invoice & Signature -->
            <div class="card">
                <h2>🧾 2. Live Invoice & Signature</h2>
                <div class="invoice-preview">
                    <div class="inv-header">
                        <h3 id="invTitle">INVOICE #APP-101</h3>
                        <span id="invDate">2026-09-13</span>
                    </div>
                    <div class="inv-row">
                        <span id="pDesc">Calculation Web Model</span>
                        <span id="pQtyPrice">8 x 75</span>
                    </div>
                    <div class="inv-row">
                        <span>Subtotal:</span>
                        <span id="subtotal">600.00</span>
                    </div>
                    <div class="inv-row">
                        <span>Tax / Formula:</span>
                        <span id="taxAmount">30.00</span>
                    </div>
                    <div class="inv-total inv-row">
                        <span>Total:</span>
                        <span id="grandTotal">630.00 USD</span>
                    </div>
                </div>

                <div class="sig-container">
                    <label>App Signature Pad</label>
                    <canvas id="sigCanvas"></canvas>
                </div>
            </div>

            <!-- Action Buttons -->
            <div class="actions">
                <button class="action-btn btn-calc" onclick="runExcelLogic()">Calculate</button>
                <button class="action-btn btn-save" onclick="saveData()">Save DB</button>
                <button class="action-btn btn-pdf" onclick="downloadPDF()">Get PDF</button>
                <button class="action-btn btn-email" onclick="sendEmailInvoice()">Email</button>
            </div>

            <div class="status" id="statusMessage"></div>

            <!-- History Table -->
            <div class="history-section">
                <h2>💾 Database Records</h2>
                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Description</th>
                            <th>Total</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody id="historyTableBody">
                        <tr>
                            <td>#APP-100</td>
                            <td>Financial Sheet</td>
                            <td>$350.00</td>
                            <td style="color: #10b981;">Synced ✅</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- Mobile App Bottom Navigation Bar -->
    <div class="bottom-nav">
        <div class="nav-item active">
            <span>🏠</span>Home
        </div>
        <div class="nav-item" onclick="simulateExcelUpload()">
            <span>📁</span>Import
        </div>
        <div class="nav-item" onclick="saveData()">
            <span>☁️</span>Sync DB
        </div>
        <div class="nav-item" onclick="toggleTheme()">
            <span>⚙️</span>Theme
        </div>
    </div>

    <script>
        // Hide Splash Screen after loading
        window.addEventListener('load', () => {
            setTimeout(() => {
                const splash = document.getElementById('splash-screen');
                splash.style.opacity = '0';
                setTimeout(() => splash.style.display = 'none', 500);
            }, 1800);
        });

        const currencySymbols = { USD: '$', EUR: '€', GBP: '£', PKR: 'Rs ' };

        function runExcelLogic() {
            const desc = document.getElementById('desc').value;
            const qty = parseFloat(document.getElementById('qty').value) || 0;
            const price = parseFloat(document.getElementById('price').value) || 0;
            const curr = document.getElementById('currency').value;
            const symbol = currencySymbols[curr];

            const sub = qty * price;
            const tax = sub * 0.05;
            const total = sub + tax;

            document.getElementById('pDesc').innerText = desc || 'Item';
            document.getElementById('pQtyPrice').innerText = `${qty} x ${price}`;
            document.getElementById('subtotal').innerText = `${symbol}${sub.toFixed(2)}`;
            document.getElementById('taxAmount').innerText = `${symbol}${tax.toFixed(2)}`;
            document.getElementById('grandTotal').innerText = `${symbol}${total.toFixed(2)} ${curr}`;
        }

        function simulateExcelUpload() {
            const status = document.getElementById('statusMessage');
            status.innerHTML = "Parsing Excel formulas into app...";
            status.style.color = "#f59e0b";
            setTimeout(() => {
                document.getElementById('desc').value = "Mobile Uploaded Excel Sheet";
                document.getElementById('qty').value = "15";
                document.getElementById('price').value = "120";
                runExcelLogic();
                status.innerHTML = "Excel sheet loaded successfully!";
                status.style.color = "#10b981";
            }, 900);
        }

        let appId = 101;
        function saveData() {
            const status = document.getElementById('statusMessage');
            const desc = document.getElementById('desc').value;
            const total = document.getElementById('grandTotal').innerText;

            status.innerHTML = "Saving record to App Database...";
            status.style.color = "#f59e0b";

            setTimeout(() => {
                status.innerHTML = "Successfully saved to Database!";
                status.style.color = "#10b981";

                const tbody = document.getElementById('historyTableBody');
                const row = document.createElement('tr');
                row.innerHTML = `<td>#APP-${appId}</td><td>${desc}</td><td>${total}</td><td style="color: #10b981;">Synced ✅</td>`;
                tbody.prepend(row);
                appId++;
            }, 800);
        }

        function downloadPDF() {
            const status = document.getElementById('statusMessage');
            status.innerHTML = "Generating PDF receipt...";
            status.style.color = "#6366f1";
            setTimeout(() => {
                status.innerHTML = "PDF downloaded successfully!";
                status.style.color = "#10b981";
            }, 1000);
        }

        function sendEmailInvoice() {
            const email = document.getElementById('clientEmail').value;
            const status = document.getElementById('statusMessage');
            status.innerHTML = `Emailing invoice to ${email}...`;
            status.style.color = "#ec4899";
            setTimeout(() => {
                status.innerHTML = `Invoice sent to ${email}!`;
                status.style.color = "#10b981";
            }, 1000);
        }

        function toggleTheme() {
            document.body.classList.toggle('light-mode');
        }

        // Signature Canvas
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
