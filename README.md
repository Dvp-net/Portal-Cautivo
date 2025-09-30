<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Portal Cautivo | Grupo ISM</title>

  <!-- Favicon & PWA -->
  <link rel="icon" href="/portal-exito/assets/favicon.ico">
  <link rel="icon" type="image/svg+xml" href="/portal-exito/assets/favicon.svg">
  <link rel="apple-touch-icon" href="/portal-exito/assets/favicon-192.png">
  <link rel="manifest" href="/portal-exito/assets/site.webmanifest">
  <meta name="theme-color" content="#1c9215">

  <style>
    :root{
      --ism-green:#1c9215; --ism-red:#E03120;
      --ink:#111418; --muted:#5e6670;
      --bg:#f6f7f8; --card:#ffffff; --ring:rgba(0,0,0,.08);
    }
    *{box-sizing:border-box}
    body{
      margin:0; font-family:system-ui,-apple-system,"Segoe UI",Roboto,Ubuntu,Arial,sans-serif;
      background:#0e1114; display:flex; align-items:center; justify-content:center; min-height:100vh;
      padding:24px; color:var(--ink);
    }
    .card{
      width:100%; max-width:620px; background:var(--card); border:1px solid var(--ring);
      border-radius:18px; box-shadow:0 18px 40px rgba(0,0,0,.08);
      padding:28px 24px; text-align:center;
    }
    .brand picture, .brand img, .brand svg{
      display:block; margin:6px auto 14px; width:100%; max-width:260px; height:auto; object-fit:contain;
    }
    .ok{font-size:1.8rem; margin:8px 0 6px}
    h1{margin:.35rem 0 .6rem; font-size:1.42rem; letter-spacing:.2px}
    hr{border:none; height:1px; background:rgba(0,0,0,.12); margin:10px 0 14px}
    p{margin:.2rem 0; color:var(--muted); line-height:1.45}
    .btns{display:flex; gap:12px; flex-wrap:wrap; justify-content:center; margin-top:18px}
    .btn{
      padding:14px 18px; border-radius:12px; font-weight:800; text-decoration:none;
      border:1px solid rgba(0,0,0,.08); box-shadow:0 8px 22px rgba(0,0,0,.06);
      transition:.15s; user-select:none;
    }
    .btn-primary{background:var(--ism-green); color:#fff}
    .btn-secondary{background:#fff; color:#111}
    .btn:active{transform:translateY(1px)}
    .hint{margin-top:14px; font-size:.9rem; color:#6b7178}
    .footer{margin-top:18px; font-size:.8rem; color:#8a9199}
  </style>
</head>
<body>
  <main class="card">
    <!-- LOGO Grupo ISM -->
    <div class="brand" aria-label="Logo Grupo ISM">
  <img class="logo" src="/Portal-Cautivo/logo-ism.png?v=2" alt="Grupo ISM">
</div>


    <div class="ok">✅</div>
    <h1>¡Conexión exitosa!</h1>
    <hr />
    <p>Ya estás conectado(a) al Wi-Fi de <b>Grupo ISM</b>.</p>

    <div class="btns">
      <a class="btn btn-primary" href="https://www.instagram.com/ism_rd/" target="_blank" rel="noopener">Ir a nuestro Instagram</a>
      <a class="btn btn-secondary" href="instagram://user?username=ism_rd">Abrir en la app</a>
    </div>

    <p class="hint">Si no se abre, toca “Abrir en navegador” o vuelve a intentar con el otro botón.</p>
    <div class="footer">© Grupo ISM — Mantente conectado.</div>
  </main>

  <script>
    // Si el portal abre en Captive Network Assistant, forzamos salida al navegador real
    (function(){
      const ua = navigator.userAgent||""; 
      const isMini = /CaptiveNetwork|CNA|MiniBrowser|wv/i.test(ua);
      if(isMini){
        document.querySelectorAll('a[target="_blank"]').forEach(a=>{
          a.addEventListener('click', ()=> setTimeout(()=>{ try{ window.close(); }catch(_){ } }, 1200));
        });
      }
    })();
  </script>
</body>
</html>
