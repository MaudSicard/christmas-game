# 🌍 Découvre un pays et sa recette

Clique sur le bouton ci-dessous pour tirer au sort un pays :

<button onclick="afficherPopup()">🎲 Afficher un pays</button>

<div id="overlay" style="display:none;" class="overlay">
  <div class="popup">
    <p id="popup-content"></p>
    <button onclick="afficherPopup()">🔁 Rejouer</button>
    <button onclick="fermerPopup()">❌ Fermer</button>
  </div>
</div>

<style>
.overlay {
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 999;
  animation: fadeIn 0.5s ease forwards;
}

.popup {
  position: absolute;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 20px;
  border-radius: 10px;
  text-align: center;
  min-width: 250px;
  animation: slideUp 0.4s ease forwards;
  box-shadow: 0 0 15px rgba(0,0,0,0.3);
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from { transform: translate(-50%, 60%); opacity: 0; }
  to { transform: translate(-50%, -50%); opacity: 1; }
}

.popup a {
  font-size: 20px;
  text-decoration: none;
  color: #0077cc;
  font-weight: bold;
}
</style>

<script>
function afficherPopup() {
  const pays = [
    { nom: "France", lien: "countries/france.md" },
    { nom: "Italie", lien: "countries/italie.md" },
    { nom: "Japon", lien: "countries/japon.md" },
    { nom: "Mexique", lien: "countries/mexique.md" },
    { nom: "Inde", lien: "countries/inde.md" },
    { nom: "Maroc", lien: "countries/maroc.md" },
    { nom: "Thailande", lien: "countries/thailande.md" },
    { nom: "Brésil", lien: "countries/bresil.md" },
    { nom: "Grèce", lien: "countries/grece.md" },
    { nom: "Vietnam", lien: "countries/vietnam.md" }
  ];
  const choix = pays[Math.floor(Math.random() * pays.length)];
  const message = `🌍 <a href="${choix.lien}">${choix.nom}</a>`;
  document.getElementById("popup-content").innerHTML = message;
  document.getElementById("overlay").style.display = "block";
}

function fermerPopup() {
  document.getElementById("overlay").style.display = "none";
}
</script>
