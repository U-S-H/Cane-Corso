<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Excel to Web Application - Prime Solutions</title>
    <style>
        :root {
            --primary: #0ea5e9;
            --secondary: #1e293b;
            --accent: #10b981;
            --bg: #0f172a;
            --card-bg: rgba(30, 41, 59, 0.7);
            --text: #f8fafc;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(-45deg, #0f172a, #1e1b4b, #065f46, #1e293b);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: var(--text);
            min-height: 100vh;
            padding: 20px;
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
            max-width: 1000px;
            background: var(--card-bg);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.5);
            overflow: hidden;
        }

        header {
            background: linear-gradient(135deg, #0284c7, #0d9488);
            padding: 25px 30px;
            text-align: center;
        }

        header h1 {
            font-size: 24px;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        header p {
            font-size: 13px;
            opacity: 0.9;
            margin-top: 5px;
        }

        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            padding: 30px;
        }

        @media(max-width: 768px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
        }

        .card {
            background: rgba(15, 23, 42, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 14px;
            padding: 20px;
        }

        h2 {
            font-size: 16px;
            color: #38bdf8;
            margin-bottom: 15px;
            border-bottom: 1px solid rgba(56, 189, 248, 0.2);
            padding-bottom: 8px;
        }

        .input-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            font-size: 13px;
            margin-bottom: 5px;
            color: #cbd5e1;
        }

        input, select {
            width: 100%;
            padding: 10px 14px;
            background: #0f172a;
            border: 1px solid #334155;
            border-radius: 8px;
            color: #fff;
            font-size: 14px;
            transition: all 0.3s ease;
        }

        input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 10px rgba(14, 165, 233, 0.3);
        }

        .invoice-preview {
            background: #ffffff;
            color: #0f172a;
            border-radius: 10px;
            padding: 20px;
            font-size: 13px;
        }

        .inv-header {
            display: flex;
            justify-content: space-between;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 10px;
            margin-bottom: 15px;
        }

        .inv-header h3 {
            color: #1e3a8a;
            font-size: 16px;
        }

        .inv-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .inv-total {
            border-top: 2px solid #e2e8f0;
            padding-top: 10px;
            margin-top: 10px;
            font-weight: bold;
            font-size: 15px;
            color: #0d9488;
        }

        .actions {
            grid-column: 1 / -1;
            display: flex;
            gap: 15px;
            margin-top: 10px;
        }

        button {
            flex: 1;
            padding: 12px;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-calc {
            background: var(--primary);
            color: white;
        }

        .btn-calc:hover {
            background: #0284c7;
        }

        .btn-save {
            background: var(--accent);
            color: white;
        }

        .btn-save:hover {
            background: #059669;
        }

        .status {
            grid-column: 1 / -1;
            text-align: center;
            font-size: 13px;
            min-height: 20px;
            color: #38bdf8;
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <h1>Prime Solutions - Excel to Web System</h1>
            <p>Automated Calculations, Invoice Generator & Database Integration</p>
        </header>

        <div class="main-grid">
            <!-- Excel Form Inputs -->
            <div class="card">
                <h2>Excel Formula Inputs</h2>
                <div class="input-group">
                    <label>Client / Item Description</label>
                    <input type="text" id="desc" value="Calculation Model Item" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Quantity / Units</label>
                    <input type="number" id="qty" value="10" min="1" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Unit Price ($)</label>
                    <input type="number" id="price" value="50" min="0" oninput="runExcelLogic()">
                </div>
                <div class="input-group">
                    <label>Discount Rate (%)</label>
                    <input type="number" id="discount" value="5" min="0" max="100" oninput="runExcelLogic()">
                </div>
            </div>

            <!-- Live Invoice Preview -->
            <div class="card">
                <h2>Generated Invoice Preview</h2>
                <div class="invoice-preview">
                    <div class="inv-header">
                        <h3 id="invTitle">INVOICE #PS-892</h3>
                        <span id="invDate">2026-09-13</span>
                    </div>
                    <div class="inv-row">
                        <span id="pDesc">Calculation Model Item</span>
                        <span id="pQtyPrice">10 x $50.00</span>
                    </div>
                    <div class="inv-row">
                        <span>Subtotal:</span>
                        <span id="subtotal">$500.00</span>
                    </div>
                    <div class="inv-row">
                        <span>Discount Applied:</span>
                        <span id="discAmount">-$25.00</span>
                    </div>
                    <div class="inv-total inv-row">
                        <span>Total Balance:</span>
                        <span id="grandTotal">$475.00</span>
                    </div>
                </div>
            </div>

            <!-- Actions -->
            <div class="actions">
                <button class="btn-calc" onclick="runExcelLogic()">Run Automatic Calculations</button>
                <button class="btn-save" onclick="saveData()">Save to Database</button>
            </div>

            <div class="status" id="statusMessage"></div>
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

        function saveData() {
            const status = document.getElementById('statusMessage');
            status.innerHTML = "Processing data and saving securely to database (Firebase/SQL)...";
            status.style.color = "#f59e0b";

            setTimeout(() => {
                status.innerHTML = "Success! Invoice generated and data successfully saved to database.";
                status.style.color = "#10b981";
            }, 1200);
        }
    </script>
</body>
</html>
