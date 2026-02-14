# oracle
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ดูดวง</title>

<style>
body { background: #0f0f1a; color: #d4af37; font-family: sans-serif; text-align: center; padding: 40px 20px; }

.card {
    width: 140px;
    height: 200px;
    border: 2px solid #d4af37;
    border-radius: 15px;
    margin: 20px auto;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
    background: #1a1a2e;
    transition: 0.5s;
    cursor: pointer;
    box-shadow: 0 0 20px rgba(212,175,55,0.3);
}

.res { margin-top: 20px; min-height: 120px; }

button {
    background: #d4af37;
    color: #1a1a2e;
    border: none;
    padding: 15px 35px;
    border-radius: 50px;
    font-weight: bold;
    cursor: pointer;
    font-size: 1.1rem;
}
</style>
</head>

<body>

<h1>THE ORACLE</h1>

<div id="card" class="card">🔮</div>
<div id="res" class="res"><h3>แตะที่ไพ่เพื่อดูดวง</h3></div>

<button id="btn">สุ่มคำทำนาย</button>

<script>
const db = [
{t:"การงานรุ่งโรจน์ มีคนคอยช่วย", j:"รุ่งจนงานงอกมาให้ทำเพิ่มไม่หยุดเลย"},
{t:"การเงินดี มีลาภลอยกะทันหัน", j:"ลาภลอยมาในรูปแบบของ ส่วนลดแอปส้ม"},
{t:"ความรักหวานชื่น คนโสดจะเจอคู่", j:"เจอคู่ในฝันนะ ชีวิตจริงรอก่อน"},
{t:"สุขภาพแข็งแรง แต่ระวังปวดหลัง", j:"เลิกนั่งท่าประหลาดดูมือถือได้แล้ว!"}
];

function draw() {
    const f = db[Math.floor(Math.random()*db.length)];
    const c = document.getElementById('card');

    c.style.transform = "rotateY(180deg)";
    c.innerText = "✨";

    document.getElementById('res').innerHTML = `
        <h2>${f.t}</h2>
        <p style="color:#888;">💡 ${f.j}</p>
    `;

    setTimeout(() => {
        c.style.transform = "rotateY(0deg)";
        c.innerText = "🔮";
    }, 3000);
}

/* ใช้ event listener */
document.getElementById("card").addEventListener("click", draw);
document.getElementById("btn").addEventListener("click", draw);

</script>

</body>
</html>
