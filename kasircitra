<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kasir Tresna</title>

<style>
*{
    box-sizing:border-box;
}

body{
    margin:0;
    font-family:Arial,sans-serif;
    background:#f5f6fa;
    color:#333;
}

header{
    background:#5f27cd;
    color:white;
    padding:20px;
    text-align:center;
}

header h1{
    margin:0;
}

nav{
    display:flex;
    background:white;
    overflow-x:auto;
    box-shadow:0 2px 8px #ddd;
}

nav button{
    flex:1;
    min-width:120px;
    padding:14px;
    border:0;
    background:white;
    color:#555;
    font-weight:bold;
}

nav button.active{
    background:#5f27cd;
    color:white;
}

.container{
    max-width:1100px;
    margin:auto;
    padding:15px;
}

.page{
    display:none;
}

.page.active{
    display:block;
}

.card{
    background:white;
    padding:18px;
    border-radius:15px;
    margin-bottom:15px;
    box-shadow:0 3px 12px rgba(0,0,0,.08);
}

h2{
    color:#5f27cd;
    margin-top:0;
}

input,select{
    width:100%;
    padding:12px;
    border:1px solid #ddd;
    border-radius:9px;
    margin:6px 0 10px;
    font-size:15px;
}

button{
    cursor:pointer;
    border:0;
    border-radius:9px;
    padding:11px 14px;
    font-weight:bold;
}

.btn-primary{
    background:#5f27cd;
    color:white;
}

.btn-success{
    background:#00b894;
    color:white;
}

.btn-danger{
    background:#ee5253;
    color:white;
}

.btn-warning{
    background:#feca57;
    color:#333;
}

.grid{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:12px;
}

.stat{
    padding:20px;
    border-radius:15px;
    background:white;
    box-shadow:0 3px 10px rgba(0,0,0,.07);
}

.stat h3{
    margin:0;
    color:#777;
    font-size:14px;
}

.stat p{
    font-size:23px;
    font-weight:bold;
    color:#5f27cd;
}

.form-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:10px;
}

.product-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:12px;
}

.product{
    border:1px solid #eee;
    padding:15px;
    border-radius:12px;
}

.product h3{
    margin:0 0 8px;
}

.price{
    color:#5f27cd;
    font-weight:bold;
}

.stock{
    color:#777;
    font-size:13px;
}

table{
    width:100%;
    border-collapse:collapse;
}

th,td{
    padding:10px;
    border-bottom:1px solid #eee;
    text-align:left;
}

.total-box{
    text-align:right;
    font-size:21px;
    font-weight:bold;
    margin-top:15px;
}

.cart-row{
    display:flex;
    justify-content:space-between;
    align-items:center;
    border-bottom:1px solid #eee;
    padding:12px 0;
}

.qty button{
    padding:6px 10px;
    margin:0 2px;
}

.empty{
    text-align:center;
    color:#999;
    padding:25px;
}

.search{
    margin-bottom:15px;
}

.receipt{
    background:white;
    max-width:450px;
    margin:auto;
    padding:20px;
}

.receipt h2,
.receipt p{
    text-align:center;
}

.receipt-line{
    display:flex;
    justify-content:space-between;
    margin:7px 0;
}

@media(max-width:800px){
    .grid{
        grid-template-columns:repeat(2,1fr);
    }

    .product-grid{
        grid-template-columns:repeat(2,1fr);
    }
}

@media(max-width:550px){
    .form-grid{
        grid-template-columns:1fr;
    }

    .product-grid{
        grid-template-columns:1fr;
    }

    table{
        font-size:12px;
    }
}

@media print{
    body *{
        visibility:hidden;
    }

    #printArea,
    #printArea *{
        visibility:visible;
    }

    #printArea{
        position:absolute;
        left:0;
        top:0;
        width:100%;
    }
}
</style>
</head>

<body>

<header>
    <h1>🛍️ KASIR TRESNA</h1>
    <p>Sistem Kasir & Manajemen Toko</p>
</header>

<nav>
    <button class="active" onclick="showPage('dashboard',this)">
        🏠 Dashboard
    </button>

    <button onclick="showPage('kasir',this)">
        🛒 Kasir
    </button>

    <button onclick="showPage('produkPage',this)">
        📦 Produk
    </button>

    <button onclick="showPage('riwayat',this)">
        📋 Riwayat
    </button>
</nav>

<div class="container">

<!-- DASHBOARD -->

<section id="dashboard" class="page active">

<div class="grid">

<div class="stat">
<h3>Jumlah Produk</h3>
<p id="statProduk">0</p>
</div>

<div class="stat">
<h3>Total Stok</h3>
<p id="statStok">0</p>
</div>

<div class="stat">
<h3>Transaksi</h3>
<p id="statTransaksi">0</p>
</div>

<div class="stat">
<h3>Total Penjualan</h3>
<p id="statPenjualan">Rp0</p>
</div>

</div>

<div class="card">
<h2>👋 Selamat Datang</h2>
<p>
Selamat datang di aplikasi <b>Kasir Tresna</b>.
Gunakan menu di atas untuk mengelola produk,
melakukan transaksi, dan melihat riwayat penjualan.
</p>
</div>

</section>


<!-- KASIR -->

<section id="kasir" class="page">

<div class="card">

<h2>🛒 Transaksi Penjualan</h2>

<input
class="search"
id="cariKasir"
placeholder="🔎 Cari produk..."
oninput="tampilkanProdukKasir()">

<div id="produkKasir" class="product-grid"></div>

</div>


<div class="card">

<h2>🧺 Keranjang</h2>

<div id="cart"></div>

<div class="total-box">
Total:
<span id="total">Rp0</span>
</div>

</div>


<div class="card">

<h2>💳 Pembayaran</h2>

<label>Diskon (%)</label>

<input
type="number"
id="diskon"
value="0"
min="0"
max="100"
oninput="hitungTotal()">

<label>Pajak (%)</label>

<input
type="number"
id="pajak"
value="0"
min="0"
oninput="hitungTotal()">

<label>Uang Dibayar</label>

<input
type="number"
id="bayar"
placeholder="Masukkan jumlah uang"
oninput="hitungKembalian()">

<p>
Subtotal:
<b id="subtotal">Rp0</b>
</p>

<p>
Diskon:
<b id="nilaiDiskon">Rp0</b>
</p>

<p>
Pajak:
<b id="nilaiPajak">Rp0</b>
</p>

<h2>
Total:
<span id="totalBayar">Rp0</span>
</h2>

<h3>
Kembalian:
<span id="kembalian">Rp0</span>
</h3>

<button
class="btn-success"
onclick="prosesTransaksi()">
✅ BAYAR
</button>

<button
class="btn-danger"
onclick="kosongkanCart()">
🗑️ KOSONGKAN
</button>

</div>

</section>


<!-- PRODUK -->

<section id="produkPage" class="page">

<div class="card">

<h2>➕ Tambah Produk</h2>

<div class="form-grid">

<div>
<label>Nama Produk</label>
<input id="namaProduk"
placeholder="Contoh: Mie Instan">
</div>

<div>
<label>Harga</label>
<input id="hargaProduk"
type="number"
placeholder="Contoh: 5000">
</div>

<div>
<label>Stok</label>
<input id="stokProduk"
type="number"
placeholder="Jumlah stok">
</div>

<div>
<label>Kategori</label>

<select id="kategoriProduk">
<option>Makanan</option>
<option>Minuman</option>
<option>Snack</option>
<option>Lainnya</option>
</select>

</div>

</div>

<button
class="btn-primary"
onclick="tambahProduk()">
+ SIMPAN PRODUK
</button>

</div>


<div class="card">

<h2>📦 Data Produk</h2>

<input
placeholder="🔎 Cari produk..."
id="cariProduk"
oninput="tampilkanProduk()">

<table>

<thead>
<tr>
<th>Nama</th>
<th>Kategori</th>
<th>Harga</th>
<th>Stok</th>
<th>Aksi</th>
</tr>
</thead>

<tbody id="tabelProduk"></tbody>

</table>

</div>

</section>


<!-- RIWAYAT -->

<section id="riwayat" class="page">

<div class="card">

<h2>📋 Riwayat Transaksi</h2>

<button
class="btn-danger"
onclick="hapusRiwayat()">
🗑️ Hapus Semua Riwayat
</button>

<div id="riwayatData"></div>

</div>

</section>

</div>


<!-- AREA STRUK -->

<div id="printArea"></div>


<script>

let produk = JSON.parse(
localStorage.getItem("produkTresna")
) || [

{
id:1,
nama:"Mie Instan",
harga:3500,
stok:20,
kategori:"Makanan"
},

{
id:2,
nama:"Es Teh",
harga:5000,
stok:30,
kategori:"Minuman"
},

{
id:3,
nama:"Roti",
harga:7000,
stok:15,
kategori:"Makanan"
},

{
id:4,
nama:"Cokelat",
harga:8000,
stok:10,
kategori:"Snack"
}

];

let cart = [];

let riwayat = JSON.parse(
localStorage.getItem("riwayatTresna")
) || [];


function rupiah(angka){

return new Intl.NumberFormat(
"id-ID",
{
style:"currency",
currency:"IDR",
maximumFractionDigits:0
}
).format(angka);

}


function simpan(){

localStorage.setItem(
"produkTresna",
JSON.stringify(produk)
);

localStorage.setItem(
"riwayatTresna",
JSON.stringify(riwayat)
);

}


function showPage(id,button){

document.querySelectorAll(".page")
.forEach(p=>p.classList.remove("active"));

document.getElementById(id)
.classList.add("active");

document.querySelectorAll("nav button")
.forEach(b=>b.classList.remove("active"));

button.classList.add("active");

if(id==="dashboard")
updateDashboard();

if(id==="produkPage")
tampilkanProduk();

if(id==="kasir")
tampilkanProdukKasir();

if(id==="riwayat")
tampilkanRiwayat();

}


function updateDashboard(){

document.getElementById("statProduk")
.innerText=produk.length;

let stok=produk.reduce(
(a,b)=>a+Number(b.stok),0
);

document.getElementById("statStok")
.innerText=stok;

document.getElementById("statTransaksi")
.innerText=riwayat.length;

let penjualan=riwayat.reduce(
(a,b)=>a+Number(b.total),0
);

document.getElementById("statPenjualan")
.innerText=rupiah(penjualan);

}


function tambahProduk(){

let nama=
document.getElementById("namaProduk").value.trim();

let harga=
Number(document.getElementById("hargaProduk").value);

let stok=
Number(document.getElementById("stokProduk").value);

let kategori=
document.getElementById("kategoriProduk").value;

if(!nama || harga<=0 || stok<0){

alert("Lengkapi data produk!");

return;

}

produk.push({

id:Date.now(),

nama:nama,

harga:harga,

stok:stok,

kategori:kategori

});

simpan();

document.getElementById("namaProduk").value="";
document.getElementById("hargaProduk").value="";
document.getElementById("stokProduk").value="";

tampilkanProduk();

updateDashboard();

alert("Produk berhasil ditambahkan!");

}


function tampilkanProduk(){

let tbody=
document.getElementById("tabelProduk");

let cari=
document.getElementById("cariProduk")
.value.toLowerCase();

tbody.innerHTML="";

let hasil=produk.filter(p=>
p.nama.toLowerCase().includes(cari)
);

hasil.forEach(p=>{

tbody.innerHTML+=`

<tr>

<td>${p.nama}</td>

<td>${p.kategori}</td>

<td>${rupiah(p.harga)}</td>

<td>${p.stok}</td>

<td>

<button
class="btn-danger"
onclick="hapusProduk(${p.id})">
Hapus
</button>

</td>

</tr>

`;

});

}


function hapusProduk(id){

let p=produk.find(x=>x.id===id);

if(!p)return;

if(!confirm(
"Yakin ingin menghapus "+p.nama+"?"
))return;

produk=produk.filter(
x=>x.id!==id
);

cart=cart.filter(
x=>x.id!==id
);

simpan();

tampilkanProduk();

tampilkanProdukKasir();

updateDashboard();

}


function tampilkanProdukKasir(){

let area=
document.getElementById("produkKasir");

let cari=
document.getElementById("cariKasir")
.value.toLowerCase();

area.innerHTML="";

produk
.filter(p=>
p.nama.toLowerCase().includes(cari)
)
.forEach(p=>{

area.innerHTML+=`

<div class="product">

<h3>${p.nama}</h3>

<div class="price">
${rupiah(p.harga)}
</div>

<div class="stock">
Stok: ${p.stok}
</div>

<br>

<button
class="btn-primary"
onclick="masukCart(${p.id})"
${p.stok<=0?"disabled":""}>
+ Tambah
</button>

</div>

`;

});

}


function masukCart(id){

let p=produk.find(
x=>x.id===id
);

if(!p || p.stok<=0){

alert("Stok habis!");

return;

}

let item=cart.find(
x=>x.id===id
);

if(item){

if(item.qty>=p.stok){

alert("Jumlah melebihi stok!");

return;

}

item.qty++;

}else{

cart.push({

id:p.id,

nama:p.nama,

harga:p.harga,

qty:1

});

}

tampilkanCart();

}


function tampilkanCart(){

let area=
document.getElementById("cart");

area.innerHTML="";

if(cart.length===0){

area.innerHTML=
'<div class="empty">Keranjang masih kosong 🛒</div>';

}

cart.forEach((item,index)=>{

area.innerHTML+=`

<div class="cart-row">

<div>

<b>${item.nama}</b><br>

${rupiah(item.harga)}

</div>

<div class="qty">

<button
onclick="kurang(${index})">
−
</button>

<b>${item.qty}</b>

<button
onclick="tambahQty(${index})">
+
</button>

<button
class="btn-danger"
onclick="hapusCart(${index})">
✕
</button>

</div>

</div>

`;

});

hitungTotal();

}


function tambahQty(index){

let item=cart[index];

let p=produk.find(
x=>x.id===item.id
);

if(item.qty>=p.stok){

alert("Stok tidak mencukupi!");

return;

}

item.qty++;

tampilkanCart();

}


function kurang(index){

cart[index].qty--;

if(cart[index].qty<=0){

cart.splice(index,1);

}

tampilkanCart();

}


function hapusCart(index){

cart.splice(index,1);

tampilkanCart();

}


function kosongkanCart(){

if(cart.length===0)return;

if(confirm("Kosongkan keranjang?")){

cart=[];

tampilkanCart();

}

}


function hitungTotal(){

let subtotal=0;

cart.forEach(item=>{

subtotal+=item.harga*item.qty;

});

let diskonPersen=
Number(
document.getElementById("diskon").value
)||0;

let pajakPersen=
Number(
document.getElementById("pajak").value
)||0;

let diskon=
subtotal*diskonPersen/100;

let setelahDiskon=
subtotal-diskon;

let pajak=
setelahDiskon*pajakPersen/100;

let total=
setelahDiskon+pajak;

document.getElementById("subtotal")
.innerText=rupiah(subtotal);

document.getElementById("nilaiDiskon")
.innerText=rupiah(diskon);

document.getElementById("nilaiPajak")
.innerText=rupiah(pajak);

document.getElementById("total")
.innerText=rupiah(total);

document.getElementById("totalBayar")
.innerText=rupiah(total);

hitungKembalian();

return total;

}


function hitungKembalian(){

let total=hitungTotalTanpaLoop();

let bayar=
Number(
document.getElementById("bayar").value
)||0;

let kembali=bayar-total;

if(kembali<0)
kembali=0;

document.getElementById("kembalian")
.innerText=rupiah(kembali);

}


function hitungTotalTanpaLoop(){

let subtotal=0;

cart.forEach(item=>{

subtotal+=item.harga*item.qty;

});

let diskonPersen=
Number(
document.getElementById("diskon").value
)||0;

let pajakPersen=
Number(
document.getElementById("pajak").value
)||0;

let diskon=
subtotal*diskonPersen/100;

let setelahDiskon=
subtotal-diskon;

let pajak=
setelahDiskon*pajakPersen/100;

return setelahDiskon+pajak;

}


function prosesTransaksi(){

if(cart.length===0){

alert("Keranjang masih kosong!");

return;

}

let total=hitungTotalTanpaLoop();

let bayar=
Number(
document.getElementById("bayar").value
)||0;

if(bayar<total){

alert(
"Uang kurang "+rupiah(total-bayar)
);

return;

}


let nomor=
"TRX-"+Date.now();

let kembali=bayar-total;

cart.forEach(item=>{

let p=produk.find(
x=>x.id===item.id
);

p.stok-=item.qty;

});


let transaksi={

nomor:nomor,

tanggal:new Date()
.toLocaleString("id-ID"),

items:JSON.parse(
JSON.stringify(cart)
),

total:total,

bayar:bayar,

kembali:kembali

};


riwayat.unshift(transaksi);

simpan();

buatStruk(transaksi);

cart=[];

document.getElementById("bayar").value="";

document.getElementById("diskon").value=0;

document.getElementById("pajak").value=0;

tampilkanCart();

tampilkanProdukKasir();

updateDashboard();

alert("Transaksi berhasil!");

}


function buatStruk(data){

let area=
document.getElementById("printArea");

let isi="";

data.items.forEach(item=>{

isi+=`

<div class="receipt-line">

<span>
${item.nama} x${item.qty}
</span>

<span>
${rupiah(item.harga*item.qty)}
</span>

</div>

`;

});

area.innerHTML=`

<div class="receipt">

<h2>🛍️ TRESNA</h2>

<p>Struk Pembelian</p>

<hr>

<p>${data.nomor}</p>

<p>${data.tanggal}</p>

<hr>

${isi}

<hr>

<div class="receipt-line">
<b>Total</b>
<b>${rupiah(data.total)}</b>
</div>

<div class="receipt-line">
Bayar
<span>${rupiah(data.bayar)}</span>
</div>

<div class="receipt-line">
Kembalian
<span>${rupiah(data.kembali)}</span>
</div>

<hr>

<p>Terima kasih telah berbelanja 💜</p>

<br>

<button
class="btn-primary"
onclick="window.print()">
🖨️ CETAK STRUK
</button>

</div>

`;

}


function tampilkanRiwayat(){

let area=
document.getElementById("riwayatData");

if(riwayat.length===0){

area.innerHTML=
'<div class="empty">Belum ada transaksi.</div>';

return;

}

area.innerHTML="";

riwayat.forEach((trx,index)=>{

let detail="";

trx.items.forEach(item=>{

detail+=`
<li>
${item.nama} × ${item.qty}
= ${rupiah(item.harga*item.qty)}
</li>
`;

});

area.innerHTML+=`

<div class="card">

<h3>${trx.nomor}</h3>

<p>${trx.tanggal}</p>

<ul>
${detail}
</ul>

<hr>

<p>
Total:
<b>${rupiah(trx.total)}</b>
</p>

<p>
Bayar:
${rupiah(trx.bayar)}
</p>

<p>
Kembalian:
${rupiah(trx.kembali)}
</p>

</div>

`;

});

}


function hapusRiwayat(){

if(riwayat.length===0)return;

if(confirm("Hapus semua riwayat transaksi?")){

riwayat=[];

simpan();

tampilkanRiwayat();

updateDashboard();

}

}


tampilkanProduk();

tampilkanProdukKasir();

tampilkanCart();

updateDashboard();

</script>

</body>
</html>
