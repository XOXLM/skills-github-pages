<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>حساب معدل الفصل الدراسي</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700&display=swap');* {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Tajawal', Arial, sans-serif;
        background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        min-height: 100vh;
        padding: 40px 20px;
    }

    .container {
        background: rgba(255, 255, 255, 0.95);
        padding: 30px;
        border-radius: 20px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        max-width: 900px;
        margin: auto;
    }

    h1 {
        text-align: center;
        color: #2c3e50;
        margin-bottom: 30px;
        font-size: 2.2em;
        position: relative;
        padding-bottom: 15px;
    }

    h1::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
        width: 100px;
        height: 3px;
        background: linear-gradient(90deg, #3498db, #2ecc71);
        border-radius: 3px;
    }

    .subjects-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 20px;
        margin-bottom: 30px;
    }

    .subject {
        background: #ffffff;
        padding: 20px;
        border-radius: 15px;
        box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        transition: transform 0.3s, box-shadow 0.3s;
    }

    .subject:hover {
        transform: translateY(-5px);
        box-shadow: 0 8px 20px rgba(0,0,0,0.1);
    }

    h3 {
        color: #2c3e50;
        margin-bottom: 15px;
        font-size: 1.1em;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    h3::before {
        content: '📚';
        font-size: 1.2em;
    }

    .input-group {
        display: flex;
        align-items: center;
        margin: 12px 0;
        gap: 10px;
    }

    .input-group label {
        min-width: 70px;
        font-weight: 500;
        color: #34495e;
    }

    .exam-input {
        flex: 1;
        padding: 10px;
        border: 2px solid #e0e0e0;
        border-radius: 8px;
        font-size: 1em;
        transition: all 0.3s;
        text-align: center;
    }

    .exam-input:focus {
        outline: none;
        border-color: #3498db;
        box-shadow: 0 0 0 3px rgba(52,152,219,0.2);
    }

    .td-input {
        border-color: #3498db;
        background-color: #f8f9fa;
    }

    button {
        background: linear-gradient(135deg, #3498db, #2980b9);
        color: white;
        padding: 15px 30px;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-size: 1.1em;
        font-weight: bold;
        width: 100%;
        transition: transform 0.3s, box-shadow 0.3s;
        margin: 20px 0;
    }

    button:hover {
        transform: translateY(-2px);
        box-shadow: 0 5px 15px rgba(52,152,219,0.4);
    }

    button:active {
        transform: translateY(0);
    }

    #result {
        font-size: 1.8em;
        padding: 20px;
        border-radius: 15px;
        text-align: center;
        margin-top: 20px;
        transition: all 0.3s;
        background: #f8f9fa;
    }

    .coefficient {
        font-size: 0.8em;
        color: #666;
        font-weight: normal;
    }

    @media (max-width: 600px) {
        .container {
            padding: 20px;
        }

        h1 {
            font-size: 1.8em;
        }

        .subjects-grid {
            grid-template-columns: 1fr;
        }
    }
</style>

</head>
<body>
    <div class="container">
        <h1>حساب معدل الفصل الدراسي</h1><div class="subjects-grid">
        <div class="subject">
            <h3>مدخل إلى القانون 1 <span class="coefficient">(معامل 2)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub1_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
            <div class="input-group">
                <label>TD:</label>
                <input type="number" id="sub1_td" step="0.1" class="exam-input td-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>

        <div class="subject">
            <h3>تنظيم قضائي 1 <span class="coefficient">(معامل 2)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub2_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
            <div class="input-group">
                <label>TD:</label>
                <input type="number" id="sub2_td" step="0.1" class="exam-input td-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>

        <div class="subject">
            <h3>قانون دستوري 1 <span class="coefficient">(معامل 1)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub3_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
            <div class="input-group">
                <label>TD:</label>
                <input type="number" id="sub3_td" step="0.1" class="exam-input td-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>

        <div class="subject">
            <h3>تاريخ النظم القانونية <span class="coefficient">(معامل 1)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub4_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>

        <div class="subject">
            <h3>لغة إنجليزية <span class="coefficient">(معامل 1)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub5_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>

        <div class="subject">
            <h3>منهجية العلوم القانونية 1 <span class="coefficient">(معامل 1)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub6_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>

        <div class="subject">
            <h3>المجتمع الدولي <span class="coefficient">(معامل 1)</span></h3>
            <div class="input-group">
                <label>EXAM:</label>
                <input type="number" id="sub7_exam" step="0.1" class="exam-input" placeholder="0-20" min="0" max="20">
            </div>
        </div>
    </div>

    <button onclick="calculate()">احسب المعدل الآن</button>
    <div id="result"></div>
</div>

<script>
    function calculate() {
        // المواد التي تحتوي على TD
        const sub1 = ((getValue('sub1_exam') + getValue('sub1_td')) / 2) * 2;
        const sub2 = ((getValue('sub2_exam') + getValue('sub2_td')) / 2) * 2;
        const sub3 = ((getValue('sub3_exam') + getValue('sub3_td')) / 2) * 1;

        // المواد بدون TD
        const sub4 = getValue('sub4_exam') * 1;
        const sub5 = getValue('sub5_exam') * 1;
        const sub6 = getValue('sub6_exam') * 1;
        const sub7 = getValue('sub7_exam') * 1;

        const total = sub1 + sub2 + sub3 + sub4 + sub5 + sub6 + sub7;
        const totalCoefficient = 9;
        
        const average = total / totalCoefficient;
        
        showResult(average);
    }

    function getValue(id) {
        const value = parseFloat(document.getElementById(id).value);
        return isNaN(value) ? 0 : Math.min(Math.max(value, 0), 20);
    }

    function showResult(average) {
        const resultDiv = document.getElementById('result');
        const isPass = average >= 10;
        
        resultDiv.innerHTML = `
            <strong>معدل الفصل:</strong> 
            ${average.toFixed(2)} 
            ${isPass ? '🎉 مبروك النجاح!' : '❌ للأسف لم تنجح'}
        `;
        
        resultDiv.style.background = isPass ? 
            'linear-gradient(135deg, #d4fc79 0%, #96e6a1 100%)' : 
            'linear-gradient(135deg, #f6d365 0%, #fda085 100%)';
        
        resultDiv.style.color = '#2c3e50';
        resultDiv.style.boxShadow = '0 5px 15px rgba(0,0,0,0.1)';
    }

    // إضافة مؤثرات حركية للحقول
    document.querySelectorAll('.exam-input').forEach(input => {
        input.addEventListener('focus', function() {
            this.parentElement.parentElement.style.transform = 'scale(1.02)';
        });
        
        input.addEventListener('blur', function() {
            this.parentElement.parentElement.style.transform = 'scale(1)';
        });
    });
</script>

</body>
</html>
