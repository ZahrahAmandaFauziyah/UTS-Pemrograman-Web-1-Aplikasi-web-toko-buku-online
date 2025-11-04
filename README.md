# UTS-Pemrograman-Web-1-Aplikasi-web-toko-buku-online
Nama : Zahrah Amanda Fauziyah
Kelas : TI.24.A2
NIM : 312410193
Mata Kuliah : Pemrograman Web 1


1. Index.HTML
   
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Login • MaNey Bookstore</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="css/style.css">
</head>
<body class="gradient-bg">

  <main class="center-wrap">
    <div class="card auth-card glass neon">
      <div class="brand">
        <img src="assets/logo.png" alt="logo" class="logo" onerror="this.style.display='none'">
        <div>
          <h1 class="brand-title">MaNey</h1>
          <div class="muted small">Bookstore — Zahrah Amanda Fauziyah • NIM 312410193</div>
        </div>
      </div>

      <form id="loginForm" class="form" onsubmit="return handleLogin(event)">
        <label>Email
          <input id="email" type="email" placeholder="email@domain.com" required>
        </label>
        <label>Password
          <input id="password" type="password" placeholder="Masukkan password" required>
        </label>

        <div class="row space">
          <button type="submit" class="btn primary">Login</button>
          <div class="links">
            <button type="button" class="btn ghost" onclick="openModal('forgot')">Lupa Password</button>
            <button type="button" class="btn ghost" onclick="openModal('register')">Daftar</button>
          </div>
        </div>
      </form>

      <p class="foot-note muted">Akun demo: <strong>rina@gmail.com / rina123</strong></p>
    </div>
  </main>

  <!-- modals -->
  <div id="backdrop" class="backdrop hidden" onclick="closeModal()"></div>

  <div id="modal-forgot" class="modal-card hidden glass neon">
    <h3>Lupa Password</h3>
    <p>Masukkan email (simulasi)</p>
    <input id="forgotEmail" placeholder="email@domain.com">
    <div class="row" style="justify-content:flex-end;">
      <button class="btn" onclick="closeModal()">Batal</button>
      <button class="btn primary" onclick="simulateForgot()">Kirim</button>
    </div>
  </div>

  <div id="modal-register" class="modal-card hidden glass neon">
    <h3>Daftar Akun</h3>
    <p>Form pendaftaran (simulasi)</p>
    <input id="regName" placeholder="Nama lengkap">
    <input id="regEmail" placeholder="email@domain.com">
    <div class="row" style="justify-content:flex-end;">
      <button class="btn" onclick="closeModal()">Batal</button>
      <button class="btn primary" onclick="simulateRegister()">Daftar</button>
    </div>
  </div>

  <script src="js/data.js"></script>
  <script src="js/script.js"></script>
</body>
</html>

<img width="1919" height="862" alt="Cuplikan layar 2025-11-04 182058" src="https://github.com/user-attachments/assets/f96e96c6-e0b8-41ef-b4ae-feeb67c57323" />
Penjelasan : 
1. Halaman Login (index.html)
Di bagian ini terdapat form untuk mengisi email dan password.
Jika pengguna mengisi dengan benar, maka akan muncul pesan sukses dan langsung diarahkan ke halaman dashboard.
Jika salah, muncul alert “email/password yang anda masukkan salah”.
Pada bagian bawah juga terdapat tombol “Lupa Password” dan “Daftar” yang muncul dalam bentuk pop-up.

2. Dashboard.HTML

<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Dashboard • MaNey</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="css/style.css">
</head>
<body class="gradient-bg">

  <header class="topbar glass neon">
    <div class="left">
      <img src="assets/logo.png" class="logo-small" alt="logo" onerror="this.style.display='none'">
      <div>
        <h2>MaNey</h2>
        <div class="muted small">Bookstore — Neon Lavender</div>
      </div>
    </div>
    <nav class="nav">
      <a href="stok.html">Katalog</a>
      <a href="checkout.html">Checkout</a>
      <a href="tracking.html">Tracking</a>
      <a href="index.html">Logout</a>
    </nav>
  </header>

  <main class="container">
    <section class="hero glass neon">
      <div id="greeting" class="greeting"></div>
      <p class="muted">Sistem front-end pemesanan buku — tema Lavender Neon.</p>

      <div class="quick-links">
        <a class="card neon-card" href="stok.html">Informasi Stok / Katalog</a>
        <a class="card neon-card" href="tracking.html">Tracking Pengiriman</a>
        <a class="card neon-card" href="#">Laporan Pemesanan</a>
        <a class="card neon-card" href="#">History Transaksi</a>
      </div>
    </section>

    <section class="latest glass neon">
      <h3>Rekomendasi Buku</h3>
      <div id="recommend" class="book-row"></div>
    </section>
  </main>

  <footer class="footer muted">Dibuat oleh Zahrah Amanda Fauziyah — NIM 312410193</footer>

  <script src="js/data.js"></script>
  <script src="js/script.js"></script>
</body>
</html>

<img width="1919" height="958" alt="Cuplikan layar 2025-11-04 182117" src="https://github.com/user-attachments/assets/4c1741eb-15eb-4d2f-8079-981659937d47" />
Penjelasan :
2. Halaman Dashboard (dashboard.html)
Di halaman ini, sistem menampilkan sapaan otomatis berdasarkan waktu — pagi, siang, sore, atau malam.
Terdapat juga menu navigasi menuju Stok Buku, Checkout, dan Tracking Pengiriman.
Desain dashboard dibuat dengan efek glassmorphism dan gradasi warna ungu-lavender agar tampil futuristik.

3. Stok.HTML

<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Stok • MaNey</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="css/style.css">
</head>
<body class="gradient-bg">

  <header class="topbar glass neon">
    <div class="left"><img src="assets/logo.png" class="logo-small" alt="logo" onerror="this.style.display='none'"><h2>MaNey</h2></div>
    <nav class="nav"><a href="dashboard.html">Dashboard</a><a href="checkout.html">Checkout</a><a href="tracking.html">Tracking</a></nav>
  </header>

  <main class="container">
    <section class="panel glass neon">
      <div class="panel-head">
        <h3>Katalog Buku</h3>
        <div>
          <button class="btn" onclick="renderAddRowCatalog()">Tambah Baris Stok</button>
          <button class="btn primary" onclick="saveCatalog()">Simpan Perubahan</button>
        </div>
      </div>

      <div class="table-wrap">
        <table id="catalogTable" class="table neon-table">
          <thead>
            <tr><th>Kode</th><th>Cover</th><th>Judul</th><th>Stok</th><th>Harga</th><th>Aksi</th></tr>
          </thead>
          <tbody id="catalogBody"></tbody>
        </table>
      </div>
    </section>
  </main>

  <script src="js/data.js"></script>
  <script src="js/script.js"></script>
</body>
</html>

<img width="1919" height="902" alt="Cuplikan layar 2025-11-04 182156" src="https://github.com/user-attachments/assets/dc8241a2-35c8-462d-b501-67ecd749f0c9" />
Penjelasan:
3. Halaman Stok / Katalog Buku (stok.html)
Di halaman ini, data buku diambil secara dinamis dari file data.js.
Semua data seperti kode buku, nama, stok, harga, dan gambar cover ditampilkan dalam bentuk tabel.
Pengguna bisa menambahkan baris baru atau mengedit stok langsung di tabel tanpa reload halaman.

4. Checkout.HTML

<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Checkout • MaNey</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="css/style.css">
</head>
<body class="gradient-bg">

  <header class="topbar glass neon">
    <div class="left"><img src="assets/logo.png" class="logo-small" alt="logo" onerror="this.style.display='none'"><h2>MaNey</h2></div>
    <nav class="nav"><a href="dashboard.html">Dashboard</a><a href="stok.html">Katalog</a><a href="tracking.html">Tracking</a></nav>
  </header>

  <main class="container narrow">
    <section class="panel glass neon">
      <h3>Form Pemesanan</h3>
      <form id="orderForm" onsubmit="return prosesPesanan(event)">
        <label>Nama Pemesan
          <input id="custName" required placeholder="Nama lengkap">
        </label>
        <label>Email
          <input id="custEmail" type="email" required placeholder="email@domain.com">
        </label>
        <label>Alamat
          <textarea id="custAddress" required placeholder="Alamat pengiriman"></textarea>
        </label>

        <h4>Daftar Pesanan</h4>
        <div id="orderList" class="order-list"><em>Belum ada item</em></div>

        <div class="row" style="align-items:center; gap:8px; margin-top:8px;">
          <select id="bookSelect"></select>
          <input id="qty" type="number" min="1" value="1" style="width:80px;">
          <button type="button" class="btn" onclick="addToOrder()">Tambah</button>
        </div>

        <label>Metode Pembayaran
          <select id="payMethod">
            <option>Transfer Bank</option>
            <option>COD</option>
            <option>e-Wallet</option>
          </select>
        </label>

        <div class="row space" style="margin-top:12px;">
          <button class="btn" type="reset" onclick="resetOrder()">Reset</button>
          <button class="btn primary" type="submit">Pesan Sekarang</button>
        </div>
      </form>
    </section>
  </main>

  <script src="js/data.js"></script>
  <script src="js/script.js"></script>
</body>
</html>

<img width="1919" height="990" alt="Cuplikan layar 2025-11-04 182251" src="https://github.com/user-attachments/assets/cb77e916-d5cd-4768-8e20-f5be2596df82" />

Penjelasan :
4. Halaman Pemesanan / Checkout (checkout.html)
Halaman ini berfungsi untuk melakukan pemesanan buku.
Pengguna mengisi nama, email, alamat, dan memilih buku yang ingin dipesan.
Setelah menekan tombol “Pesan Sekarang”, sistem akan membuat Nomor DO (Delivery Order) secara otomatis,
lalu menyimpannya di localStorage dan langsung pindah ke halaman Tracking.


5. Tracking.HTML

<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Tracking • MaNey</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="css/style.css">
</head>
<body class="gradient-bg">

  <header class="topbar glass neon">
    <div class="left"><img src="assets/logo.png" class="logo-small" alt="logo" onerror="this.style.display='none'"><h2>MaNey</h2></div>
    <nav class="nav"><a href="dashboard.html">Dashboard</a><a href="stok.html">Katalog</a><a href="checkout.html">Checkout</a></nav>
  </header>

  <main class="container narrow">
    <section class="panel glass neon">
      <h3>Tracking Pengiriman</h3>
      <label>Nomor Delivery Order
        <input id="doNumber" placeholder="Contoh: 20230012">
      </label>
      <div class="row" style="justify-content:flex-end; margin-top:8px;">
        <button class="btn primary" onclick="searchDO()">Cari</button>
      </div>

      <div id="trackingResult" style="margin-top:16px;"></div>
    </section>
  </main>

  <script src="js/data.js"></script>
  <script src="js/script.js"></script>
  <!-- tampilkan DO terakhir (jika berasal dari checkout) -->
  <script>
    document.addEventListener('DOMContentLoaded', ()=> {
      const last = JSON.parse(localStorage.getItem('pesananTerakhir'));
      if(last && last.noDO){
        // tampilkan ringkasan DO terakhir
        const out = document.getElementById('trackingResult');
        out.innerHTML = `<h4>Pesanan Terakhir — ${last.noDO}</h4>
          <p><strong>Nama:</strong> ${last.nama}</p>
          <p><strong>Buku:</strong> ${last.buku}</p>
          <p><strong>Status:</strong> ${last.status}</p>
          <p><strong>Tanggal:</strong> ${last.tanggal}</p>
          <p><strong>Total:</strong> ${last.total}</p>`;
      }
    });
  </script>
</body>
</html>

<img width="1919" height="969" alt="Cuplikan layar 2025-11-04 182350" src="https://github.com/user-attachments/assets/5426d6ae-69e8-4f86-9c37-4ad15a03b6d0" />
Penjelasan :
5. Halaman Tracking (tracking.html)
Di sini pengguna dapat melacak pesanan berdasarkan nomor DO.
Jika nomor DO sesuai dengan data di file data.js, maka akan muncul informasi nama pemesan, status pengiriman, ekspedisi, tanggal kirim, dan total pembayaran.
Ada juga tampilan progress bar yang menunjukkan sejauh mana pengiriman berlangsung.
Selain itu, jika pengguna baru saja melakukan checkout, maka data terakhirnya otomatis muncul di bagian tracking.

