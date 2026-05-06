<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sumthing - Pesan Sekarang!</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Menggunakan font Fredoka yang bulat dan tebal agar sesuai logo -->
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script>
        // Fungsi untuk menangani jika gambar gagal dimuat
        function handleImageError() {
            const logo = document.getElementById('mainLogo');
            const fallback = document.getElementById('logoFallback');
            if (logo) logo.style.display = 'none';
            if (fallback) fallback.style.display = 'flex';
        }
    </script>
    <style>
        body {
            font-family: 'Fredoka', sans-serif;
            background-color: #fff9f0;
            color: #2B0A06;
        }
        
        /* Judul utama dengan efek bayangan 3D seperti logo */
        .brand-title {
            color: #2B0A06;
            text-shadow: 2px 2px 0px #fff, 4px 4px 0px #F39200;
            letter-spacing: -1px;
        }

        .bg-sumthing-orange { background-color: #F39200; }
        .text-sumthing-orange { color: #F39200; }
        
        .header-bg {
            background-color: #fbbf24;
            background-image: radial-gradient(#d97706 1.5px, transparent 1.5px);
            background-size: 20px 20px;
        }

        .btn-primary {
            background-color: #F39200;
            transition: all 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 6px 0 #bf7300;
            border: 2px solid #2B0A06;
        }
        
        .btn-primary:hover {
            transform: scale(1.02);
        }

        .btn-primary:active {
            transform: translateY(4px);
            box-shadow: 0 2px 0 #bf7300;
        }

        .card {
            background: white;
            border: 3px solid #2B0A06;
            border-radius: 24px;
            box-shadow: 6px 6px 0px rgba(43, 10, 6, 0.1);
        }
        
        .logo-container {
            width: 180px;
            height: 180px;
            margin: 0 auto 1.5rem;
            position: relative;
            perspective: 1000px;
        }

        /* Efek Timbul pada Logo */
        .logo-sticker {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 9999px;
            border: 8px solid white;
            /* Bayangan ganda untuk efek kedalaman/timbul */
            box-shadow: 
                0 0 0 4px #2B0A06, 
                10px 15px 0px rgba(43, 10, 6, 0.15);
            background-color: white;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
        }

        /* Animasi saat logo di-hover (terangkat lebih tinggi) */
        .logo-container:hover .logo-sticker {
            transform: translateY(-10px) rotate(2deg);
            box-shadow: 
                0 0 0 4px #2B0A06, 
                15px 25px 0px rgba(43, 10, 6, 0.1);
        }

        .logo-fallback {
            display: none;
            width: 100%;
            height: 100%;
            border-radius: 9999px;
            border: 8px solid white;
            box-shadow: 0 0 0 4px #2B0A06, 10px 15px 0px rgba(43, 10, 6, 0.15);
            background-color: #F39200;
            align-items: center;
            justify-content: center;
            font-size: 80px;
        }

        input, select {
            border: 2px solid #2B0A06;
            border-radius: 14px;
            padding: 12px;
            width: 100%;
            font-weight: 500;
        }
        
        input:focus, select:focus {
            outline: none;
            border-color: #F39200;
            background-color: #fffbeb;
        }

        .menu-item {
            border: 2px solid #2B0A06;
            transition: transform 0.2s;
        }
        
        .menu-item:hover {
            transform: translateX(4px);
        }

        .input-label {
            display: block;
            font-size: 0.875rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #2B0A06;
        }
    </style>
</head>
<body class="pb-20">

    <!-- Header Section -->
    <header class="text-center pt-12 pb-14 px-4 header-bg border-b-4 border-sumthing-dark">
        <div class="logo-container">
            <!-- Menambahkan tautan ke Instagram pada Logo -->
            <a href="https://instagram.com/ci_sumthing" target="_blank" title="Cek Instagram Kami!">
                <img id="mainLogo" 
                     src="https://www.image2url.com/r2/default/images/1777968536395-cae082c8-049c-42ae-9614-cac528a89bc6.png" 
                     alt="Logo Sumthing" 
                     class="logo-sticker"
                     onerror="handleImageError()">
            </a>
            <div id="logoFallback" class="logo-fallback">🥟</div>
        </div>
        <h1 class="text-5xl font-bold brand-title mb-3">Sumthing</h1>
        <p class="bg-[#2B0A06] text-white inline-block px-5 py-1.5 rounded-full text-sm font-medium shadow-lg">
            "Bernutrisi dan ramah di kantong"
        </p>
    </header>

    <main class="max-w-lg mx-auto px-4 -mt-6">
        <form id="orderForm" class="space-y-8">
            
            <!-- Identitas Pelanggan -->
            <section class="card p-6">
                <h2 class="text-2xl font-bold mb-5 flex items-center text-sumthing-orange">
                    <span class="bg-orange-100 p-2 rounded-lg mr-3">👤</span> Pemesan
                </h2>
                <div class="space-y-4">
                    <div>
                        <label class="input-label">Nama Lengkap</label>
                        <input type="text" id="customerName" placeholder="Siapa nama kamu?" required>
                    </div>
                    <div>
                        <label class="input-label">Nomor WhatsApp</label>
                        <input type="tel" id="customerWA" placeholder="Contoh: 0812345..." required>
                    </div>
                </div>
            </section>

            <!-- Varian Menu -->
            <section class="card p-6">
                <h2 class="text-2xl font-bold mb-5 flex items-center text-sumthing-orange">
                    <span class="bg-orange-100 p-2 rounded-lg mr-3">🥟</span> Pilih Menu
                </h2>
                <div id="menuList" class="space-y-4">
                    <div class="menu-item flex items-center justify-between p-4 bg-orange-50 rounded-2xl">
                        <div>
                            <h3 class="font-bold text-lg">Siomay Original</h3>
                            <p class="text-sm font-medium text-orange-700">Rp 15.000 / porsi</p>
                        </div>
                        <div class="flex items-center space-x-3 bg-white p-1 rounded-full border-2 border-sumthing-dark">
                            <button type="button" onclick="changeQty('item1', -1)" class="w-9 h-9 rounded-full hover:bg-gray-100 font-bold text-xl">-</button>
                            <span id="qty-item1" class="font-bold w-6 text-center text-lg">0</span>
                            <button type="button" onclick="changeQty('item1', 1)" class="w-9 h-9 rounded-full bg-sumthing-orange text-white border-2 border-sumthing-dark font-bold text-xl">+</button>
                        </div>
                    </div>

                    <div class="menu-item flex items-center justify-between p-4 bg-orange-50 rounded-2xl">
                        <div>
                            <h3 class="font-bold text-lg">Dimsum Mix (5 pcs)</h3>
                            <p class="text-sm font-medium text-orange-700">Rp 20.000 / porsi</p>
                        </div>
                        <div class="flex items-center space-x-3 bg-white p-1 rounded-full border-2 border-sumthing-dark">
                            <button type="button" onclick="changeQty('item2', -1)" class="w-9 h-9 rounded-full hover:bg-gray-100 font-bold text-xl">-</button>
                            <span id="qty-item2" class="font-bold w-6 text-center text-lg">0</span>
                            <button type="button" onclick="changeQty('item2', 1)" class="w-9 h-9 rounded-full bg-sumthing-orange text-white border-2 border-sumthing-dark font-bold text-xl">+</button>
                        </div>
                    </div>

                    <div class="menu-item flex items-center justify-between p-4 bg-orange-50 rounded-2xl">
                        <div>
                            <h3 class="font-bold text-lg">Siomay Kuah Pedas</h3>
                            <p class="text-sm font-medium text-orange-700">Rp 18.000 / porsi</p>
                        </div>
                        <div class="flex items-center space-x-3 bg-white p-1 rounded-full border-2 border-sumthing-dark">
                            <button type="button" onclick="changeQty('item3', -1)" class="w-9 h-9 rounded-full hover:bg-gray-100 font-bold text-xl">-</button>
                            <span id="qty-item3" class="font-bold w-6 text-center text-lg">0</span>
                            <button type="button" onclick="changeQty('item3', 1)" class="w-9 h-9 rounded-full bg-sumthing-orange text-white border-2 border-sumthing-dark font-bold text-xl">+</button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Pengambilan -->
            <section class="card p-6">
                <h2 class="text-2xl font-bold mb-5 flex items-center text-sumthing-orange">
                    <span class="bg-orange-100 p-2 rounded-lg mr-3">🕒</span> Pengambilan
                </h2>
                <div class="space-y-5">
                    <div>
                        <label class="input-label">Metode</label>
                        <select id="pickupMethod" required>
                            <option value="Ambil di Tempat">Ambil di Tempat (Self Pickup)</option>
                            <option value="COD">COD (Sekitar Area)</option>
                        </select>
                    </div>
                    <div>
                        <label class="input-label">Tanggal Pengambilan</label>
                        <input type="date" id="pickupDate" required>
                    </div>
                    <div>
                        <label class="input-label">Sesi Jam</label>
                        <div class="space-y-2">
                            <label class="flex items-center p-4 border-2 border-gray-200 rounded-2xl cursor-pointer hover:border-sumthing-orange hover:bg-yellow-50 transition font-medium">
                                <input type="radio" name="pickupTime" value="10.00-11.00" class="w-5 h-5 mr-3 accent-orange-600" checked>
                                <span>10.00 - 11.00</span>
                            </label>
                            <label class="flex items-center p-4 border-2 border-gray-200 rounded-2xl cursor-pointer hover:border-sumthing-orange hover:bg-yellow-50 transition font-medium">
                                <input type="radio" name="pickupTime" value="13.00-14.00" class="w-5 h-5 mr-3 accent-orange-600">
                                <span>13.00 - 14.00</span>
                            </label>
                            <label class="flex items-center p-4 border-2 border-gray-200 rounded-2xl cursor-pointer hover:border-sumthing-orange hover:bg-yellow-50 transition font-medium">
                                <input type="radio" name="pickupTime" value="16.30-17.30" class="w-5 h-5 mr-3 accent-orange-600">
                                <span>16.30 - 17.30</span>
                            </label>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Sticky Total & Order Button -->
            <div class="sticky bottom-6 z-10 px-2">
                <div class="bg-white border-4 border-sumthing-dark rounded-[30px] p-5 shadow-2xl">
                    <div class="flex justify-between items-center mb-4 px-2">
                        <span class="font-bold text-xl">Total:</span>
                        <span id="totalDisplay" class="text-3xl font-bold text-sumthing-orange">Rp 0</span>
                    </div>
                    <button type="button" onclick="sendToWhatsApp()" class="w-full py-4 text-white font-bold text-xl rounded-2xl btn-primary flex items-center justify-center space-x-2">
                        <span>Pesan Sekarang! 🚀</span>
                    </button>
                </div>
            </div>

        </form>
    </main>

    <!-- Footer -->
    <footer class="mt-16 text-center px-4">
        <a href="https://instagram.com/ci_sumthing" target="_blank" class="inline-flex items-center space-x-2 bg-[#2B0A06] text-white px-6 py-3 rounded-full font-bold hover:scale-105 transition shadow-lg">
            <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
            <span>Instagram: @ci_sumthing</span>
        </a>
        <p class="mt-8 text-xs font-bold text-gray-400 uppercase tracking-widest">&copy; 2024 Sumthing Indonesia</p>
    </footer>

    <script>
        // Data Menu
        const menuData = {
            item1: { name: "Siomay Original", price: 15000, qty: 0 },
            item2: { name: "Dimsum Mix (5 pcs)", price: 20000, qty: 0 },
            item3: { name: "Siomay Kuah Pedas", price: 18000, qty: 0 }
        };

        // Fungsi mengubah jumlah
        function changeQty(itemId, delta) {
            const item = menuData[itemId];
            item.qty = Math.max(0, item.qty + delta);
            document.getElementById(`qty-${itemId}`).innerText = item.qty;
            updateTotal();
        }

        // Fungsi update total harga
        function updateTotal() {
            let total = 0;
            for (let key in menuData) {
                total += menuData[key].price * menuData[key].qty;
            }
            document.getElementById('totalDisplay').innerText = "Rp " + total.toLocaleString('id-ID');
            return total;
        }

        // Fungsi kirim ke WhatsApp
        function sendToWhatsApp() {
            const name = document.getElementById('customerName').value;
            const wa = document.getElementById('customerWA').value;
            const method = document.getElementById('pickupMethod').value;
            const date = document.getElementById('pickupDate').value;
            const time = document.querySelector('input[name="pickupTime"]:checked').value;
            const total = updateTotal();

            if (!name || !wa || !date) {
                alert("Waduh! Nama, WhatsApp, dan tanggalnya jangan lupa diisi ya! 🙏");
                return;
            }

            let itemDetails = "";
            let hasOrder = false;
            for (let key in menuData) {
                if (menuData[key].qty > 0) {
                    itemDetails += `- ${menuData[key].name} (${menuData[key].qty}x): Rp ${(menuData[key].price * menuData[key].qty).toLocaleString('id-ID')}\n`;
                    hasOrder = true;
                }
            }

            if (!hasOrder) {
                alert("Pilih menunya dulu yuk, biar perut nggak keroncongan! 🥟");
                return;
            }

            const businessWA = "6281234567890"; // Ganti dengan nomor WhatsApp Anda
            const message = `*PESANAN BARU SUMTHING* 🥟🚀\n\n` +
                            `*Halo Admin!*\n` +
                            `Saya mau pesan nih:\n\n` +
                            `*Nama:* ${name}\n` +
                            `*WA:* ${wa}\n\n` +
                            `*Daftar Pesanan:*\n${itemDetails}\n` +
                            `*Total: Rp ${total.toLocaleString('id-ID')}*\n\n` +
                            `--- Info Pengambilan ---\n` +
                            `📍 *Metode:* ${method}\n` +
                            `📅 *Tanggal:* ${date}\n` +
                            `🕒 *Jam:* ${time}\n\n` +
                            `Ditunggu ya konfirmasinya! Terima kasih ✨`;

            window.open(`https://wa.me/${businessWA}?text=${encodeURIComponent(message)}`, '_blank');
        }

        // Inisialisasi tanggal default ke hari ini
        document.getElementById('pickupDate').valueAsDate = new Date();
    </script>
</body>
</html>
