<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>صفحة تفاعلية ذكية</title>
<style>
  body {
    text-align:center; 
    font-family:sans-serif; 
    padding:50px; 
    transition: background 1s;
  }
  h1 {
    font-size:3em; 
    transition: transform 0.5s, color 0.5s;
  }
  button { 
    padding:15px 30px; 
    font-size:18px; 
    cursor:pointer; 
    margin-top:20px;
    border:none;
    border-radius:8px;
    background-color:#333;
    color:white;
    transition: background 0.3s;
  }
  button:hover {
    background-color:#555;
  }
</style>
</head>
<body>

<h1 id="welcome">مرحبا بك!</h1>
<p>اضغط الزر لتغيير الخلفية والنصوص بطريقة ممتعة 🎨</p>
<button onclick="changeColor()">اضغطني</button>
<p>عدد مرات الضغط: <span id="counter">0</span></p>

<script>
let count = 0;
const messages = [
  "أهلاً!",
  "مرحبا!",
  "صباح الخير!",
  "مساء الخير!",
  "تحية لك!",
  "استمتع بوقتك!",
  "اليوم يوم جميل!",
  "ابتسم 😊"
];

function getRandomColor() {
  // يعطي لون عشوائي جميل
  const hue = Math.floor(Math.random() * 360);
  return `hsl(${hue}, 70%, 60%)`;
}

function changeColor() {
  // تغيير لون الخلفية تدريجياً
  document.body.style.background = getRandomColor();
  
  // تغيير النص
  const msg = messages[Math.floor(Math.random() * messages.length)];
  const welcome = document.getElementById("welcome");
  welcome.innerText = msg;

  // حركة صغيرة للنص
  welcome.style.transform = `rotate(${Math.floor(Math.random()*20-10)}deg) scale(${1 + Math.random()*0.2})`;
  welcome.style.color = getRandomColor();

  // تحديث العداد
  count++;
  document.getElementById("counter").innerText = count;
}

// تغيير النص تلقائياً كل 5 ثواني
setInterval(() => {
  const welcome = document.getElementById("welcome");
  welcome.innerText = messages[Math.floor(Math.random()*messages.length)];
  welcome.style.color = getRandomColor();
  welcome.style.transform = `rotate(${Math.floor(Math.random()*20-10)}deg) scale(${1 + Math.random()*0.2})`;
}, 5000);

</script>
</body>
</html>
