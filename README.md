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
      --ism-red:#e03120;
      --ink:#0a0a0a;
      --muted:#5b5b5b;
      --bg:#f6f7f8;
      --card:#ffffff;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; font-family: system-ui, -apple-system, "Segoe UI", Roboto, Ubuntu, Cantarell, Arial, sans-serif;
      color:var(--ink); background:linear-gradient(135deg, #ffffff 0%, #fff7f5 30%, #f5fff6 100%);
      display:flex; align-items:center; justify-content:center; padding:24px;
    }
    .card{
      width:100%; max-width:560px; background:var(--card); border-radius:18px; padding:28px;
      box-shadow:0 18px 40px rgba(0,0,0,.08); text-align:center; position:relative; overflow:hidden;
      border:1px solid rgba(0,0,0,.06);
    }
    .ribbon{
      position:absolute; inset:auto -40px -40px auto; width:220px; height:220px; opacity:.08;
      background:
        radial-gradient(closest-side, var(--ism-red), transparent 70%),
        radial-gradient(closest-side, var(--ism-green), transparent 70%);
      filter:blur(6px);
    }
    .logo{
      height:64px; margin:6px auto 14px; display:block; object-fit:contain;
    }
    h1{margin:.2rem 0 .25rem; font-size:1.55rem}
    p{margin:.4rem 0; color:var(--muted)}
    .ok{font-size:1.6rem; margin-top:4px}
    .btns{display:flex; gap:12px; flex-wrap:wrap; justify-content:center; margin-top:16px}
    .btn{
      display:inline-block; padding:14px 18px; border-radius:12px; text-decoration:none; font-weight:700;
      border:1px solid rgba(0,0,0,.08); transition:transform .05s ease, box-shadow .15s ease;
      box-shadow:0 6px 18px rgba(0,0,0,.06);
    }
    .btn:active{transform:translateY(1px)}
    .btn-primary{background:var(--ism-green); color:#fff}
    .btn-secondary{background:#fff; color:var(--ink)}
    .hint{margin-top:12px; font-size:.86rem; color:#6b6b6b}
    .footer{margin-top:18px; font-size:.78rem; color:#8a8a8a}
    @media (prefers-color-scheme: dark){
      body{background:#0f1113}
      .card{background:#0f1512; border-color:#0d2014}
      .hint,.footer{color:#9aa3a8}
      .ok{color:#d1f7d6}
    }
  </style>
</head>
<body>
  <main class="card" role="main" aria-label="Conexión Exitosa">
    <!-- REEMPLAZA el src por tu logo oficial si quieres -->
    <img class="logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Check_green_icon.svg/120px-Check_green_icon.svg.png" alt="Grupo ISM" />
    <div class="ok">✅</div>
    <h1>¡Conexión exitosa!</h1>
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
    <div class="footer">© Grupo ISM — Mantente conectado. </div>
    <div class="ribbon" aria-hidden="true"></div>
  </main>
  <script>
    // Si el portal se abre dentro del "Captive Network Assistant", forzamos que los enlaces se abran fuera
    (function(){
      const isMiniBrowser = /CaptiveNetwork|CNA|MiniBrowser|wv/.test(navigator.userAgent);
      if(isMiniBrowser){
        document.querySelectorAll('a[target="_blank"]').forEach(a=>{
          a.addEventListener('click', ()=> setTimeout(()=>window.close(), 1200));
        });
      }
    })();
  </script>
</body>
</html>
