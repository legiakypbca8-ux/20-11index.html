
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Thư chúc mừng 20/11 | ALL WITH LOVE</title>

<style>
:root {
  --lime: #c6ff00;
  --green: #07594f;
  --yellow: #ffd400;
  --paper: #fffdf6;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  display: grid;
  place-items: center;
  overflow-x: hidden;
  font-family: Arial, sans-serif;
  background: var(--lime);
  color: #111;
  position: relative;
}

/* TRANG TRÍ NỀN */
.shape {
  position: absolute;
  width: 260px;
  height: 260px;
  border-radius: 50%;
  background: var(--green);
  pointer-events: none;
}

.left {
  left: -135px;
  top: 12%;
}

.right {
  right: -150px;
  bottom: 7%;
  width: 300px;
  height: 300px;
}

.dash {
  position: absolute;
  width: 150px;
  height: 32px;
  background: var(--yellow);
  transform: rotate(-10deg);
  pointer-events: none;
}

.one {
  top: 12%;
  right: 7%;
}

.two {
  bottom: 13%;
  left: 5%;
  transform: rotate(11deg);
}

/* BỐ CỤC CHÍNH */
.scene {
  width: min(92vw, 760px);
  text-align: center;
  position: relative;
  z-index: 1;
  padding: 30px 12px 60px;
}

.eyebrow {
  font-size: clamp(13px, 2vw, 17px);
  font-weight: 800;
  letter-spacing: .18em;
  margin-bottom: 22px;
}

/* PHONG BÌ */
.envelope {
  position: relative;
  width: min(100%, 690px);
  aspect-ratio: 1.55 / 1;
  margin: auto;

  background: #171a1a;
  border: 4px solid #080a0a;
  border-radius: 16px;

  overflow: hidden;
  filter: drop-shadow(12px 17px 0 var(--green));
  isolation: isolate;
}

/* HỌA TIẾT CHẤM */
.envelope::before {
  content: "";
  position: absolute;
  inset: 0;
  z-index: 1;
  border-radius: 12px;

  background-image:
    radial-gradient(#444 1.5px, transparent 1.5px);

  background-size: 12px 12px;
  opacity: .55;
  pointer-events: none;
}

/* LÁ THƯ */
.letter {
  position: absolute;
  left: 8%;
  right: 8%;
  bottom: 9%;
  height: 75%;

  background: var(--paper);
  border-radius: 5px;
  z-index: 2;

  box-shadow: 7px 7px 0 var(--yellow);

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;

  padding: 20px;

  opacity: 0;
  visibility: hidden;

  transition:
    bottom .8s cubic-bezier(.2,.8,.2,1),
    opacity .5s ease,
    visibility .5s ease;
}

.letter h1 {
  margin: 18px 0 12px;
  font-size: clamp(20px, 4vw, 34px);
  flex-shrink: 0;
}

.letter p {
  width: 100%;
  max-width: 470px;
  margin: 7px 0;

  font-size: clamp(12px, 2vw, 17px);
  line-height: 1.6;
}

.signature {
  font-weight: 800;
}

/* NẮP PHONG BÌ */
.flap {
  position: absolute;
  inset: 0;
  z-index: 5;

  transform-origin: top center;
  transition: transform .8s ease;

  background: var(--paper);
  clip-path: polygon(0 0, 100% 0, 50% 57%);

  backface-visibility: hidden;
  pointer-events: none;
}

/* MẶT TRƯỚC PHONG BÌ */
.front {
  position: absolute;
  inset: 0;
  z-index: 3;

  background: var(--paper);
  border-radius: 0 0 12px 12px;

  clip-path: polygon(
    0 100%,
    0 38%,
    50% 78%,
    100% 38%,
    100% 100%
  );

  pointer-events: none;
}

/* NÚT VÀNG 20/11 */
.seal-front {
  position: absolute;
  z-index: 7;

  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  width: 92px;
  height: 92px;

  border-radius: 50%;
  display: grid;
  place-items: center;

  background: var(--yellow);
  border: 6px solid #101212;

  font-weight: 900;
  font-size: 23px;

  cursor: pointer;

  transition:
    opacity .35s ease,
    transform .35s ease;
}

.seal-front:hover {
  transform: translate(-50%, -50%) scale(1.08);
}

/* NÚT ĐÓNG THƯ */
.hint {
  margin-top: 30px;
  padding: 13px 23px;

  color: white;
  background: #111;
  border: 0;

  box-shadow: 5px 5px 0 var(--yellow);

  font-size: 15px;
  font-weight: 900;
  cursor: pointer;
}

.hint:hover {
  transform: translateY(-3px);
}

.subhint {
  margin-top: 15px;
  font-size: 13px;
  font-weight: 700;
}

/* HIỆU ỨNG MỞ PHONG BÌ */
.envelope.opened .flap {
  transform: rotateX(180deg);
}

/* LÁ THƯ NHÔ LÊN NHẸ, KHÔNG BAY RA NGOÀI */
.envelope.opened .letter {
  height: 88%;
  max-height: 75vh;

  bottom: 6%;

  opacity: 1;
  visibility: visible;

  z-index: 8;

  overflow-y: auto;
  overflow-x: hidden;

  justify-content: flex-start;

  padding: 25px 22px;

  scrollbar-width: thin;
  scrollbar-color: var(--green) var(--paper);
}

/* THANH CUỘN TRÊN CHROME */
.envelope.opened .letter::-webkit-scrollbar {
  width: 6px;
}

.envelope.opened .letter::-webkit-scrollbar-track {
  background: var(--paper);
}

.envelope.opened .letter::-webkit-scrollbar-thumb {
  background: var(--green);
  border-radius: 10px;
}

/* CON DẤU BIẾN MẤT KHI MỞ */
.envelope.opened .seal-front {
  opacity: 0;
  pointer-events: none;
  transform: translate(-50%, -50%) scale(.5);
}

/* GIẤY MÀU RƠI */
.confetti {
  position: fixed;
  top: -20px;
  width: 10px;
  height: 14px;
  z-index: 20;
  pointer-events: none;

  animation: fall 3s linear forwards;
}

@keyframes fall {
  to {
    transform: translateY(110vh) rotate(720deg);
    opacity: 0;
  }
}

/* ĐIỆN THOẠI */
@media (max-width: 520px) {
  .scene {
    padding: 20px 8px 50px;
  }

  .envelope {
    width: 95%;
  }

  .envelope.opened .letter {
    height: 90%;
    max-height: 70vh;
    bottom: 5%;
    padding: 25px 14px 20px;
  }

  .letter h1 {
    font-size: 21px;
  }

  .letter p {
    font-size: 13px;
    line-height: 1.6;
  }

  .seal-front {
    width: 72px;
    height: 72px;
    font-size: 19px;
  }
}
</style>
</head>

<body>

<div class="shape left"></div>
<div class="shape right"></div>
<div class="dash one"></div>
<div class="dash two"></div>

<main class="scene">

  <div class="eyebrow">
    20.11 · VIETNAMESE TEACHERS' DAY
  </div>

  <div class="envelope" id="envelope">

    <!-- NỘI DUNG LÁ THƯ -->
    <div class="letter">

      <h1>Happy Teachers' Day!</h1>

      <p>
        Nhân ngày Nhà giáo Việt Nam 20/11, em muốn gửi đến cô lời cảm ơn chân thành nhất vì đã luôn tận tâm, kiên nhẫn và dành biết bao tâm huyết cho hành trình gieo chữ, trao truyền tri thức.
      </p>

      <p>
        Cảm ơn cô vì đã trở thành một người giữ lửa, giúp em nuôi dưỡng tình yêu với sự học, để mỗi trang viết không chỉ là nơi gửi gắm những suy nghĩ mà còn là hành trình khám phá, chiêm nghiệm và thấu hiểu cuộc sống. Có lẽ, điều đáng quý nhất mà em nhận được không chỉ nằm ở những kiến thức hay bài học trên trang giấy, mà còn là cách cô khơi gợi trong em niềm say mê, sự rung cảm và khát vọng được đi xa hơn trên con đường theo đuổi con chữ.
      </p>

      <p class="signature">
        Em chúc cô luôn mạnh khỏe, bình an, hạnh phúc và mãi giữ trong mình ngọn lửa nhiệt thành với sự nghiệp trồng người. Mong rằng trên hành trình miệt mài gieo những hạt mầm tri thức, cô sẽ luôn nhận lại thật nhiều yêu thương, trân trọng và những mùa hoa trái ngọt lành từ các thế hệ học trò. Chúc cô có một ngày 20/11 thật ý nghĩa và trọn vẹn ạ!
      </p>

      <p class="signature">
        — Lê Gia Kỳ —
      </p>

    </div>

    <!-- CÁC LỚP PHONG BÌ -->
    <div class="flap"></div>
    <div class="front"></div>

    <!-- NÚT NIÊM PHONG -->
    <button class="seal-front" id="sealButton">
      20/11
    </button>

  </div>

  <button class="hint" id="hintButton">
    BẤM VÀO BAO THƯ ĐỂ MỞ
  </button>

  <div class="subhint">
    Một lời cảm ơn nhỏ, gửi đến những người truyền cảm hứng lớn.
  </div>

</main>

<script>
const envelope = document.getElementById("envelope");
const sealButton = document.getElementById("sealButton");
const hintButton = document.getElementById("hintButton");

let opened = false;

/* HIỆU ỨNG GIẤY MÀU */
function createConfetti() {
  const colors = [
    "#07594f",
    "#ffd400",
    "#ffffff",
    "#111111"
  ];

  for (let i = 0; i < 45; i++) {
    const piece = document.createElement("div");

    piece.classList.add("confetti");

    piece.style.left = Math.random() * 100 + "vw";

    piece.style.backgroundColor =
      colors[Math.floor(Math.random() * colors.length)];

    piece.style.animationDelay =
      Math.random() * 1.2 + "s";

    piece.style.animationDuration =
      (2 + Math.random() * 2) + "s";

    document.body.appendChild(piece);

    setTimeout(() => {
      piece.remove();
    }, 4500);
  }
}

/* ĐÓNG / MỞ PHONG BÌ */
function toggleEnvelope() {
  opened = !opened;

  envelope.classList.toggle("opened", opened);

  hintButton.textContent = opened
    ? "ĐÓNG LÁ THƯ"
    : "BẤM VÀO BAO THƯ ĐỂ MỞ";

  if (opened) {
    createConfetti();
  }
}

/* CHỈ NHẤN NÚT VÀNG ĐỂ MỞ */
sealButton.addEventListener("click", toggleEnvelope);

/* NÚT BÊN DƯỚI ĐỂ ĐÓNG / MỞ */
hintButton.addEventListener("click", toggleEnvelope);
</script>

</body>
</html>
