<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Distributor Profile & MLM Tree</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      background: linear-gradient(135deg, #ff6ec4, #7873f5);
    }
    .connector {
      width: 2px;
      background-color: white;
      height: 20px;
      margin: auto;
    }
    .horizontal-line {
      height: 2px;
      background-color: white;
      flex-grow: 1;
    }
  </style>
  <script>
    // Sample data
    const members = [
      {
        name: "Karim",
        role: "You",
        image: "images/karim.jpg",
        id: "MLM001",
        phone: "01234567890",
        downline: [
          {
            name: "Jannat",
            image: "images/jannat.jpg",
            id: "MLM002",
            phone: "01711111111",
            downline: [
              {
                name: "Nayeem",
                image: "images/nayeem.jpg",
                id: "MLM003",
                phone: "01888888888"
              }
            ]
          },
          {
            name: "Rakib",
            image: "images/rakib.jpg",
            id: "MLM004",
            phone: "01555555555",
            downline: [
              {
                name: "Rafi",
                image: "images/rafi.jpg",
                id: "MLM005",
                phone: "01444444444"
              }
            ]
          },
          {
            name: "Lamia",
            image: "images/lamia.jpg",
            id: "MLM006",
            phone: "01333333333"
          }
        ]
      }
    ];

    function showPopup(member) {
      document.getElementById("popup").classList.remove("hidden");
      document.getElementById("popup-img").src = member.image;
      document.getElementById("popup-name").textContent = member.name;
      document.getElementById("popup-id").textContent = member.id;
      document.getElementById("popup-phone").textContent = member.phone;
    }

    function closePopup() {
      document.getElementById("popup").classList.add("hidden");
    }

    function renderTree(members, container) {
      const row = document.createElement("div");
      row.className = "flex justify-center items-start space-x-8 relative";

      members.forEach((member) => {
        const node = document.createElement("div");
        node.className = "flex flex-col items-center space-y-2 relative";

        node.innerHTML = `
          <div class="flex flex-col items-center group cursor-pointer" onclick='showPopup(${JSON.stringify(member)})'>
            <img src="${member.image}" class="w-16 h-16 rounded-full border-4 border-white shadow-lg group-hover:scale-105 transition-transform" />
            <div class="mt-1 text-sm bg-white text-black px-2 py-1 rounded-full shadow group-hover:bg-yellow-200">${member.name}</div>
            <div class="absolute mt-20 hidden group-hover:block text-xs bg-black bg-opacity-70 text-white px-2 py-1 rounded">ID: ${member.id}</div>
          </div>
        `;

        row.appendChild(node);
      });

      container.appendChild(row);

      // Add connectors and children recursively
      members.forEach((member) => {
        if (member.downline && member.downline.length > 0) {
          const connectorWrapper = document.createElement("div");
          connectorWrapper.className = "flex flex-col items-center";

          const verticalLine = document.createElement("div");
          verticalLine.className = "connector";
          connectorWrapper.appendChild(verticalLine);

          const horizontalContainer = document.createElement("div");
          horizontalContainer.className = "flex space-x-10 items-center mt-1 mb-1";
          member.downline.forEach(() => {
            const line = document.createElement("div");
            line.className = "horizontal-line";
            horizontalContainer.appendChild(line);
          });
          connectorWrapper.appendChild(horizontalContainer);

          container.appendChild(connectorWrapper);

          const childContainer = document.createElement("div");
          childContainer.className = "flex justify-center space-x-10 mt-4";
          renderTree(member.downline, childContainer);
          container.appendChild(childContainer);
        }
      });
    }

    window.onload = function () {
      const treeContainer = document.getElementById("tree-container");
      renderTree(members, treeContainer);
    };
  </script>
</head>
<body class="min-h-screen text-white font-sans">

  <!-- Header -->
  <header class="bg-gradient-to-r from-pink-600 via-purple-600 to-blue-600 p-6 text-center shadow-2xl">
    <h1 class="text-4xl font-extrabold tracking-wider glow">🚀 Distributor Profile</h1>
    <p class="text-sm mt-2 text-pink-200">Shining your network journey!</p>
  </header>

  <!-- Profile Card -->
  <main class="max-w-xl mx-auto mt-8 bg-white bg-opacity-10 backdrop-blur-xl border border-white/20 rounded-3xl shadow-2xl p-6">

    <!-- Photo + Name -->
    <div class="flex flex-col items-center">
      <img src="profile.jpg" alt="Distributor Photo" class="w-32 h-32 rounded-full border-4 border-pink-400 shadow-lg" />
      <h2 class="mt-4 text-3xl font-bold text-yellow-300">Abdul Karim</h2>
      <p class="text-pink-100 text-sm mt-1">MLM ID: <span class="font-semibold text-white">#MLM239823</span></p>
    </div>

    <!-- QR Code -->
    <div class="flex justify-center mt-4">
      <img src="qrcode.png" alt="QR Code" class="w-24 h-24 border-2 border-yellow-400 p-1 rounded-xl bg-white" />
    </div>

    <!-- Balance -->
    <div class="bg-gradient-to-r from-green-400 to-lime-500 text-center py-4 px-6 mt-6 rounded-xl shadow-md text-black">
      <p class="text-lg font-bold">💰 Current Balance</p>
      <p class="text-3xl font-extrabold mt-1">৳ 12,500</p>
    </div>

    <!-- About -->
    <div class="mt-6 p-4 bg-gradient-to-r from-pink-500 to-purple-700 rounded-xl shadow-lg">
      <h3 class="text-xl font-bold text-yellow-200 mb-2">🧾 About Me</h3>
      <p class="text-white text-sm leading-relaxed">
        আমি একজন উদ্যমী ডিস্ট্রিবিউটর, যিনি MLM নেটওয়ার্কের মাধ্যমে সফলতা অর্জনের লক্ষ্যে কাজ করছি। আমি চাই সবাই আমার টিমে সফল হোক।
      </p>
    </div>

    <!-- Contact -->
    <div class="mt-6 p-4 bg-gradient-to-r from-blue-500 to-cyan-500 rounded-xl shadow-lg text-center">
      <p class="text-lg font-semibold text-white">📞 017xxxxxxxx</p>
      <p class="text-white text-sm">✉️ karim@gmail.com</p>
      <div class="flex justify-center gap-4 mt-3 text-white">
        <a href="#" class="hover:underline">🌐 Facebook</a>
        <a href="#" class="hover:underline">📷 Instagram</a>
      </div>
    </div>

    <!-- Status -->
    <div class="mt-6 bg-gradient-to-r from-purple-400 via-pink-400 to-red-400 p-4 rounded-xl text-center shadow-lg text-white">
      <p class="font-bold text-lg">✅ Active Member</p>
      <p class="text-sm">Joined: January 10, 2025</p>
    </div>
  </main>

<!-- MLM Tree -->
<section class="mt-12 px-4">
  <h2 class="text-center text-2xl font-bold mb-6 text-yellow-100">🌳 My Network Tree</h2>
  <div id="tree-container" class="overflow-x-auto pb-10"></div>

  <!-- Popup -->
  <div id="popup" class="fixed inset-0 bg-black bg-opacity-70 flex justify-center items-center hidden z-50">
    <div class="bg-white rounded-xl p-6 w-80 text-center text-black shadow-2xl relative">
      <button onclick="closePopup()" class="absolute top-2 right-2 text-xl text-gray-600 hover:text-red-500">×</button>
      <img id="popup-img" src="" class="w-24 h-24 rounded-full mx-auto border-4 border-pink-400 mb-4" />
      <h3 id="popup-name" class="text-xl font-bold"></h3>
      <p class="text-sm text-gray-600 mt-1">ID: <span id="popup-id" class="font-semibold"></span></p>
      <p class="text-sm text-gray-600">📞 <span id="popup-phone" class="font-semibold"></span></p>
    </div>
  </div>
</section>

  <!-- Footer -->
  <footer class="text-center text-pink-200 text-sm mt-10 mb-6">
    © 2025 Soha Network | Designed by Abir
  </footer>

</body>
</html>
