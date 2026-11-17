
<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>A Letter For You 🤍</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300;400&family=Playfair+Display:ital,wght@0,400;0,500;1,400&display=swap');

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background: #f8f5ef;
  color: #514438;
  font-family: 'Kanit', sans-serif;
  font-weight: 300;
}

/* PASSWORD */

#lockScreen {
  position: fixed;
  inset: 0;
  z-index: 10;
  background: #f8f5ef;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
}

.lock-card {
  background: #fffdf9;
  width: 100%;
  max-width: 350px;
  padding: 40px 25px;
  text-align: center;
  border: 1px solid #e9e0d4;
}

.lock-card h1 {
  font-family: 'Playfair Display', serif;
  font-size: 30px;
  font-weight: 400;
}

.lock-card p {
  color: #a39485;
  font-size: 13px;
}

input {
  width: 100%;
  padding: 14px;
  margin: 20px 0;
  background: #faf8f3;
  border: 1px solid #e9e0d4;
  text-align: center;
  font-size: 18px;
  outline: none;
}

button {
  cursor: pointer;
  font-family: inherit;
}

.main-btn {
  background: #8b7560;
  color: white;
  border: none;
  padding: 13px;
  width: 100%;
  letter-spacing: 1px;
}

#error {
  color: #b66a60;
  font-size: 13px;
  min-height: 20px;
}

/* MAIN */

#website {
  display: none;
  animation: fade 1s ease;
}

@keyframes fade 
  from { opacity: 0; }
  to { opacity: 1; }
}

header {
  text-align: center;
  padding: 30px;
  font-family: 'Playfair Display', serif;
  letter-spacing: 3px;
  font-size: 13px;
  color: #8b7560;
}

.hero {
  min-height: 85vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 20px;
}

.subtitle {
  font-family: 'Playfair Display', serif;
  font-style: italic;
  color: #a99a89;
}

.hero h1 {
  font-family: 'Playfair Display', serif;
  font-weight: 400;
  font-size: clamp(30px, 7vw, 45px);
  margin: 12px 0;
}

.envelope {
  position: relative;
  width: min(300px, 85vw);
  height: 190px;
  background: #e6d9c9;
  margin: 80px auto 35px;
  box-shadow: 0 15px 35px #76604a20;
  cursor: pointer;
  perspective: 800px;
}

.envelope-back {
  position: absolute;
  inset: 0;
  background: #e8ddcf;
}

.envelope-front {
  position: absolute;
  inset: 0;
  background: #f0e5d8;
  clip-path: polygon(0 0, 50% 65%, 100% 0, 100% 100%, 0 100%);
  z-index: 3;
}

.flap {
  position: absolute;
  inset: 0;
  background: #d9c9b5;
  clip-path: polygon(0 0, 100% 0, 50% 68%);
  transform-origin: top;
  transition: transform .8s ease;
  z-index: 4;
}

.seal {
  position: absolute;
  top: 75px;
  left: 50%;
  transform: translateX(-50%);
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: #a58b71;
  color: white;
  display: grid;
  place-items: center;
  z-index: 5;
  font-size: 20px;
  transition: .4s;
}

.letter {
  position: absolute;
  width: 88%;
  height: 170px;
  left: 6%;
  bottom: 5px;
  background: #fffdf9;
  padding: 15px;
  z-index: 2;
  transition: transform 1s ease;
  opacity: 0;
  font-family: 'Playfair Display', serif;
}

.envelope.open .flap {
  transform: rotateX(180deg);
  z-index: 1;
}

.envelope.open .seal {
  opacity: 0;
}

.envelope.open .letter {
  opacity: 1;
  transform: translateY(-140px);
}

.hint {
  font-size: 13px;
  color: #a39485;
  letter-spacing: 1px;
}

/* LOVE LETTER */

#letterSection {
  display: none;
  max-width: 650px;
  margin: auto;
  padding: 25px;
  animation: fade 1s ease;
}

.paper {
  background: #fffdf9;
  padding: clamp(25px, 7vw, 60px);
  border: 1px solid #e9e0d4;
  box-shadow: 0 10px 30px #76604a0c;
  line-height: 2.1;
}

.paper h2 {
  font-family: 'Playfair Display', serif;
  font-weight: 400;
  text-align: center;
  font-size: 28px;
}

.paper p {
  white-space: pre-line;
}

.signature {
  text-align: right;
  margin-top: 40px;
  font-family: 'Playfair Display', serif;
  font-style: italic;
}

footer {
  text-align: center;
  padding: 40px 20px;
  color: #a39485;
  font-family: 'Playfair Display', serif;
  font-style: italic;
}

@media(max-width:480px) {
  .envelope {
    height: 170px;
  }

  .envelope.open .letter {
    transform: translateY(-125px);
  }
}
</style>
</head>

<body>

<!-- PASSWORD PAGE -->

<div id="lockScreen">

  <div class="lock-card">

    <div style="font-size:40px">✉</div>

    <p>A LITTLE SURPRISE FOR YOU</p>

    <h1>For Someone Special</h1>

    <p>มีจดหมายฉบับหนึ่งรออยู่นะ</p>

    <input
      type="password"
      id="password"
      placeholder="Enter password"
      onkeydown="if(event.key==='Enter') unlock()"
    >

    <button class="main-btn" onclick="unlock()">
      OPEN MY LETTER
    </button>

    <div id="error"></div>

  </div>

</div>

<!-- MAIN WEBSITE -->

<div id="website">

  <header>
    A LETTER FOR YOU
  </header>

  <section class="hero">

    <div class="subtitle">
      A little something from my heart
    </div>

    <h1>To My Favorite Person</h1>

    <p>ถึงวรเมธ ♡</p>

    <!-- ENVELOPE -->

    <div class="envelope"
         id="envelope"
         onclick="openEnvelope()">

      <div class="envelope-back"></div>

      <div class="letter">
        <h3>Dear You,</h3>
        <p>There is something I want to tell you...</p>
        <p>♡</p>
      </div>

      <div class="flap"></div>

      <div class="envelope-front"></div>

      <div class="seal">♡</div>

    </div>

    <div class="hint" id="hint">
      CLICK TO OPEN THE LETTER
    </div>

  </section>

  <!-- LETTER CONTENT -->

  <section id="letterSection">

    <div class="paper">

      <h2>Dear My Love,</h2>

      <p>
ถึงวรเมธคนดีของพี่
อาจจะงงว่าทำไมต้องมาอ่านอะไรแบบนี้
พี่ก็ไม่รู้ว่าทำทำไม อยากให้อ่านเฉยๆ
อยากให้รู้ว่าจริงใจเสมอ นี่55555
 คือว่า..มีเรื่องจะบอกก็คืออ คิดถึง แค่นี้แหละ
หยอกก เหนื่อยอยู่ล่ะสิใช้มั้ยล้าา 
เหนื่อยก็พักไม่รักก็พอ เห้ยย!! ไม่ใช่ๆ
อย่าพึ่งท้อนะ แล้วก็อย่าคิดเยอะ 
ดูแลลตัวเองดีๆ ฉู้ๆๆ รู้ว่าอยากกลับบ้านแล้ว
อดทนอีกนิดนึงนะ🫰🏻
แล้วก็ๆๆ ขอให้หายปวดหลัง
ถึงจะดูเป็นไปได้ก็เถอะ5555
อย่าพึ่งเบื่อกันเด้อ ไม่ได้ขอแต่บังคับ5555
สุดท้ายนี้ขอให้คุณวรเมธสนุกกับการใช้ชีวิตในทุกวัน
ถึงจะเหนื่อยหน่อย ครั้งหนึ่งในชีวิตที่ได้เหนื่อยขนาดนี้
จงภูมิใจ5555 🤍
      </p>

      <div class="signature">
        With all my love,<br>
        Yours ♡
      </div>

    </div>

  </section>

  <footer>
    Made with love, just for you ♡
  </footer>

</div>

<script>

// CHANGE PASSWORD HERE
const SECRET_PASSWORD = "19092007";

// PASSWORD
function unlock() {

  const pass = document.getElementById("password").value;

  if(pass === SECRET_PASSWORD) {

    document.getElementById("lockScreen").style.display = "none";

    document.getElementById("website").style.display = "block";

  } else {

    document.getElementById("error").innerText =
      "รหัสผ่านไม่ถูกต้อง ลองอีกครั้งนะจ้ะ 🤍";

  }

}

// OPEN ENVELOPE
function openEnvelope() {

  const envelope = document.getElementById("envelope");

  const letter = document.getElementById("letterSection");

  if(!envelope.classList.contains("open")) {

    envelope.classList.add("open");

    document.getElementById("hint").innerText =
      "YOUR LETTER IS OPEN ♡";

    setTimeout(() => {

      letter.style.display = "block";

      letter.scrollIntoView({
        behavior: "smooth",
        block: "start"
      });

    }, 900);

  }

}

</script>

</body>
</html>
# woramet-