d'glazedonut 
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D'Glaze Premium - Lengkap & Akurat</title>
    <!-- Icons & Fonts -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #2c3e50;   /* Dark Blue */
            --accent: #e67e22;    /* Glaze Orange */
            --gold: #f1c40f;      /* Points Gold */
            --bg: #fdfbf7;        /* Creamy Background */
            --white: #ffffff;
            --gray: #95a5a6;
            --text-dark: #333333;
            --danger: #e74c3c;
            --radius: 12px;
            --shadow: 0 8px 30px rgba(0,0,0,0.08);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background-color: var(--bg); color: var(--text-dark); padding-bottom: 80px; }

        /* --- UI UTILITIES --- */
        .container { max-width: 1100px; margin: 0 auto; padding: 20px; }
        .btn { border: none; border-radius: 8px; padding: 10px 20px; cursor: pointer; font-weight: 600; transition: 0.2s; display: inline-flex; align-items: center; justify-content: center; gap: 8px; }
        .btn-primary { background: var(--primary); color: white; }
        .btn-accent { background: var(--accent); color: white; }
        .btn-gold { background: var(--gold); color: #444; }
        .btn-outline { border: 1px solid #ddd; background: white; color: var(--text-dark); }
        .btn:hover { filter: brightness(1.1); transform: translateY(-2px); }
        .btn:active { transform: translateY(0); }
        
        /* --- HEADER --- */
        header { background: var(--white); padding: 15px 5%; position: sticky; top: 0; z-index: 100; box-shadow: 0 2px 10px rgba(0,0,0,0.05); display: flex; justify-content: space-between; align-items: center; }
        .logo { font-weight: 800; font-size: 1.4rem; color: var(--accent); display: flex; align-items: center; gap: 8px; text-decoration: none; }
        .logo span { color: var(--primary); }
        
        nav ul { display: flex; list-style: none; gap: 25px; }
        nav a { text-decoration: none; color: var(--text-dark); font-weight: 500; font-size: 0.95rem; transition: 0.3s; position: relative; }
        nav a.active, nav a:hover { color: var(--accent); }
        nav a.active::after { content:''; position: absolute; bottom: -5px; left:0; width:100%; height:2px; background: var(--accent); }

        .header-actions { display: flex; align-items: center; gap: 15px; }
        .cart-btn { position: relative; cursor: pointer; font-size: 1.3rem; color: var(--primary); }
        .cart-badge { position: absolute; top: -6px; right: -8px; background: var(--accent); color: white; font-size: 0.7rem; width: 20px; height: 20px; border-radius: 50%; display: flex; justify-content: center; align-items: center; border: 2px solid white; }

        /* --- USER DROPDOWN --- */
        .user-menu-container { position: relative; }
        .user-avatar { width: 40px; height: 40px; border-radius: 50%; object-fit: cover; border: 2px solid var(--accent); cursor: pointer; }
        .user-dropdown {
            display: none; position: absolute; top: 55px; right: 0; background: white;
            box-shadow: var(--shadow); border-radius: 8px; width: 220px; padding: 5px; z-index: 101; animation: slideDown 0.2s;
        }
        .user-dropdown button { width: 100%; text-align: left; padding: 12px; border: none; background: none; cursor: pointer; border-radius: 6px; color: var(--text-dark); font-size: 0.9rem; display: flex; align-items: center; gap: 10px; }
        .user-dropdown button:hover { background: #f0f0f0; }
        .user-dropdown button.logout { color: var(--danger); }

        /* --- PAGE SECTIONS --- */
        .section { display: none; animation: fadeIn 0.4s ease; }
        .section.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes slideDown { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }

        .page-title { text-align: center; margin-bottom: 25px; font-size: 1.8rem; color: var(--primary); font-weight: 700; }

        /* --- PRODUCT GRID --- */
        .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 20px; }
        .card { background: var(--white); border-radius: var(--radius); overflow: hidden; box-shadow: var(--shadow); transition: 0.3s; display: flex; flex-direction: column; }
        .card:hover { transform: translateY(-5px); box-shadow: 0 12px 40px rgba(0,0,0,0.12); }
        .card-img { width: 100%; height: 200px; object-fit: cover; background: #eee; }
        .card-body { padding: 15px; flex-grow: 1; display: flex; flex-direction: column; }
        .card-title { font-weight: 700; font-size: 1.1rem; margin-bottom: 5px; color: var(--primary); }
        .card-desc { font-size: 0.85rem; color: var(--gray); margin-bottom: 15px; flex-grow: 1; }
        .card-price { font-size: 1.2rem; color: var(--accent); font-weight: 700; margin-bottom: 10px; }
        .card-price small { font-size: 0.8rem; color: #999; font-weight: 400; }

        /* --- WALLET LIST --- */
        .wallet-item { display: flex; justify-content: space-between; align-items: center; background: white; padding: 15px; border-radius: 12px; margin-bottom: 12px; border: 1px solid #eee; }
        .wallet-info { display: flex; align-items: center; gap: 15px; }
        .wallet-icon { width: 45px; height: 45px; border-radius: 10px; display: flex; justify-content: center; align-items: center; color: white; font-size: 1.2rem; }
        .gopay { background: #00AED6; } .ovo { background: #4C3494; } .dana { background: #118EEA; } .bca { background: #0056C3; }

        /* --- PROFILE --- */
        .profile-header { text-align: center; background: white; padding: 30px; border-radius: 12px; margin-bottom: 20px; }
        .profile-img-lg { width: 100px; height: 100px; border-radius: 50%; border: 4px solid var(--gold); margin-bottom: 10px; object-fit: cover; }
        .points-card { background: linear-gradient(135deg, #f1c40f 0%, #f39c12 100%); color: white; padding: 15px; border-radius: 12px; margin: 15px 0; display: flex; justify-content: space-between; align-items: center; }
        .points-val { font-size: 1.5rem; font-weight: 800; }
        .detail-row { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #eee; }
        
        /* --- MODALS --- */
        .modal-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.7); z-index: 1000; display: none; justify-content: center; align-items: center; backdrop-filter: blur(4px); }
        .modal { background: white; padding: 30px; border-radius: 16px; width: 90%; max-width: 500px; max-height: 90vh; overflow-y: auto; position: relative; animation: slideUp 0.3s; }
        @keyframes slideUp { from { transform: translateY(30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        .close-btn { position: absolute; top: 15px; right: 20px; font-size: 1.5rem; cursor: pointer; color: #aaa; }
        .close-btn:hover { color: var(--primary); }

        /* --- FORMS --- */
        .form-group { margin-bottom: 15px; text-align: left; }
        label { display: block; font-weight: 600; margin-bottom: 5px; font-size: 0.9rem; color: #555; }
        input, select, textarea { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 8px; font-size: 0.95rem; outline: none; }
        input:focus { border-color: var(--accent); }

        /* --- CUSTOM OPTIONS --- */
        .custom-section { margin-bottom: 20px; border-bottom: 1px solid #eee; padding-bottom: 15px; }
        .custom-section h4 { color: var(--gray); font-size: 0.85rem; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 10px; }
        .options-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); gap: 10px; }
        .option-card { border: 1px solid #ddd; border-radius: 8px; padding: 10px; cursor: pointer; transition: 0.2s; position: relative; }
        .option-card:hover { border-color: var(--accent); background: #fff8f0; }
        .option-card.selected { border-color: var(--accent); background: #fff3cd; box-shadow: 0 0 0 1px var(--accent); }
        .opt-name { font-size: 0.9rem; font-weight: 600; margin-bottom: 4px; }
        .opt-price { font-size: 0.8rem; color: var(--accent); }

        /* --- CART & CHECKOUT --- */
        .cart-item { display: flex; align-items: center; justify-content: space-between; padding: 10px 0; border-bottom: 1px solid #eee; }
        .qty-box { display: flex; align-items: center; gap: 10px; background: #f5f5f5; padding: 4px 8px; border-radius: 20px; }
        .qty-btn { width: 24px; height: 24px; border-radius: 50%; border: none; background: white; cursor: pointer; font-weight: bold; color: var(--primary); box-shadow: 0 1px 3px rgba(0,0,0,0.1); display: flex; justify-content: center; align-items: center; }

        /* Points Toggle Switch */
        .switch-container { background: #fff8e1; padding: 15px; border-radius: 8px; display: flex; justify-content: space-between; align-items: center; margin: 15px 0; border: 1px solid #ffeeba; }
        .switch { position: relative; display: inline-block; width: 44px; height: 24px; }
        .switch input { opacity: 0; width: 0; height: 0; }
        .slider { position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; background-color: #ccc; transition: .4s; border-radius: 34px; }
        .slider:before { position: absolute; content: ""; height: 18px; width: 18px; left: 3px; bottom: 3px; background-color: white; transition: .4s; border-radius: 50%; }
        input:checked + .slider { background-color: var(--gold); }
        input:checked + .slider:before { transform: translateX(20px); }

        /* QRIS */
        .qris-area { text-align: center; margin: 15px 0; padding: 20px; background: #f9f9f9; border-radius: 8px; border: 2px dashed #ccc; }

        /* --- MOBILE NAV --- */
        .mobile-nav { position: fixed; bottom: 0; left: 0; width: 100%; background: white; display: none; justify-content: space-around; padding: 12px 10px; border-top: 1px solid #eee; box-shadow: 0 -2px 10px rgba(0,0,0,0.05); z-index: 99; }
        .mn-item { text-align: center; color: #bbb; cursor: pointer; flex: 1; font-size: 0.75rem; }
        .mn-item i { display: block; font-size: 1.3rem; margin-bottom: 4px; margin-bottom: 5px; }
        .mn-item.active { color: var(--accent); }

        /* --- TOAST --- */
        .toast { position: fixed; bottom: 90px; left: 50%; transform: translateX(-50%); background: rgba(44, 62, 80, 0.95); color: white; padding: 12px 24px; border-radius: 30px; font-size: 0.9rem; z-index: 2000; opacity: 0; transition: 0.3s; pointer-events: none; white-space: nowrap; }
        .toast.show { opacity: 1; bottom: 100px; }

        @media (max-width: 768px) {
            header nav { display: none; }
            .mobile-nav { display: flex; }
            .container { padding: 15px; }
        }
    </style>
</head>
<body>

    <!-- TOAST NOTIFICATION -->
    <div id="toast" class="toast">Pesan notifikasi</div>

    <!-- HEADER -->
    <header>
        <a href="#" onclick="navTo('menu')" class="logo">
            <i class="fas fa-circle-notch"></i> D'Glaze <span>Premium</span>
        </a>
        
        <nav>
            <ul>
                <li><a href="#" onclick="navTo('menu', this)" class="active">Menu</a></li>
                <li><a href="#" onclick="navTo('wallet', this)">Dompet</a></li>
                <li><a href="#" onclick="navTo('location', this)">Lokasi</a></li>
                <li><a href="#" onclick="navTo('orders', this)">Pesanan</a></li>
            </ul>
        </nav>

        <div class="header-actions">
            <div class="cart-btn" onclick="openCart()">
                <i class="fas fa-shopping-bag"></i>
                <div class="cart-badge" id="cart-badge">0</div>
            </div>
            
            <!-- Guest State -->
            <button id="btn-login-guest" class="btn btn-primary" onclick="showLoginModal()" style="padding: 8px 16px; font-size: 0.8rem;">Masuk</button>
            
            <!-- Logged In State -->
            <div id="user-area" class="user-menu-container" style="display: none;">
                <img src="" id="header-avatar" class="user-avatar" onclick="toggleUserMenu()">
                <div id="user-dropdown" class="user-dropdown">
                    <button onclick="navTo('profile'); toggleUserMenu();"><i class="fas fa-user-circle"></i> Profil Saya</button>
                    <button onclick="navTo('wallet'); toggleUserMenu();"><i class="fas fa-wallet"></i> Dompet</button>
                    <button class="logout" onclick="doLogout()"><i class="fas fa-sign-out-alt"></i> Keluar</button>
                </div>
            </div>
        </div>
    </header>

    <!-- MAIN CONTENT -->
    <main class="container">

        <!-- 1. MENU PAGE -->
        <section id="page-menu" class="section active">
            <h2 class="page-title">Menu Favorit</h2>
            <div class="grid" id="product-grid">
                <!-- Items injected by JS -->
            </div>
        </section>

        <!-- 2. WALLET PAGE -->
        <section id="page-wallet" class="section">
            <h2 class="page-title">Metode Pembayaran</h2>
            <div class="card" style="padding: 20px; margin-bottom: 20px; border-left: 5px solid var(--accent);">
                <h3>Hubungkan E-Wallet / Kartu</h3>
                <p style="color:#666; font-size:0.9rem; margin-bottom:10px;">Simpan kartu untuk pembayaran cepat.</p>
                <button class="btn btn-gold" onclick="openAddWalletModal()"><i class="fas fa-plus"></i> Tambah Baru</button>
            </div>
            <div id="wallet-list">
                <!-- Wallets injected by JS -->
            </div>
        </section>

        <!-- 3. LOCATION PAGE -->
        <section id="page-location" class="section">
            <h2 class="page-title">Lokasi Kami</h2>
            <div class="card" style="padding:0; overflow:hidden; margin-bottom:20px;">
                <div style="padding:15px; border-bottom:1px solid #eee;">
                    <h3 style="color:var(--accent);"><i class="fas fa-map-marker-alt"></i> Jakarta Timur</h3>
                    <p style="font-size:0.9rem; margin-top:5px;">Jl. Hj. Juhaman No. 12, Jakarta Timur</p>
                    <p style="color:var(--gray); font-size:0.8rem;">08:00 - 22:00 WIB</p>
                </div>
                <iframe width="100%" height="250" frameborder="0" style="border:0;" 
                src="https://maps.google.com/maps?q=Jl.+Hj+Juhaman,+Jakarta+Timur&t=&z=15&ie=UTF8&iwloc=&output=embed"></iframe>
            </div>
            
            <div class="card" style="padding:0; overflow:hidden;">
                <div style="padding:15px; border-bottom:1px solid #eee;">
                    <h3 style="color:var(--accent);"><i class="fas fa-map-marker-alt"></i> Bekasi</h3>
                    <p style="font-size:0.9rem; margin-top:5px;">Perumahan Puri Nusaphala, Kota Bekasi</p>
                    <p style="color:var(--gray); font-size:0.8rem;">08:00 - 22:00 WIB</p>
                </div>
                <iframe width="100%" height="250" frameborder="0" style="border:0;" 
                src="https://maps.google.com/maps?q=Perumahan+Puri+Nusaphala,+Kota+Bekasi&t=&z=15&ie=UTF8&iwloc=&output=embed"></iframe>
            </div>
        </section>

        <!-- 4. PROFILE PAGE -->
        <section id="page-profile" class="section">
            <h2 class="page-title">Profil Saya</h2>
            <div class="profile-header">
                <img src="" id="prof-img" class="profile-img-lg">
                <h3 id="prof-name">Nama User</h3>
                <p id="prof-email" style="color:#666;">email@example.com</p>
                
                <div class="points-card">
                    <div>
                        <div style="font-size:0.8rem; opacity:0.9;">Poin Tersedia</div>
                        <div class="points-val" id="prof-points">0</div>
                    </div>
                    <i class="fas fa-coins fa-2x" style="opacity:0.5;"></i>
                </div>

                <button class="btn btn-outline" onclick="openEditProfileModal()"><i class="fas fa-edit"></i> Edit Profil</button>
            </div>

            <div class="card" style="padding:20px;">
                <div class="detail-row">
                    <span>No HP</span>
                    <strong id="disp-phone">-</strong>
                </div>
                <div class="detail-row">
                    <span>Alamat</span>
                    <strong id="disp-address">-</strong>
                </div>
                <div class="detail-row" style="border:none;">
                    <span>Detail Patokan</span>
                    <strong id="disp-detail">-</strong>
                </div>
            </div>
        </section>

        <!-- 5. ORDERS PAGE -->
        <section id="page-orders" class="section">
            <h2 class="page-title">Riwayat Pesanan</h2>
            <div id="orders-list">
                <!-- Orders injected by JS -->
            </div>
        </section>

    </main>

    <!-- MOBILE NAV -->
    <div class="mobile-nav">
        <div class="mn-item active" onclick="navTo('menu')"><i class="fas fa-utensils"></i>Menu</div>
        <div class="mn-item" onclick="navTo('wallet')"><i class="fas fa-wallet"></i>Dompet</div>
        <div class="mn-item" onclick="navTo('location')"><i class="fas fa-map-marked-alt"></i>Lokasi</div>
        <div class="mn-item" onclick="navTo('profile')"><i class="fas fa-user"></i>Profil</div>
        <div class="mn-item" onclick="navTo('orders')"><i class="fas fa-receipt"></i>Pesanan</div>
    </div>

    <!-- MODAL: LOGIN -->
    <div id="modal-login" class="modal-overlay">
        <div class="modal" style="text-align: center;">
            <span class="close-btn" onclick="closeModal('modal-login')">&times;</span>
            <h2>Selamat Datang</h2>
            <p style="margin-bottom:20px; color:#666;">Masuk untuk mulai pesan donatmu.</p>
            <div style="display:grid; gap:10px;">
                <button class="btn btn-outline" style="border-color:#ddd;" onclick="doLogin('google')"><i class="fab fa-google"></i> Masuk dengan Google</button>
                <button class="btn btn-outline" style="border-color:#ddd;" onclick="doLogin('facebook')"><i class="fab fa-facebook-f"></i> Masuk dengan Facebook</button>
                <button class="btn btn-outline" style="border-color:#ddd;" onclick="doLogin('email')"><i class="fas fa-envelope"></i> Masuk dengan Email</button>
            </div>
        </div>
    </div>

    <!-- MODAL: SETUP PROFILE (FIRST TIME) -->
    <div id="modal-setup" class="modal-overlay">
        <div class="modal">
            <span class="close-btn" onclick="closeModal('modal-setup')">&times;</span>
            <h3>Lengkapi Data Diri</h3>
            <p style="font-size:0.85rem; color:#666; margin-bottom:15px;">Data ini diperlukan untuk pengiriman.</p>
            
            <div class="form-group">
                <label>Nomor WhatsApp</label>
                <input type="tel" id="setup-phone" placeholder="0812...">
            </div>
            <div class="form-group">
                <label>Alamat Lengkap</label>
                <textarea id="setup-address" rows="2" placeholder="Nama Jalan, No Rumah..."></textarea>
            </div>
