<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Titolo modificato per evitare scritte indesiderate all'esterno della card -->
<title>Gaetano Leone</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  min-height: 100vh;
  overflow: hidden;

  display: flex;
  justify-content: center;
  align-items: center;

  padding: 15px;

  background:
    radial-gradient(circle at 50% 20%, #292929 0%, #111 45%, #030303 100%);

  color: #eeeeee;
  font-family: 'Inter', sans-serif;
}

/* PARTICELLE */

.particles {
  position: fixed;
  inset: 0;
  pointer-events: none;
  overflow: hidden;
}

.particle {
  position: absolute;
  bottom: -10px;

  width: 2px;
  height: 2px;

  background: #d8d8d8;
  border-radius: 50%;

  box-shadow: 0 0 8px #ffffff;

  opacity: 0;

  animation: float 8s linear infinite;
}

.particle:nth-child(1) { left: 8%; animation-delay: 0s; }
.particle:nth-child(2) { left: 18%; animation-delay: 2s; }
.particle:nth-child(3) { left: 30%; animation-delay: 4s; }
.particle:nth-child(4) { left: 42%; animation-delay: 1s; }
.particle:nth-child(5) { left: 55%; animation-delay: 5s; }
.particle:nth-child(6) { left: 67%; animation-delay: 3s; }
.particle:nth-child(7) { left: 78%; animation-delay: 6s; }
.particle:nth-child(8) { left: 90%; animation-delay: 1.5s; }

@keyframes float {
  0% {
    transform: translateY(0) scale(0);
    opacity: 0;
  }

  15% {
    opacity: .7;
  }

  70% {
    opacity: .5;
  }

  100% {
    transform: translateY(-110vh) translateX(40px) scale(1.5);
    opacity: 0;
  }
}

/* CARD */

.invito {
  position: relative;

  width: min(440px, 92vw);
  min-height: 570px;

  padding: 45px 30px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  text-align: center;

  background: rgba(15, 15, 15, .93);

  border: 1px solid rgba(210, 210, 210, .45);

  box-shadow:
    0 25px 70px rgba(0,0,0,.8),
    inset 0 0 50px rgba(255,255,255,.025);

  overflow: hidden;

  opacity: 0;
  transform: translateY(30px) scale(.97);

  animation:
    cardIn 1.2s cubic-bezier(.2,.8,.2,1) forwards;
}

@keyframes cardIn {
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

/* CORNICE */

.invito::before {
  content: "";

  position: absolute;
  inset: 13px;

  border: 1px solid rgba(220,220,220,.22);

  animation: borderGlow 4s ease-in-out infinite;
}

@keyframes borderGlow {
  0%,100% {
    border-color: rgba(220,220,220,.16);
  }

  50% {
    border-color: rgba(255,255,255,.5);
  }
}

/* BAGLIORE */

.invito::after {
  content: "";

  position: absolute;

  width: 250px;
  height: 250px;

  border-radius: 50%;

  background: rgba(255,255,255,.045);

  filter: blur(70px);

  top: -120px;
  left: -120px;

  animation: glowMove 7s ease-in-out infinite alternate;
}

@keyframes glowMove {
  to {
    transform: translate(500px, 500px);
  }
}

/* TESTI */

.piccolo,
h1,
.nome,
.linea,
.testo,
.dettagli,
.footer {
  position: relative;
  z-index: 2;

  opacity: 0;
  transform: translateY(18px);
}

.piccolo {
  font-size: 9px;
  letter-spacing: 4px;
  text-transform: uppercase;

  color: #bdbdbd;

  animation: textIn .8s .6s forwards;
}

h1 {
  margin-top: 18px;

  font-size: 100px;
  line-height: .75;

  font-weight: 300;
  letter-spacing: -5px;

  color: #f2f2f2;

  text-shadow:
    0 0 20px rgba(255,255,255,.12);

  animation:
    textIn .9s .9s forwards,
    silverGlow 4s 2s ease-in-out infinite;
}

@keyframes silverGlow {
  0%,100% {
    text-shadow: 0 0 10px rgba(255,255,255,0);
  }

  50% {
    text-shadow: 0 0 28px rgba(255,255,255,.3);
  }
}

.nome {
  margin-top: 22px;

  font-size: 27px;
  font-weight: 400;

  letter-spacing: 4px;

  color: #d5d5d5;

  animation: textIn .9s 1.2s forwards;
}

.linea {
  width: 0;
  height: 1px;

  margin: 25px 0;

  background: #d5d5d5;

  animation: lineIn .9s 1.5s forwards;
}

@keyframes lineIn {
  to {
    width: 70px;
  }
}

.testo {
  font-size: 15px;
  font-weight: 300;
  line-height: 1.7;

  color: #bdbdbd;

  animation: textIn .8s 1.7s forwards;
}

.dettagli {
  margin-top: 27px;

  display: flex;
  flex-direction: column;

  gap: 15px;

  animation: textIn .8s 2s forwards;
}

.dettaglio {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.etichetta {
  font-size: 8px;
  letter-spacing: 3px;

  text-transform: uppercase;

  color: #777;
}

.valore {
  font-size: 17px;
  font-weight: 400;

  color: #eeeeee;
}

.footer {
  margin-top: 30px;

  font-size: 8px;
  letter-spacing: 3px;

  text-transform: uppercase;

  color: #666;

  animation: textIn .8s 2.3s forwards;
}

@keyframes textIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* MOBILE */

@media (max-width: 450px) {

  .invito {
    width: min(380px, 94vw);
    min-height: 540px;

    padding: 40px 25px;
  }

  h1 {
    font-size: 90px;
  }

  .nome {
    font-size: 24px;
    letter-spacing: 3px;
  }
}
</style>
</head>

<body>

<div class="particles">
  <span class="particle"></span>
  <span class="particle"></span>
  <span class="particle"></span>
  <span class="particle"></span>
  <span class="particle"></span>
  <span class="particle"></span>
  <span class="particle"></span>
  <span class="particle"></span>
</div>

<main class="invito">

  <div class="piccolo">
    Sei invitato
  </div>

  <h1>18</h1>

  <div class="nome">
    Gaetano Leone
  </div>

  <div class="linea"></div>

  <p class="testo">
    Una serata speciale per celebrare<br>
    un traguardo importante.
  </p>

  <div class="dettagli">

    <div class="dettaglio">
      <span class="etichetta">Data</span>
      <span class="valore">
        24 Ottobre 2026
      </span>
    </div>

    <div class="dettaglio">
      <span class="etichetta">Ora</span>
      <span class="valore">
        20:00
      </span>
    </div>

    <div class="dettaglio">
      <span class="etichetta">Luogo</span>
      <span class="valore">
        Convivio di Hera · KR
      </span>
    </div>

  </div>

  <div class="footer">
    Una notte da ricordare
  </div>

</main>

</body>
</html>
