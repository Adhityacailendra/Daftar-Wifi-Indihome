<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Registrasi Pelanggan IndiHome</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex items-center justify-center min-h-screen">
  <div class="w-full max-w-md bg-white p-6 rounded-lg shadow-md">
    <h1 class="text-center text-xl font-bold mb-4">Kirim Link Registrasi Customer</h1>
    <div class="bg-blue-600 text-white p-4 rounded-lg mb-4">
      <p>Formulir pendaftaran & verifikasi pelanggan, lengkapi persyaratan berikut:</p>
      <ul class="list-disc list-inside">
        <li>Foto KTP</li>
        <li>Foto Rumah</li>
      </ul>
      <p class="mt-2">
        Untuk layanan internet IndiHome di wilayah Baturaja dan sekitarnya, mohon hubungi petugas 
        <span class="font-bold">082281512603</span> untuk konfirmasi pemasangan.
      </p>
    </div>
    <form id="whatsappForm">
      <div class="mb-4">
        <label class="block text-gray-700 mb-2" for="nama">Nama Pelanggan</label>
        <input class="w-full px-3 py-2 border border-gray-300 rounded-lg" type="text" id="nama" placeholder="Nama lengkap pelanggan" required>
      </div>
      <div class="mb-4">
        <label class="block text-gray-700 mb-2" for="email">Email Pelanggan</label>
        <input class="w-full px-3 py-2 border border-gray-300 rounded-lg" type="email" id="email" placeholder="Alamat email pelanggan" required>
      </div>
      <div class="mb-4">
        <label class="block text-gray-700 mb-2" for="phone">No. Handphone</label>
        <input class="w-full px-3 py-2 border border-gray-300 rounded-lg" type="text" id="phone" placeholder="No. handphone pelanggan" required>
      </div>
      <div class="text-center text-red-600 font-bold mb-4">INDIHOME</div>
      <button type="button" onclick="sendToWhatsApp()" class="w-full bg-green-600 text-white py-2 rounded-lg hover:bg-green-700">
        Kirim Link Verifikasi
      </button>
    </form>
    <p class="text-center text-gray-500 text-sm mt-4">
      Design by Adhitya Cailendra Putra SF AGENCY #INDIHOME35
    </p>
  </div>

  <script>
    function sendToWhatsApp() {
      var nama = document.getElementById("nama").value;
      var email = document.getElementById("email").value;
      var phone = document.getElementById("phone").value;
      
      if (nama === "" || email === "" || phone === "") {
        alert("Harap isi semua data sebelum mengirim.");
        return;
      }

      var message = "Halo, saya ingin mendaftar IndiHome.\n\n" +
                    "Nama: " + nama + "\n" +
                    "Email: " + email + "\n" +
                    "No. Handphone: " + phone + "\n\n" +
                    "Mohon informasi lebih lanjut. Terima kasih!";

      var whatsappUrl = "https://api.whatsapp.com/send?phone=6282281512603&text=" + encodeURIComponent(message);
      window.open(whatsappUrl, "_blank");
    }
  </script>
</body>
</html>