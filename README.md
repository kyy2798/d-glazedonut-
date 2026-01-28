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
            <div class="form-group">
                <label>Patokan / Detail</label>
                <input type="text" id="setup-detail" placeholder="Pagar hitam, sebelah warung...">
            </div>
            <button class="btn btn-primary" style="width:100%;" onclick="saveSetupProfile()">Simpan & Lanjut</button>
        </div>
    </div>

    <!-- MODAL: EDIT PROFILE -->
    <div id="modal-edit-profile" class="modal-overlay">
        <div class="modal">
            <span class="close-btn" onclick="closeModal('modal-edit-profile')">&times;</span>
            <h3>Edit Profil</h3>
            <div class="form-group">
                <label>Nomor WhatsApp</label>
                <input type="tel" id="edit-phone">
            </div>
            <div class="form-group">
                <label>Alamat Lengkap</label>
                <textarea id="edit-address" rows="2"></textarea>
            </div>
            <div class="form-group">
                <label>Patokan / Detail</label>
                <input type="text" id="edit-detail">
            </div>
            <button class="btn btn-primary" style="width:100%;" onclick="saveEditProfile()">Update Data</button>
        </div>
    </div>

    <!-- MODAL: ADD WALLET -->
    <div id="modal-add-wallet" class="modal-overlay">
        <div class="modal">
            <span class="close-btn" onclick="closeModal('modal-add-wallet')">&times;</span>
            <h3>Tambah Metode Bayar</h3>
            <div class="form-group">
                <label>Tipe E-Wallet / Bank</label>
                <select id="wallet-type">
                    <option value="gopay">GoPay</option>
                    <option value="ovo">OVO</option>
                    <option value="dana">DANA</option>
                    <option value="bca">BCA</option>
                </select>
            </div>
            <div class="form-group">
                <label id="wallet-label">Nomor Akun</label>
                <input type="text" id="wallet-number" placeholder="08xx...">
            </div>
            <button class="btn btn-primary" style="width:100%;" onclick="saveWallet()">Hubungkan</button>
        </div>
    </div>

    <!-- MODAL: CUSTOM DONUT -->
    <div id="modal-custom" class="modal-overlay">
        <div class="modal" style="max-width:600px;">
            <span class="close-btn" onclick="closeModal('modal-custom')">&times;</span>
            <h3 style="text-align:center; margin-bottom:5px;">Buat Donat Custom</h3>
            <p style="text-align:center; color:#666; font-size:0.9rem; margin-bottom:20px;">Pilih glaze dan topping favoritmu.</p>
            
            <div style="max-height:60vh; overflow-y:auto; padding-right:5px;">
                <!-- Glaze Section -->
                <div class="custom-section">
                    <h4>1. Pilih Glaze (Wajib Satu)</h4>
                    <div class="options-grid" id="glaze-options"></div>
                </div>

                <!-- Topping Section -->
                <div class="custom-section" style="border:none;">
                    <h4>2. Pilih Topping (Boleh Banyak)</h4>
                    <div class="options-grid" id="topping-options"></div>
                </div>
            </div>

            <div style="display:flex; justify-content:space-between; align-items:center; margin-top:20px; padding-top:15px; border-top:1px solid #eee;">
                <div>
                    <small>Total Harga</small>
                    <div style="font-size:1.5rem; font-weight:800; color:var(--accent);" id="custom-total-display">Rp 8.000</div>
                </div>
                <button class="btn btn-primary" onclick="addCustomToCart()">Masuk Keranjang</button>
            </div>
        </div>
    </div>

    <!-- MODAL: CART & CHECKOUT -->
    <div id="modal-cart" class="modal-overlay">
        <div class="modal">
            <span class="close-btn" onclick="closeModal('modal-cart')">&times;</span>
            <h3 style="margin-bottom:15px;">Keranjang Belanja</h3>
            
            <div id="cart-items-container" style="max-height:250px; overflow-y:auto; border-bottom:1px solid #eee; padding-bottom:15px; margin-bottom:15px;">
                <!-- Cart items JS -->
            </div>

            <!-- POINTS LOGIC -->
            <div class="switch-container">
                <div>
                    <div style="font-weight:600;">Gunakan Poin?</div>
                    <small id="points-hint-text">Poin Anda: 0 (100 Poin = Diskon Rp 10.000)</small>
                </div>
                <label class="switch">
                    <input type="checkbox" id="use-points-toggle" onchange="calcCheckout()">
                    <span class="slider"></span>
                </label>
            </div>

            <div style="text-align:right; margin-bottom:15px;">
                <div style="font-size:1.4rem; font-weight:700; color:var(--primary);" id="checkout-total">Rp 0</div>
                <small id="discount-label" style="color:var(--danger); display:none;">Hemat Rp 0</small>
            </div>

            <!-- PAYMENT AREA (Hidden initially) -->
            <div id="payment-area" style="display:none; background:#f9f9f9; padding:15px; border-radius:8px;">
                <div class="form-group">
                    <label>Metode Pembayaran</label>
                    <select id="payment-method" onchange="handlePaymentSelect()">
                        <option value="">-- Pilih --</option>
                        <option value="QRIS">QRIS (Scan Barcode)</option>
                        <option value="WALLET">E-Wallet / Kartu Tersimpan</option>
                        <option value="MANUAL">Transfer Bank Manual</option>
                    </select>
                </div>

                <!-- QRIS UI -->
                <div id="pay-qris" style="display:none;" class="qris-area">
                    <p style="margin-bottom:10px; font-weight:600;">Scan QRIS di bawah ini:</p>
                    <img id="qris-img" src="" alt="QRIS" style="width:180px; height:180px; border-radius:8px;">
                    <p style="font-size:0.8rem; color:#666; margin-top:5px;">Berlaku untuk GoPay, OVO, Dana, Mobile Banking.</p>
                </div>

                <!-- WALLET LIST UI -->
                <div id="pay-wallet" style="display:none;">
                    <div id="checkout-wallet-list" style="display:grid; gap:8px; margin-bottom:10px;"></div>
                </div>

                <!-- MANUAL UI -->
                <div id="pay-manual" style="display:none; font-size:0.9rem; text-align:center; background:white; padding:10px; border:1px dashed #ccc; border-radius:8px;">
                    <p>Transfer ke <strong>BCA 123-456-7890</strong> a.n D'Glaze.</p>
                </div>

                <button id="btn-pay" class="btn btn-accent" style="width:100%; margin-top:15px; display:none;" onclick="processPayment()">Bayar Sekarang</button>
            </div>

            <button id="btn-checkout" class="btn btn-primary" style="width:100%;" onclick="goToPayment()">Lanjut Pembayaran</button>
        </div>
    </div>

    <script>
        // --- DATA & CONFIG ---
        const BASE_PRICE = 8000;
        
        // UPDATED COMBOS: SEMUA GAMBAR .JPG
        const COMBOS = [
            { id: 'c1', name: "Choco Bomb", price: 13000, desc: "Donat cokelat lumer dengan topping cokelat chips.", img: "chocobomb.jpg" },
            { id: 'c2', name: "Berry Bliss", price: 13500, desc: "Glaze stroberi dengan potongan buah segar.", img: "berrybliss.jpg" },
            { id: 'c3', name: "Matcha Crunch", price: 14000, desc: "Glaze matcha jepang dengan almond.", img: "matchaalmond.jpg" },
            { id: 'c4', name: "Tiramisu", price: 15000, desc: "Rasa kopi kuat dengan bubuk kakao.", img: "tiramisu.jpg" },

            // MENU LAINNYA (Placeholder images)
            { id: 'c5', name: "Cheese Meses", price: 11000, desc: "Glaze gula original dengan meses cokelat dan keju parut.", img: "cheesemeises.jpg" },
            { id: 'c6', name: "Choco Cashew", price: 16000, desc: "Glaze cokelat tebal dengan kacang mete dan remahan oreo.", img: "chocolate.jpg" },
            { id: 'c7', name: "White Berry", price: 15000, desc: "Glaze cokelat putih manis dengan oreo dan stroberi segar.", img: "whitechocolateberry.jpg" },
            { id: 'c8', name: "Banana Split", price: 13000, desc: "Glaze stroberi dengan potongan pisang dan sprinkles ceria.", img: "strawberry.jpg" },
            { id: 'c9', name: "Blueberry Crunch", price: 13500, desc: "Glaze blueberry asam manis dengan sereal dan white choco chips.", img: "blueberry.jpg" },
            { id: 'c10', name: "Salted Caramel Pecan", price: 16000, desc: "Caramel asin gurih dengan kacang mete dan choco chips.", img: "caramelpecan.jpg" },
            { id: 'c11', name: "Double Cheese", price: 15000, desc: "Double keju (glaze & parut) dengan topping oreo crunchy.", img: "doublecheese.jpg" }
        ];

        const GLAZES = [
            { name: "Gula Original", price: 0 },
            { name: "Chocolate Glaze", price: 2000 },
            { name: "White Chocolate", price: 2000 },
            { name: "Strawberry Glaze", price: 2000 },
            { name: "Matcha Glaze", price: 3000 },
            { name: "Blueberry Glaze", price: 2500 },
            { name: "Caramel Sea Salt", price: 2500 },
            { name: "Cheese Glaze", price: 3000 }
        ];

        // Updated Toppings with White Choco Chips
        const TOPPINGS = [
            { name: "Meses Cokelat", price: 1000 },
            { name: "Sprinkles", price: 1000 },
            { name: "Oreo Crumbs", price: 2000 },
            { name: "Choco Chips", price: 1500 },
            { name: "Keju Parut", price: 2000 },
            { name: "Kacang Almond", price: 3000 },
            { name: "Kacang Mete", price: 4000 },
            { name: "Sereal", price: 1500 },
            { name: "Potongan Strawberry", price: 3000 },
            { name: "Potongan Pisang", price: 2000 },
            { name: "White Choco Chips", price: 1500 }
        ];

        // --- STATE MANAGEMENT ---
        let user = JSON.parse(localStorage.getItem('dg_user')) || null;
        let cart = JSON.parse(localStorage.getItem('dg_cart')) || [];
        let orders = JSON.parse(localStorage.getItem('dg_orders')) || [];

        // --- INIT ---
        window.onload = function() {
            renderMenu();
            checkAuth();
            updateCartBadge();
        };

        // --- NAVIGATION ---
        function navTo(pageId, el) {
            // Hide all sections
            document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
            // Show target
            document.getElementById('page-' + pageId).classList.add('active');
            
            // Desktop Nav Active State
            if(el) {
                document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
                el.classList.add('active');
            } else if (pageId === 'menu') {
                document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
                document.querySelector('nav a:first-child').classList.add('active');
            }

            // Mobile Nav Active State
            document.querySelectorAll('.mn-item').forEach(i => i.classList.remove('active'));
            const mapMn = { 'menu':0, 'wallet':1, 'location':2, 'profile':3, 'orders':4 };
            if(document.querySelectorAll('.mn-item')[mapMn[pageId]]) {
                document.querySelectorAll('.mn-item')[mapMn[pageId]].classList.add('active');
            }

            if(pageId === 'wallet') renderWallets();
            if(pageId === 'orders') renderOrders();
            if(pageId === 'profile') renderProfile();
        }

        function showToast(msg) {
            const t = document.getElementById('toast');
            t.innerText = msg;
            t.classList.add('show');
            setTimeout(() => t.classList.remove('show'), 3000);
        }

        function closeModal(id) { document.getElementById(id).style.display = 'none'; }
        function openModal(id) { document.getElementById(id).style.display = 'flex'; }

        // --- AUTH SYSTEM ---
        function checkAuth() {
            const guestBtn = document.getElementById('btn-login-guest');
            const userArea = document.getElementById('user-area');
            if(user) {
                guestBtn.style.display = 'none';
                userArea.style.display = 'block';
                document.getElementById('header-avatar').src = user.avatar;
            } else {
                guestBtn.style.display = 'block';
                userArea.style.display = 'none';
            }
        }

        function toggleUserMenu() {
            const dd = document.getElementById('user-dropdown');
            dd.style.display = (dd.style.display === 'block') ? 'none' : 'block';
        }

        function showLoginModal() { openModal('modal-login'); }
        
        function doLogin(provider) {
            // Simulating Login
            user = {
                name: "Pelanggan Baru",
                email: `user@${provider}.com`,
                phone: "",
                address: "",
                detail: "",
                points: 0, // Starting points
                wallets: [],
                avatar: `https://ui-avatars.com/api/?name=Pelanggan+Baru&background=e67e22&color=fff`
            };
            saveUser();
            closeModal('modal-login');
            checkAuth();
            showToast("Login Berhasil!");
            
            // Check if profile complete
            if(!user.phone || !user.address) {
                setTimeout(() => openModal('modal-setup'), 500);
            }
        }

        function doLogout() {
            if(confirm("Keluar akun?")) {
                user = null;
                cart = [];
                saveUser();
                saveCart();
                checkAuth();
                navTo('menu');
                showToast("Berhasil Keluar");
                document.getElementById('user-dropdown').style.display = 'none';
            }
        }

        function saveUser() { localStorage.setItem('dg_user', JSON.stringify(user)); }

        // --- PROFILE ---
        function saveSetupProfile() {
            user.phone = document.getElementById('setup-phone').value;
            user.address = document.getElementById('setup-address').value;
            user.detail = document.getElementById('setup-detail').value;
            saveUser();
            closeModal('modal-setup');
            renderProfile();
            showToast("Profil Tersimpan!");
        }

        function openEditProfileModal() {
            document.getElementById('edit-phone').value = user.phone || '';
            document.getElementById('edit-address').value = user.address || '';
            document.getElementById('edit-detail').value = user.detail || '';
            openModal('modal-edit-profile');
        }

        function saveEditProfile() {
            user.phone = document.getElementById('edit-phone').value;
            user.address = document.getElementById('edit-address').value;
            user.detail = document.getElementById('edit-detail').value;
            saveUser();
            closeModal('modal-edit-profile');
            renderProfile();
            showToast("Profil Diupdate!");
        }

        function renderProfile() {
            document.getElementById('prof-img').src = user.avatar;
            document.getElementById('prof-name').innerText = user.name;
            document.getElementById('prof-email').innerText = user.email;
            document.getElementById('prof-points').innerText = user.points.toLocaleString();
            document.getElementById('disp-phone').innerText = user.phone || '-';
            document.getElementById('disp-address').innerText = user.address || '-';
            document.getElementById('disp-detail').innerText = user.detail || '-';
        }

        // --- WALLET ---
        function openAddWalletModal() { openModal('modal-add-wallet'); }
        
        function saveWallet() {
            const type = document.getElementById('wallet-type').value;
            const num = document.getElementById('wallet-number').value;
            if(!num) return alert("Nomor harus diisi");
            
            user.wallets.push({ type, num });
            saveUser();
            closeModal('modal-add-wallet');
            renderWallets();
            showToast("Metode Bayar Ditambahkan");
        }

        function renderWallets() {
            const container = document.getElementById('wallet-list');
            if(user.wallets.length === 0) {
                container.innerHTML = '<p style="text-align:center; color:#999;">Belum ada metode bayar.</p>';
                return;
            }
            container.innerHTML = user.wallets.map((w, i) => `
                <div class="wallet-item">
                    <div class="wallet-info">
                        <div class="wallet-icon ${w.type}">
                            <i class="fas fa-wallet"></i>
                        </div>
                        <div>
                            <strong style="text-transform:uppercase;">${w.type}</strong><br>
                            <span style="color:#666;">${w.num}</span>
                        </div>
                    </div>
                    <button style="border:none; background:none; color:var(--danger); cursor:pointer;" onclick="deleteWallet(${i})"><i class="fas fa-trash"></i></button>
                </div>
            `).join('');
        }

        function deleteWallet(idx) {
            if(confirm("Hapus kartu ini?")) {
                user.wallets.splice(idx, 1);
                saveUser();
                renderWallets();
            }
        }

        // --- MENU & CUSTOM ---
        function renderMenu() {
            const container = document.getElementById('product-grid');
            let html = COMBOS.map(c => `
                <div class="card">
                    <img src="${c.img}" class="card-img" alt="${c.name}">
                    <div class="card-body">
                        <div class="card-title">${c.name}</div>
                        <div class="card-desc">${c.desc}</div>
                        <div class="card-price">Rp ${c.price.toLocaleString()}</div>
                        <button class="btn btn-primary" onclick="addToCart('${c.name}', ${c.price})">Pesan</button>
                    </div>
                </div>
            `).join('');

            // Custom Card
            html += `
                <div class="card" style="border: 2px dashed var(--accent); background:#fffdf5;">
                    <div class="card-img" style="height:200px; display:flex; align-items:center; justify-content:center; background:#fff8f0; flex-direction:column;">
                        <i class="fas fa-magic fa-3x" style="color:var(--accent); margin-bottom:10px;"></i>
                        <span style="font-weight:bold; color:var(--accent);">Custom Donut</span>
                    </div>
                    <div class="card-body">
                        <div class="card-title">Buat Sendiri</div>
                        <div class="card-desc">Pilih glaze dan topping sesukamu.</div>
                        <div class="card-price">Mulai <small>Rp 8.000</small></div>
                        <button class="btn btn-accent" onclick="openCustomModal()">Buat Custom</button>
                    </div>
                </div>
            `;
            container.innerHTML = html;
        }

        // Custom Logic
        let tempCustom = { glazeIdx: 0, toppingIdxs: [], total: 8000 };

        function openCustomModal() {
            if(!user) return showLoginModal();
            
            // Render Glazes
            const glazeContainer = document.getElementById('glaze-options');
            glazeContainer.innerHTML = GLAZES.map((g, i) => `
                <div class="option-card ${i===0?'selected':''}" onclick="selectGlaze(${i}, this)">
                    <div class="opt-name">${g.name}</div>
                    <div class="opt-price">${g.price > 0 ? '+Rp '+g.price.toLocaleString() : 'Gratis'}</div>
                </div>
            `).join('');

            // Render Toppings
            const toppingContainer = document.getElementById('topping-options');
            toppingContainer.innerHTML = TOPPINGS.map((t, i) => `
                <div class="option-card" id="top-opt-${i}" onclick="toggleTopping(${i})">
                    <div class="opt-name">${t.name}</div>
                    <div class="opt-price">+Rp ${t.price.toLocaleString()}</div>
                </div>
            `).join('');

            // Reset State
            tempCustom = { glazeIdx: 0, toppingIdxs: [], total: 8000 };
            updateCustomTotal();
            openModal('modal-custom');
        }

        function selectGlaze(idx, el) {
            document.querySelectorAll('#glaze-options .option-card').forEach(c => c.classList.remove('selected'));
            el.classList.add('selected');
            tempCustom.glazeIdx = idx;
            updateCustomTotal();
        }

        function toggleTopping(idx) {
            const el = document.getElementById('top-opt-'+idx);
            const pos = tempCustom.toppingIdxs.indexOf(idx);
            if(pos > -1) {
                tempCustom.toppingIdxs.splice(pos, 1);
                el.classList.remove('selected');
            } else {
                tempCustom.toppingIdxs.push(idx);
                el.classList.add('selected');
            }
            updateCustomTotal();
        }

        function updateCustomTotal() {
            let total = BASE_PRICE;
            total += GLAZES[tempCustom.glazeIdx].price;
            tempCustom.toppingIdxs.forEach(i => {
                total += TOPPINGS[i].price;
            });
            tempCustom.total = total;
            document.getElementById('custom-total-display').innerText = 'Rp ' + total.toLocaleString();
        }

        function addCustomToCart() {
            // Create name string
            const gName = GLAZES[tempCustom.glazeIdx].name;
            const tNames = tempCustom.toppingIdxs.map(i => TOPPINGS[i].name).join(', ');
            const fullName = `Custom (${gName}${tNames ? ', '+tNames : ''})`;
            
            addToCart(fullName, tempCustom.total);
            closeModal('modal-custom');
        }

        // --- CART LOGIC ---
        function addToCart(name, price) {
            const exist = cart.find(item => item.name === name);
            if(exist) {
                exist.qty++;
            } else {
                cart.push({ name, price, qty: 1 });
            }
            saveCart();
            updateCartBadge();
            showToast("Masuk Keranjang!");
        }

        function saveCart() { localStorage.setItem('dg_cart', JSON.stringify(cart)); }
        function updateCartBadge() {
            const count = cart.reduce((a, b) => a + b.qty, 0);
            document.getElementById('cart-badge').innerText = count;
        }

        function openCart() {
            if(!user) return showLoginModal();
            renderCartItems();
            // Reset payment view
            document.getElementById('payment-area').style.display = 'none';
            document.getElementById('btn-checkout').style.display = 'block';
            // Recalculate totals
            calcCheckout();
            openModal('modal-cart');
        }

        function renderCartItems() {
            const container = document.getElementById('cart-items-container');
            if(cart.length === 0) {
                container.innerHTML = '<p style="text-align:center; padding:20px; color:#999;">Keranjang kosong.</p>';
                return;
            }
            container.innerHTML = cart.map((item, i) => `
                <div class="cart-item">
                    <div style="flex:1;">
                        <strong>${item.name}</strong><br>
                        <small>Rp ${item.price.toLocaleString()}</small>
                    </div>
                    <div class="qty-box">
                        <button class="qty-btn" onclick="updateQty(${i}, -1)">-</button>
                        <span>${item.qty}</span>
                        <button class="qty-btn" onclick="updateQty(${i}, 1)">+</button>
                    </div>
                </div>
            `).join('');
        }

        function updateQty(idx, change) {
            cart[idx].qty += change;
            if(cart[idx].qty <= 0) cart.splice(idx, 1);
            saveCart();
            renderCartItems();
            updateCartBadge();
            calcCheckout(); // Re-calc totals
        }

        // --- CHECKOUT & POINTS LOGIC ---
        let finalBill = 0;
        let pointsUsed = 0;

        function calcCheckout() {
            const subtotal = cart.reduce((a, b) => a + (b.price * b.qty), 0);
            const usePoints = document.getElementById('use-points-toggle').checked;
            
            // Update hint text
            document.getElementById('points-hint-text').innerText = `Poin Anda: ${user.points} (100 Poin = Diskon Rp 10.000)`;

            if(usePoints && user.points >= 100) {
                // Calculate Redeemable Discount
                // Logic: Every 100 points = 10,000 discount
                const setsOf100 = Math.floor(user.points / 100);
                let discount = setsOf100 * 10000;

                if(discount > subtotal) {
                    discount = subtotal; // Max discount is total price
                }

                pointsUsed = setsOf100 * 100; // Points consumed
                finalBill = subtotal - discount;
                
                document.getElementById('discount-label').style.display = 'block';
                document.getElementById('discount-label').innerText = `Hemat Rp ${discount.toLocaleString()} (${pointsUsed} Poin)`;
            } else {
                pointsUsed = 0;
                finalBill = subtotal;
                document.getElementById('discount-label').style.display = 'none';
            }

            document.getElementById('checkout-total').innerText = 'Rp ' + finalBill.toLocaleString();
        }

        function goToPayment() {
            if(cart.length === 0) return showToast("Keranjang kosong!");
            document.getElementById('btn-checkout').style.display = 'none';
            document.getElementById('payment-area').style.display = 'block';
            // Reset Payment UI
            document.getElementById('payment-method').value = "";
            document.getElementById('pay-qris').style.display = 'none';
            document.getElementById('pay-wallet').style.display = 'none';
            document.getElementById('pay-manual').style.display = 'none';
            document.getElementById('btn-pay').style.display = 'none';
        }

        function handlePaymentSelect() {
            const method = document.getElementById('payment-method').value;
            document.getElementById('pay-qris').style.display = 'none';
            document.getElementById('pay-wallet').style.display = 'none';
            document.getElementById('pay-manual').style.display = 'none';
            document.getElementById('btn-pay').style.display = 'none';

            if(method === 'QRIS') {
                // Generate Fake QR based on total
                const dataStr = "DGLAZE-" + finalBill;
                document.getElementById('qris-img').src = `https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${dataStr}`;
                document.getElementById('pay-qris').style.display = 'block';
                document.getElementById('btn-pay').style.display = 'block';
            } else if(method === 'WALLET') {
                if(user.wallets.length === 0) {
                    alert("Belum ada dompet tersimpan. Silakan tambah di menu Dompet.");
                    document.getElementById('payment-method').value = "";
                    return;
                }
                const list = document.getElementById('checkout-wallet-list');
                list.innerHTML = user.wallets.map((w, i) => `
                    <button class="btn btn-outline" style="justify-content:flex-start;" onclick="selectWalletMethod(this)">
                        <i class="fas fa-wallet ${w.type}" style="margin-right:10px;"></i> ${w.type.toUpperCase()} - ${w.num}
                    </button>
                `).join('');
                document.getElementById('pay-wallet').style.display = 'block';
                document.getElementById('btn-pay').style.display = 'block';
            } else if(method === 'MANUAL') {
                document.getElementById('pay-manual').style.display = 'block';
                document.getElementById('btn-pay').style.display = 'block';
            }
        }

        function selectWalletMethod(btn) {
            document.querySelectorAll('#checkout-wallet-list button').forEach(b => {
                b.classList.remove('btn-primary');
                b.classList.add('btn-outline');
            });
            btn.classList.remove('btn-outline');
            btn.classList.add('btn-primary');
        }

        function processPayment() {
            const method = document.getElementById('payment-method').value;
            if(!method) return alert("Pilih metode pembayaran.");

            const btn = document.getElementById('btn-pay');
            btn.innerText = "Memproses...";
            btn.disabled = true;

            setTimeout(() => {
                // 1. Deduct Points
                user.points -= pointsUsed;
                
                // 2. Earn New Points (Rp 1 = 1 Point)
                const pointsEarned = Math.floor(finalBill);
                user.points += pointsEarned;
                saveUser();

                // 3. Save Order
                const newOrder = {
                    id: 'INV-' + Date.now().toString().slice(-4),
                    date: new Date().toLocaleDateString() + ' ' + new Date().toLocaleTimeString(),
                    items: [...cart],
                    total: finalBill,
                    payMethod: method,
                    pointsUsed: pointsUsed,
                    pointsEarned: pointsEarned
                };
                orders.unshift(newOrder);
                localStorage.setItem('dg_orders', JSON.stringify(orders));

                // 4. Clear Cart
                cart = [];
                saveCart();
                updateCartBadge();

                // 5. UI Feedback
                closeModal('modal-cart');
                showToast("Pembayaran Berhasil!");
                navTo('orders');
                renderOrders();

                // Reset Button
                btn.innerText = "Bayar Sekarang";
                btn.disabled = false;
            }, 1500);
        }

        function renderOrders() {
            const container = document.getElementById('orders-list');
            if(orders.length === 0) {
                container.innerHTML = '<p style="text-align:center; color:#999; margin-top:20px;">Belum ada riwayat pesanan.</p>';
                return;
            }
            container.innerHTML = orders.map(o => `
                <div class="card" style="padding:15px; margin-bottom:15px; border-left: 5px solid var(--primary);">
                    <div style="display:flex; justify-content:space-between; margin-bottom:10px;">
                        <span style="font-weight:bold; color:var(--accent);">#${o.id}</span>
                        <span style="font-size:0.85rem; color:#666;">${o.date}</span>
                    </div>
                    <div style="font-size:0.9rem; color:#444; margin-bottom:10px;">
                        ${o.items.map(i => `${i.qty}x ${i.name}`).join('<br>')}
                    </div>
                    <div style="border-top:1px solid #eee; padding-top:10px; display:flex; justify-content:space-between; align-items:center;">
                        <div>
                            ${o.pointsUsed > 0 ? `<div style="font-size:0.75rem; color:var(--danger);">Pakai ${o.pointsUsed} Poin</div>` : ''}
                            <div style="font-size:0.75rem; color:var(--gold);">+${o.pointsEarned} Poin Baru</div>
                        </div>
                        <div style="font-weight:bold; font-size:1.1rem;">Rp ${o.total.toLocaleString()}</div>
                    </div>
                    <div style="margin-top:5px; font-size:0.8rem; color:#666; text-align:right;">
                        Metode: ${o.payMethod}
                    </div>
                </div>
            `).join('');
        }

        // Click outside modal to close
        window.onclick = function(event) {
            if (event.target.classList.contains('modal-overlay')) {
                event.target.style.display = "none";
            }
        }
    </script>
</body>
</html>
