<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>工單號碼查詢系統</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        label, input {
            display: block;
            margin: 10px 0;
        }
        input[type="text"] {
            padding: 10px;
            width: 300px;
        }
        #color-result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h2>工單號碼查詢系統</h2>
    <label for="workOrder">輸入工單號碼：</label>
    <input type="text" id="workOrder" placeholder="請輸入工單號碼" autofocus>

    <button onclick="searchColor()">查詢顏色</button>

    <div id="color-result"></div>

    <script>
        // 工單號碼與顏色的對應關係
        const workOrderData = {
            'J515-24050641': '白',
            'J515-24060591': '白',
            'J515-24050616': '金',
            'J515-24060590': '金',
            'J515-24050639': '藍',
            'J515-24050613': '白',
            'J515-24051104': '綠',
            'J515-24051106': '綠',
            'J515-24051105': '綠',
            'J515-24051111': '綠',
            'J515-24051112': '綠',
            'J515-24051114': '綠',
            'J515-24051113': '綠',
            'J515-24050643': '藍',
            'J515-24090143': '黃',
            'J515-24050606': '黃',
            'J515-24050626': '白',
            'J515-24050622': '白',
            'J515-24050602': '白',
            'J515-24050607': '金',
            'J515-24080409': '金',
            'J515-24060583': '金',
            'J515-24060582': '金',
            'J515-24080346': '綠',
            'J515-24050630': '藍',
            'J515-24060586': '黃',
            'J515-24090508': '黃',
            'J515-24050600': '白',
            'J515-24080408': '金',
            'J515-24090507': '金',
            'J515-24060579': '金',
            'J515-24060578': '金',
            'J515-24060580': '金',
            'J515-24090506': '金',
            'J515-24051107': '綠',
            'J515-24090502': '黃',
            'J515-24090509': '黃',
            'J515-24050587': '黃',
            'J515-24050590': '黃',
            'J515-24090144': '黃',
            'J515-24060584': '黃',
            'J515-24050594': '白',
            'J515-24050637': '白',
            'J515-24060581': '金',
            'J515-24060589': '金',
            'J515-24051110': '綠',
            'J515-24050595': '藍',
            'J515-24050611': '藍',
            'J515-24050632': '藍',
            'J515-24050615': '藍',
            'J515-24090146': '黃',
            'J515-24050614': '黃',
            'J515-24080407': '黃',
            'J515-24050574': '白',
            'J515-24090527': '白',
            'J515-24050644': '金',
            'J515-24090515': '黃',
            'J515-24050568': '白'
        };

        // 查詢顏色的函數
        function searchColor() {
            const workOrderInput = document.getElementById('workOrder');
            const resultDiv = document.getElementById('color-result');
            const workOrder = workOrderInput.value.trim();
            
            if (workOrder in workOrderData) {
                resultDiv.textContent = `工單號碼 ${workOrder} 的顏色是：${workOrderData[workOrder]}`;
            } else {
                resultDiv.textContent = `找不到工單號碼 ${workOrder} 的顏色`;
            }

            // 查詢完畢後，自動選取工單號碼欄位的內容
            workOrderInput.select();
        }

        // 按 Enter 鍵也能進行查詢
        document.getElementById('workOrder').addEventListener('keydown', function(event) {
            if (event.key === 'Enter') {
                searchColor();
            }
        });
    </script>

</body>
</html>
