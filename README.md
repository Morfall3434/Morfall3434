- 👋 Hi, I’m @Morfall3434
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Morfall3434/Morfall3434 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Empire Trading Funds - Deviens un trader financé</title>
  <link rel="stylesheet" href="styles.css">
  <script defer>
    // Fonction de gestion des utilisateurs en localStorage (fonctionnel côté client pour tester)
    const users = JSON.parse(localStorage.getItem('users') || '{}');
    function registerUser() {
      const email = document.getElementById('regEmail').value;
      const password = document.getElementById('regPassword').value;
      if (users[email]) {
        alert('Utilisateur déjà enregistré.');
      } else {
        users[email] = { password };
        localStorage.setItem('users', JSON.stringify(users));
        alert('Inscription réussie. Vous pouvez vous connecter.');
        window.location.href = '#login';
      }
    }
    function loginUser() {
      const email = document.getElementById('logEmail').value;
      const password = document.getElementById('logPassword').value;
      if (users[email] && users[email].password === password) {
        localStorage.setItem('loggedIn', email);
        document.getElementById('authSection').classList.add('hidden');
        document.getElementById('dashboard').classList.remove('hidden');
        document.getElementById('userEmail').textContent = email;
      } else {
        alert('Identifiants incorrects.');
      }
    }
    function logoutUser() {
      localStorage.removeItem('loggedIn');
      location.reload();
    }
    window.onload = () => {
      if (localStorage.getItem('loggedIn')) {
        document.getElementById('authSection').classList.add('hidden');
        document.getElementById('dashboard').classList.remove('hidden');
        document.getElementById('userEmail').textContent = localStorage.getItem('loggedIn');
      }
    }
  </script>
</head>
<body class="bg-gray-900 text-white">
  <nav class="bg-gray-800 px-6 py-4 flex justify-between">
    <div class="text-xl font-bold text-blue-400">Empire Trading Funds</div>
    <div>
      <a href="#challenges" class="mr-4 hover:text-blue-300">Challenges</a>
      <a href="#about" class="mr-4 hover:text-blue-300">À propos</a>
      <a href="#services" class="mr-4 hover:text-blue-300">Nos Services</a>
      <a href="#login" class="mr-4 hover:text-blue-300">Connexion</a>
      <a href="#signup" class="hover:text-blue-300">Inscription</a>
    </div>
  </nav>

  <header class="text-center py-20 bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1581092580491-336c58b5d7f5');">
    <h1 class="text-4xl md:text-6xl font-bold text-blue-400">Empire Trading Funds</h1>
    <p class="mt-4 text-xl">Relève notre challenge et accède à des comptes financés jusqu'à 20 000 €</p>
  </header>

  <section id="challenges" class="max-w-5xl mx-auto p-6">
    <h2 class="text-3xl font-semibold text-blue-400 mb-6">Nos Challenges</h2>
    <div class="grid md:grid-cols-2 gap-6">
      <div class="bg-gray-800 p-6 rounded-xl shadow">
        <h3 class="text-xl font-semibold">Challenge Classique (2 étapes)</h3>
        <p>Étape 1 : Objectif 12%<br>Étape 2 : Objectif 8%</p>
        <p>Perte max jour : 4%<br>Perte totale : 8%</p>
      </div>
      <div class="bg-gray-800 p-6 rounded-xl shadow">
        <h3 class="text-xl font-semibold">Challenge Express (1 étape)</h3>
        <p>Objectif unique : 11%</p>
        <p>Perte max jour : 3%<br>Perte totale : 8%</p>
      </div>
    </div>
  </section>

  <section id="about" class="max-w-5xl mx-auto p-6">
    <h2 class="text-3xl font-semibold text-blue-400 mb-6">À propos de nous</h2>
    <p>Empire Trading Funds est une plateforme innovante qui aide les traders à développer leurs compétences en gérant des fonds financiers de manière responsable. Nous offrons un environnement sécurisé pour tester vos stratégies tout en bénéficiant d'un capital financier.</p>
  </section>

  <section id="services" class="max-w-5xl mx-auto p-6">
    <h2 class="text-3xl font-semibold text-blue-400 mb-6">Nos Services</h2>
    <ul class="list-disc pl-6 space-y-2">
      <li>Formation complète au trading en ligne</li>
      <li>Accès à des comptes financés après validation de challenge</li>
      <li>Support dédié pour maximiser vos chances de succès</li>
      <li>Suivi en temps réel de vos performances et de vos retraits</li>
    </ul>
  </section>

  <section id="authSection" class="max-w-4xl mx-auto py-12 px-6">
    <div class="grid md:grid-cols-2 gap-8">
      <div id="signup">
        <h2 class="text-2xl font-semibold text-blue-400 mb-4">Inscription</h2>
        <input type="email" id="regEmail" placeholder="Email" class="w-full p-2 mb-2 rounded text-black">
        <input type="password" id="regPassword" placeholder="Mot de passe" class="w-full p-2 mb-2 rounded text-black">
        <button onclick="registerUser()" class="bg-blue-500 px-4 py-2 rounded hover:bg-blue-600">Créer un compte</button>
      </div>
      <div id="login">
        <h2 class="text-2xl font-semibold text-blue-400 mb-4">Connexion</h2>
        <input type="email" id="logEmail" placeholder="Email" class="w-full p-2 mb-2 rounded text-black">
        <input type="password" id="logPassword" placeholder="Mot de passe" class="w-full p-2 mb-2 rounded text-black">
        <button onclick="loginUser()" class="bg-green-500 px-4 py-2 rounded hover:bg-green-600">Se connecter</button>
      </div>
    </div>
  </section>

  <section id="dashboard" class="hidden max-w-4xl mx-auto py-12 px-6">
    <h2 class="text-3xl text-blue-400 font-semibold mb-6">Bienvenue, <span id="userEmail"></span></h2>
    <div class="grid gap-4">
      <div class="bg-gray-800 p-4 rounded">
        <h3 class="text-xl font-semibold mb-2">Tableau de bord</h3>
        <p>Suivi de performance en temps réel : à connecter via API MT5/Ctrader (à venir)</p>
      </div>
      <div class="bg-gray-800 p-4 rounded">
        <h3 class="text-xl font-semibold mb-2">Retraits</h3>
        <p>Fonctionnalité de retrait disponible après vérification du compte.</p>
      </div>
      <button onclick="logoutUser()" class="mt-4 bg-red-500 px-4 py-2 rounded hover:bg-red-600">Se déconnecter</button>
    </div>
  </section>

  <footer class="bg-gray-800 py-6 text-center">
    <h3 class="text-blue-400 text-xl mb-2">Conditions de Trading</h3>
    <ul class="text-sm space-y-1">
      <li>Trading autorisé du lundi au vendredi uniquement</li>
      <li>Interdiction de trader les week-ends</li>
      <li>Pause obligatoire 10 min avant et après les annonces économiques</li>
      <li>Copy-trading, bots HFT, martingale interdits</li>
      <li>Levier au choix : 1:10, 1:30 ou 1:50</li>
    </ul>
    <p class="mt-4 text-xs text-gray-400">&copy; 2025 Empire Trading Funds. Tous droits réservés.</p>
  </footer>
</body>
</html>
