<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Gaetano Leone — 18° Compleanno</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">

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

      background:
        radial-gradient(circle at 50% 20%, #292929 0%, #111 45%, #030303 100%);

      color: #f5f1e8;
      font-family: 'Montserrat', sans-serif;
    }

    /* =========================
       PARTICELLE
    ========================= */

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
      background: #d4af37;
      border-radius: 50%;
      box-shadow: 0 0 8px #d4af37;
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
    .particle:nth-child(9) { left: 25%; animation-delay: 6s; }
    .particle:nth-child(10) { left: 72%; animation-delay: 7s; }

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

    /* =========================
       INVITO
    ========================= */

    .invito {
      position: relative;

      width: min(620px, 90vw);
      min-height: 760px;

      padding: 70px 45px;

      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      text-align: center;

      background: rgba(15, 15, 15, .9);
      border: 1px solid rgba(212, 175, 55, .55);

      box-shadow:
        0 30px 100px rgba(0,0,0,.8),
        inset 0 0 70px rgba(212,175,55,.04);

      overflow: hidden;

      opacity: 0;
      transform: translateY(35px) scale(.96);

      animation: cardIn 1.4s cubic-bezier(.2,.8,.2,1) forwards;
    }

    @keyframes cardIn {
      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    /* Luminosità che attraversa la cornice */

    .invito::before {
      content: "";
      position: absolute;
      inset: 17px;

      border: 1px solid rgba(212,175,55,.25);

      animation: borderGlow 4s ease-in-out infinite;
    }

    .invito::after {
      content: "";
      position: absolute;

      width: 300px;
      height: 300px;

      background: rgba(212,175,55,.06);
      filter: blur(80px);

      border-radius: 50%;

      top: -150px;
      left: -150px;

      animation: glowMove 7s ease-in-out infinite alternate;
    }

    @keyframes borderGlow {
      0%,100% {
        border-color: rgba(212,175,55,.18);
      }

      50% {
        border-color: rgba(212,175,55,.55);
      }
    }

    @keyframes glowMove {
      to {
        transform: translate(650px, 650px);
      }
    }

    /* =========================
       TESTI
    ========================= */

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
      transform: translateY(20px);
    }

    .piccolo {
      font-size: 12px;
      letter-spacing: 5px;
      text-transform: uppercase;
      color: #d4af37;

      animation: textIn .9s .7s forwards;
    }

    h1 {
      margin-top: 25px;

      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(80px, 18vw, 125px);
      line-height: .75;

      font-weight: 500;
      letter-spacing: 4px;

      color: #f7f2e7;

      text-shadow:
        0 0 25px rgba(212,175,55,.15);

      animation:
        textIn 1s 1s forwards,
        numberGlow 4s 2s ease-in-out infinite;
    }

    @keyframes numberGlow {
      0%,100% {
        text-shadow: 0 0 10px rgba(212,175,55,0);
      }

      50% {
        text-shadow: 0 0 30px rgba(212,175,55,.35);
      }
    }

    .nome {
      margin-top: 25px;

      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(32px, 7vw, 50px);

      font-weight: 600;
      letter-spacing: 3px;

      color: #d4af37;

      animation: textIn 1s 1.3s forwards;
    }

    .linea {
      width: 0;
      height: 1px;

      margin: 35px 0;

      background: #d4af37;

      animation: lineIn 1s 1.7s forwards;
    }

    @keyframes lineIn {
      to {
        width: 90px;
      }
    }

    .testo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 24px;
      line-height: 1.5;

      animation: textIn 1s 1.9s forwards;
    }

    .dettagli {
      margin-top: 38px;

      display: flex;
      flex-direction: column;
      gap: 20px;

      animation: textIn 1s 2.2s forwards;
    }

    .dettaglio {
      display: flex;
      flex-direction: column;
      gap: 5px;
    }

    .etichetta {
      font-size: 10px;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: #888;
    }

    .valore {
      font-family: 'Cormorant Garamond', serif;
      font-size: 26px;
    }

    .luogo {
      color: #d4af37;
    }

    .footer {
      margin-top: 45px;

      font-size: 10px;
      letter-spacing: 4px;
      text-transform: uppercase;

      color: #777;

      animation: textIn 1s 2.5s forwards;
    }

    @keyframes textIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* =========================
       MOBILE
    ========================= */

    @media (max-width: 500px) {

      .invito {
        min-height: 700px;
        padding: 55px 25px;
      }

      .testo {
        font-size: 21px;
      }

      .valore {
        font-size: 23px;
      }

      .piccolo {
        letter-spacing: 3px;
      }
    }
  </style>
</head>

<body>

  <!-- Particelle dorate -->
  <div class="particles">
    <span class="particle"></span>
    <span class="particle"></span>
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
        <span class="etichetta">Luogo</span>
        <span class="valore luogo">
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
