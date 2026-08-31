<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login & Register - Noble Academy</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- FontAwesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css"/>
</head>
<body class="bg-gray-100 font-sans flex items-center justify-center min-h-screen p-4">

  <!-- AUTH CONTAINER -->
  <div class="w-full max-w-md bg-white rounded-2xl shadow-xl overflow-hidden border border-gray-100">
    
    <!-- Header / Branding -->
    <div class="bg-[#002B49] text-white p-6 text-center">
      <div class="w-16 h-16 bg-yellow-500 text-[#002B49] font-bold text-2xl rounded-full flex items-center justify-center mx-auto mb-3 border-2 border-white shadow">
        NA
      </div>
      <h1 class="text-xl font-extrabold tracking-wide uppercase">Noble Academy</h1>
      <p class="text-xs text-gray-300 mt-1">Jijiga, Ethiopia • Student & Staff Portal</p>
    </div>

    <!-- Tab Buttons -->
    <div class="flex border-b text-xs font-semibold uppercase tracking-wider">
      <button id="loginTabBtn" onclick="switchTab('login')" class="w-1/2 py-3 text-center border-b-2 border-[#002B49] text-[#002B49] font-bold transition">
        <i class="fas fa-sign-in-alt mr-1"></i> Sign In
      </button>
      <button id="registerTabBtn" onclick="switchTab('register')" class="w-1/2 py-3 text-center text-gray-400 hover:text-gray-600 border-b-2 border-transparent transition">
        <i class="fas fa-user-plus mr-1"></i> Register
      </button>
    </div>

    <!-- Forms Wrapper -->
    <div class="p-6">

      <!-- 1. LOGIN FORM -->
      <form id="loginForm" class="space-y-4" onsubmit="event.preventDefault(); alert('Soo dhowaow!');">
        <div>
          <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Admission ID / Email</label>
          <div class="relative">
            <span class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-400 text-sm">
              <i class="fas fa-id-card"></i>
            </span>
            <input type="text" required placeholder="e.g. NA-2026-1042 or email" class="w-full pl-10 pr-4 py-2.5 text-xs bg-gray-50 border border-gray-300 rounded-lg focus:outline-none focus:border-[#002B49]">
          </div>
        </div>

        <div>
          <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Password</label>
          <div class="relative">
            <span class="absolute inset-y-0 left-0 flex items-center pl-3 text-gray-400 text-sm">
              <i class="fas fa-lock"></i>
            </span>
            <input type="password" required placeholder="••••••••" class="w-full pl-10 pr-4 py-2.5 text-xs bg-gray-50 border border-gray-300 rounded-lg focus:outline-none focus:border-[#002B49]">
          </div>
        </div>

        <div class="flex items-center justify-between text-xs">
          <label class="flex items-center text-gray-600 cursor-pointer">
            <input type="checkbox" class="rounded text-[#002B49] focus:ring-0 mr-2"> Remember me
          </label>
          <a href="#" class="text-blue-800 hover:underline font-semibold">Forgot Password?</a>
        </div>

        <button type="submit" class="w-full bg-[#002B49] text-white py-3 rounded-lg text-xs font-bold uppercase tracking-wider shadow hover:bg-blue-900 transition">
          Gudaha Gal (Login)
        </button>
      </form>

      <!-- 2. REGISTER FORM (Initially Hidden) -->
      <form id="registerForm" class="space-y-4 hidden" onsubmit="event.preventDefault(); alert('Codsigaaga waa la diray!');">
        <div>
          <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Full Name</label>
          <input type="text" required placeholder="Magacaaga oo dhammaystiran" class="w-full px-3 py-2 text-xs bg-gray-50 border border-gray-300 rounded-lg focus:outline-none focus:border-[#002B49]">
        </div>

        <div>
          <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Email Address</label>
          <input type="email" required placeholder="example@gmail.com" class="w-full px-3 py-2 text-xs bg-gray-50 border border-gray-300 rounded-lg focus:outline-none focus:border-[#002B49]">
        </div>

        <div>
          <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Role / Doorkaaga</label>
          <select class="w-full px-3 py-2 text-xs bg-gray-50 border border-gray-300 rounded-lg focus:outline-none focus:border-[#002B49]">
            <option value="student">Student (Arday)</option>
            <option value="parent">Parent (Waalid)</option>
            <option value="teacher">Teacher (Macallin)</option>
          </select>
        </div>

        <div>
          <label class="block text-xs font-bold text-gray-700 uppercase mb-1">Password</label>
          <input type="password" required placeholder="••••••••" class="w-full px-3 py-2 text-xs bg-gray-50 border border-gray-300 rounded-lg focus:outline-none focus:border-[#002B49]">
        </div>

        <button type="submit" class="w-full bg-yellow-600 text-white py-3 rounded-lg text-xs font-bold uppercase tracking-wider shadow hover:bg-yellow-700 transition">
          Diiwaangeli (Register)
        </button>
      </form>

    </div>
  </div>

  <!-- JavaScript to switch tabs -->
  <script>
    function switchTab(tab) {
      const loginForm = document.getElementById('loginForm');
      const registerForm = document.getElementById('registerForm');
      const loginBtn = document.getElementById('loginTabBtn');
      const registerBtn = document.getElementById('registerTabBtn');

      if (tab === 'login') {
        loginForm.classList.remove('hidden');
        registerForm.classList.add('hidden');
        loginBtn.className = "w-1/2 py-3 text-center border-b-2 border-[#002B49] text-[#002B49] font-bold transition";
        registerBtn.className = "w-1/2 py-3 text-center text-gray-400 hover:text-gray-600 border-b-2 border-transparent transition";
      } else {
        loginForm.classList.add('hidden');
        registerForm.classList.remove('hidden');
        registerBtn.className = "w-1/2 py-3 text-center border-b-2 border-[#002B49] text-[#002B49] font-bold transition";
        loginBtn.className = "w-1/2 py-3 text-center text-gray-400 hover:text-gray-600 border-b-2 border-transparent transition";
      }
    }
  </script>

</body>
</html>
