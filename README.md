<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>EA Activator</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 min-h-screen flex items-center justify-center">
  <div class="bg-white shadow-xl rounded-2xl p-8 w-full max-w-md">
    <h1 class="text-2xl font-bold mb-6 text-center text-blue-600">EA Activator</h1>

    <div class="mb-4">
      <label class="block font-semibold mb-1">Bot Name:</label>
      <input id="botName" class="w-full border rounded-lg p-2" placeholder="e.g., GoldHunterEA" />
    </div>

    <div class="mb-4">
      <label class="block font-semibold mb-1">Symbols (comma-separated):</label>
      <input id="symbols" class="w-full border rounded-lg p-2" placeholder="e.g., XAUUSD, NAS100" />
    </div>

    <button onclick="generateKey()" class="w-full bg-blue-600 text-white py-2 rounded-xl hover:bg-blue-700">Generate License Key</button>

    <div id="output" class="mt-6 text-sm break-all text-center text-green-600 font-mono"></div>
  </div>

  <script>
    function generateKey() {
      const botName = document.getElementById('botName').value.trim();
      const symbols = document.getElementById('symbols').value.trim();

      if (!botName || !symbols) {
        alert('Please enter both bot name and symbols.');
        return;
      }

      const base = `${botName}:${symbols}`;
      const hash = btoa(unescape(encodeURIComponent(base + Date.now()))).slice(0, 32);

      document.getElementById('output').textContent = `License Key: ${hash}`;
    }
  </script>
</body>
</html>
