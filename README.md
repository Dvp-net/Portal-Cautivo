<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta http-equiv="Cache-Control" content="no-store, max-age=0, must-revalidate" />
  <meta http-equiv="Pragma" content="no-cache" />
  <meta http-equiv="Expires" content="0" />
  <title>Conexión Exitosa | Grupo ISM</title>
  <style>
    :root{
      --ism-green:#1c9215;
      --ism-red:#E03120;
      --ink:#111418;
      --muted:#5e6670;
      --bg:#f6f7f8;
      --card:#ffffff;
      --ring:rgba(0,0,0,.08);
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:system-ui,-apple-system,"Segoe UI",Roboto,Ubuntu,Cantarell,Arial,sans-serif;
      color:var(--ink);
      background:linear-gradient(135deg,#ffffff 0%,#fff7f5 35%,#f4fff6 100%);
      display:flex; align-items:center; justify-content:center; padding:24px;
    }
    .card{
      width:100%; max-width:620px;
      background:var(--card);
      border:1px solid var(--ring);
      border-radius:18px;
      box-shadow:0 18px 40px rgba(0,0,0,.08);
      padding:28px 24px;
      text-align:center;
      position:relative; overflow:hidden;
    }
    .ribbon{
      position:absolute; inset:auto -42px -42px auto; width:240px; height:240px; opacity:.10;
      background:
        radial-gradient(closest-side,var(--ism-red),transparent 70%),
        radial-gradient(closest-side,var(--ism-green),transparent 70%);
      filter:blur(8px);
      pointer-events:none;
    }
    /* ====== LOGO ====== */
    .brand{
      display:flex; align-items:center; justify-content:center;
      margin:6px auto 14px;
    }
    .brand picture, .brand img, .brand svg{
      display:block; margin:0 auto;
      width:100%; max-width:260px; height:auto; object-fit:contain;
    }

    .ok{font-size:1.8rem; margin:8px 0 6px}

    h1{margin:.35rem 0 .6rem; font-size:1.42rem; letter-spacing:.2px}
    hr{border:none; height:1px; background:rgba(0,0,0,.08); margin:10px 0 14px}

    p{margin:.2rem 0; color:var(--muted); line-height:1.45}

    .btns{display:flex; gap:12px; flex-wrap:wrap; justify-content:center; margin-top:18px}
    .btn{
      display:inline-block; padding:14px 18px; border-radius:12px; text-decoration:none; font-weight:800;
      border:1px solid rgba(0,0,0,.08); transition:transform .05s ease, box-shadow .15s ease, filter .12s ease;
      box-shadow:0 8px 22px rgba(0,0,0,.06);
      user-select:none;
    }
    .btn:active{transform:translateY(1px)}
    .btn-primary{background:var(--ism-green); color:#fff}
    .btn-secondary{background:#fff; color:var(--ink)}

    .hint{margin-top:14px; font-size:.9rem; color:#6b7178}
    .footer{margin-top:18px; font-size:.8rem; color:#8a9199}

    @media (max-width:520px){
      .card{padding:22px 18px}
      .brand picture, .brand img, .brand svg{max-width:210px}
      h1{font-size:1.28rem}
    }

    /* Dark mode */
    @media (prefers-color-scheme: dark){
      body{background:#0e1114}
      .card{background:#0f1512; border-color:#0b1f14}
      hr{background:#13241b}
      .hint,.footer{color:#9aa3a8}
      .ok{color:#c8f4ce}
    }
  </style>
</head>
<body>
  <main class="card" role="main" aria-label="Conexión Exitosa">
    <!-- LOGO: usa SVG si existe; si no, cae al PNG -->
    <div class="brand" aria-label="Logo Grupo ISM">
      <picture>
        <source srcset="./assets/logo-ism.svg" type="image/svg+xml">
        <img src="./assets/logo-ism.png" alt="Grupo ISM">
      </picture>
    </div>

    <div class="ok">✅</div>
    <h1>¡Conexión exitosa!</h1>
    <hr />
    <p>Ya estás conectado(a) al Wi-Fi de <b>Grupo ISM</b>.</p>

    <div class="btns">
      <!-- Abre Instagram en el navegador real -->
      <a class="btn btn-primary" href="https://www.instagram.com/ism_rd/" target="_blank" rel="noopener">
        Ir a nuestro Instagram
      </a>
      <!-- Deep-link: intenta abrir la app de Instagram -->
      <a class="btn btn-secondary" href="instagram://user?username=ism_rd">
        Abrir en la app
      </a>
    </div>

    <p class="hint">Si no se abre, toca “Abrir en navegador” o vuelve a intentar con el otro botón.</p>
    <div class="footer">© Grupo ISM — Mantente conectado.</div>

    <div class="ribbon" aria-hidden="true"></div>
  </main>

  <script>
    // Si el portal está dentro del "Captive Network Assistant", intentamos cerrar el mini navegador al abrir fuera
    (function(){
      const ua = navigator.userAgent || "";
      const isMiniBrowser = /CaptiveNetwork|CNA|MiniBrowser|wv/i.test(ua);
      if(isMiniBrowser){
        document.querySelectorAll('a[target="_blank"]').forEach(a=>{
          a.addEventListener('click', ()=> setTimeout(()=>{ try{ window.close(); }catch(_){} }, 1200));
        });
      }
    })();
  </script>
</body>
</html>
