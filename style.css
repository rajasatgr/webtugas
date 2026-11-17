// ===== 1. SALAM SESUAI JAM =====
const salam = document.getElementById("salam");
const jam = new Date().getHours();

if (jam < 11) {
  salam.textContent = "Selamat pagi";
} else if (jam < 15) {
  salam.textContent = "Selamat siang";
} else if (jam < 18) {
  salam.textContent = "Selamat sore";
} else {
  salam.textContent = "Selamat malam";
}

// ===== 2. TAHUN OTOMATIS DI FOOTER =====
document.getElementById("tahun").textContent = new Date().getFullYear();

// ===== 3. MENU DI HP =====
const menuBtn = document.getElementById("menuBtn");
const nav = document.getElementById("nav");

menuBtn.addEventListener("click", function () {
  const terbuka = nav.classList.toggle("terbuka");
  menuBtn.setAttribute("aria-expanded", terbuka);
});

// Tutup menu setelah salah satu link diklik
nav.querySelectorAll("a").forEach(function (link) {
  link.addEventListener("click", function () {
    nav.classList.remove("terbuka");
    menuBtn.setAttribute("aria-expanded", "false");
  });
});

// ===== 4. MODE GELAP / TERANG =====
const themeBtn = document.getElementById("themeBtn");
const root = document.documentElement;

function setTema(tema) {
  if (tema === "gelap") {
    root.setAttribute("data-tema", "gelap");
    themeBtn.textContent = "Mode terang";
  } else {
    root.removeAttribute("data-tema");
    themeBtn.textContent = "Mode gelap";
  }
}

// Ingat pilihan terakhir (dibungkus try supaya tidak error jika penyimpanan diblokir)
try {
  setTema(localStorage.getItem("tema") || "terang");
} catch (e) {
  setTema("terang");
}

themeBtn.addEventListener("click", function () {
  const temaBaru = root.getAttribute("data-tema") === "gelap" ? "terang" : "gelap";
  setTema(temaBaru);
  try {
    localStorage.setItem("tema", temaBaru);
  } catch (e) {}
});

// ===== 5. FORMULIR KONTAK =====
const form = document.getElementById("formKontak");
const status = document.getElementById("formStatus");

form.addEventListener("submit", function (event) {
  event.preventDefault(); // cegah halaman reload

  const nama = form.nama.value.trim();
  const email = form.email.value.trim();
  const pesan = form.pesan.value.trim();

  status.className = "form-status";

  if (nama === "" || email === "" || pesan === "") {
    status.textContent = "Semua kolom harus diisi.";
    status.classList.add("error");
    return;
  }

  if (!email.includes("@")) {
    status.textContent = "Alamat email belum benar. Contoh: nama@email.com";
    status.classList.add("error");
    return;
  }

  // Catatan: formulir ini belum mengirim data ke server.
  status.textContent = "Terima kasih, " + nama + "! Pesanmu sudah diterima.";
  status.classList.add("sukses");
  form.reset();
});
