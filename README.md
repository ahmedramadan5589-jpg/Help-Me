<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تسجيل الدخول أو إنشاء حساب</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>مرحباً بك في تطبيق بيانات الطوارئ</h1>

        <!-- تبويب لتبديل بين تسجيل الدخول وإنشاء حساب -->
        <div class="tabs">
            <button id="login-tab" class="active">تسجيل الدخول</button>
            <button id="signup-tab">إنشاء حساب</button>
        </div>

        <!-- نموذج تسجيل الدخول -->
        <form id="login-form" class="form">
            <label for="login-email">البريد الإلكتروني</label>
            <input type="email" id="login-email" name="email" required>

            <label for="login-password">كلمة السر</label>
            <input type="password" id="login-password" name="password" required>

            <button type="submit">تسجيل الدخول</button>
        </form>

        <!-- نموذج إنشاء حساب -->
        <form id="signup-form" class="form hidden">
            <label for="signup-name">الاسم الكامل</label>
            <input type="text" id="signup-name" name="name" required>

            <label for="signup-email">البريد الإلكتروني</label>
            <input type="email" id="signup-email" name="email" required>

            <label for="signup-password">كلمة السر</label>
            <input type="password" id="signup-password" name="password" required>

            <button type="submit">إنشاء حساب</button>
        </form>

    </div>

    <script src="script.js"></script>
</body>
</html>






* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    color: #333;
    padding: 20px;
}

.container {
    max-width: 400px;
    margin: 0 auto;
    background-color: #fff;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

h1 {
    text-align: center;
    margin-bottom: 20px;
    color: #007bff;
}

.tabs {
    display: flex;
    justify-content: space-around;
    margin-bottom: 20px;
}

button {
    background-color: #007bff;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

button.active {
    background-color: #28a745;
}

.form {
    display: flex;
    flex-direction: column;
}

label {
    margin: 10px 0 5px;
}

input {
    padding: 10px;
    font-size: 14px;
    margin-bottom: 20px;
    border-radius: 5px;
    border: 1px solid #ddd;
}

button[type="submit"] {
    background-color: #28a745;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button[type="submit"]:hover {
    background-color: #218838;
}

/* إخفاء النموذج الذي لا يتم استخدامه */
.hidden {
    display: none;
}






// الحصول على النماذج والأزرار
const loginForm = document.getElementById('login-form');
const signupForm = document.getElementById('signup-form');
const loginTab = document.getElementById('login-tab');
const signupTab = document.getElementById('signup-tab');

// عندما يتم النقر على تبويب "تسجيل الدخول"
loginTab.addEventListener('click', function() {
    loginTab.classList.add('active');
    signupTab.classList.remove('active');
    loginForm.classList.remove('hidden');
    signupForm.classList.add('hidden');
});

// عندما يتم النقر على تبويب "إنشاء حساب"
signupTab.addEventListener('click', function() {
    signupTab.classList.add('active');
    loginTab.classList.remove('active');
    signupForm.classList.remove('hidden');
    loginForm.classList.add('hidden');
});

// نموذج تسجيل الدخول
loginForm.addEventListener('submit', function(event) {
    event.preventDefault(); // منع إرسال النموذج بشكل افتراضي
    const email = document.getElementById('login-email').value;
    const password = document.getElementById('login-password').value;

    // هنا يمكن إضافة الكود لإرسال بيانات تسجيل الدخول إلى الخادم
    alert(`تسجيل الدخول باستخدام البريد الإلكتروني: ${email}`);
    // في النهاية إعادة تعيين الحقول
    loginForm.reset();
});

// نموذج إنشاء حساب
signupForm.addEventListener('submit', function(event) {
    event.preventDefault(); // منع إرسال النموذج بشكل افتراضي
    const name = document.getElementById('signup-name').value;
    const email = document.getElementById('signup-email').value;
    const password = document.getElementById('signup-password').value;

    // هنا يمكن إضافة الكود لإرسال بيانات إنشاء الحساب إلى الخادم
    alert(`إنشاء حساب جديد للمستخدم: ${name} باستخدام البريد الإلكتروني: ${email}`);
    // في النهاية إعادة تعيين الحقول
    signupForm.reset();
});









<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق البيانات الشخصية للطوارئ</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>إضافة بيانات العميل للطوارئ</h1>
        
        <!-- نموذج إضافة البيانات الشخصية -->
        <form id="personal-info-form">
            <label for="name">الاسم الكامل</label>
            <input type="text" id="name" name="name" required>

            <label for="country_of_origin">البلد الأم</label>
            <input type="text" id="country_of_origin" name="country_of_origin" required>

            <label for="destination_country">البلد المقصود</label>
            <input type="text" id="destination_country" name="destination_country" required>

            <label for="emergency_contact">رقم الطوارئ</label>
            <input type="tel" id="emergency_contact" name="emergency_contact" required>

            <label for="health_condition">الحالة الصحية</label>
            <textarea id="health_condition" name="health_condition" rows="3" required></textarea>

            <label for="medications">الأدوية التي وصفت له</label>
            <textarea id="medications" name="medications" rows="3" required></textarea>

            <label for="address">العنوان</label>
            <input type="text" id="address" name="address" required>

            <label for="barcode">صورة الباركود (اختياري)</label>
            <input type="file" id="barcode" name="barcode" accept="image/*">

            <button type="submit">حفظ البيانات</button>
        </form>

        <!-- عرض بيانات الطوارئ -->
        <h2>بيانات الطوارئ</h2>
        <div id="emergency-data">
            <!-- سيتم عرض بيانات الطوارئ هنا بعد الإضافة -->
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>






* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f9;
    color: #333;
    padding: 20px;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    background-color: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

h1, h2 {
    text-align: center;
    margin-bottom: 20px;
    color: #007bff;
}

form {
    display: flex;
    flex-direction: column;
}

label {
    margin: 10px 0 5px;
}

input, textarea {
    padding: 10px;
    font-size: 14px;
    margin-bottom: 20px;
    border-radius: 5px;
    border: 1px solid #ddd;
}

button {
    background-color: #28a745;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

#emergency-data {
    background-color: #f8f9fa;
    padding: 15px;
    border-radius: 8px;
    border: 1px solid #ddd;
}

#emergency-data p {
    margin-bottom: 10px;
}






// الحصول على نموذج البيانات
const form = document.getElementById('personal-info-form');

// عند إرسال النموذج
form.addEventListener('submit', function(event) {
    event.preventDefault(); // منع الإرسال التلقائي للنموذج

    // جمع البيانات من النموذج
    const name = document.getElementById('name').value;
    const countryOfOrigin = document.getElementById('country_of_origin').value;
    const destinationCountry = document.getElementById('destination_country').value;
    const emergencyContact = document.getElementById('emergency_contact').value;
    const healthCondition = document.getElementById('health_condition').value;
    const medications = document.getElementById('medications').value;
    const address = document.getElementById('address').value;
    const barcode = document.getElementById('barcode').files[0]; // الملف المرفق للباركود

    // إنشاء كود QR (يمكنك استخدام مكتبة لإنشاء QR، هنا فقط عرضها كصورة مباشرة)
    let barcodeUrl = '';
    if (barcode) {
        barcodeUrl = URL.createObjectURL(barcode);
    }

    // عرض البيانات في القسم المخصص للطوارئ
    const emergencyDataContainer = document.getElementById('emergency-data');
    emergencyDataContainer.innerHTML = `
        <h3>بيانات العميل للطوارئ:</h3>
        <p><strong>الاسم:</strong> ${name}</p>
        <p><strong>البلد الأم:</strong> ${countryOfOrigin}</p>
        <p><strong>البلد المقصود:</strong> ${destinationCountry}</p>
        <p><strong>رقم الطوارئ:</strong> ${emergencyContact}</p>
        <p><strong>الحالة الصحية:</strong> ${healthCondition}</p>
        <p><strong>الأدوية:</strong> ${medications}</p>
        <p><strong>العنوان:</strong> ${address}</p>
        ${barcodeUrl ? `<p><strong>صورة الباركود:</strong><img src="${barcodeUrl}" alt="Barcode Image" style="max-width: 100px; margin-top: 10px;"></p>` : ''}
    `;

    // إعادة تعيين النموذج بعد الإرسال
    form.reset();
});






