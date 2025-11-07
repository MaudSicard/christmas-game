# 🌍 Découvre un pays et sa recette

Clique sur le bouton ci-dessous pour tirer au sort un pays :

<div style="margin-top:20px;">
  <button class="styled-button" onclick="afficherPays()">🎲 Afficher un pays</button>
</div>

<div id="resultat" class="fade-in" style="margin-top:20px; font-size:20px; font-weight:bold;"></div>

[⬅️ Retour à l'accueil](index.md)

<style>
.styled-button {
  background-color: #0077cc;
  color: white;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 8px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
.styled-button:hover {
  background-color: #005fa3;
}

.fade-in {
  opacity: 0;
  transition: opacity 0.6s ease-in-out;
}
.fade-in.visible {
  opacity: 1;
}

.home-link {
  font-size: 18px;
  text-decoration: none;
  color: #0077cc;
  font-weight: bold;
}
.home-link:hover {
  text-decoration: underline;
}
</style>

<script>
function afficherPays() {
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
  const message = `🌍 <a href="${choix.lien.replace('.md', '.html')}" style="color:#0077cc; text-decoration:none;">${choix.nom}</a>`;

  const resultat = document.getElementById("resultat");
  resultat.innerHTML = message;
  resultat.classList.remove("visible");
  void resultat.offsetWidth; // force reflow
  resultat.classList.add("visible");
}
</script>
