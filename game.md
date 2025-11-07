# 🌍 Découvre un pays et sa recette

Clique sur le bouton ci-dessous pour tirer au sort un pays :

<button onclick="afficherPopup()">Afficher un pays</button>

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
  const message = `🌍 <a href="${choix.lien}" target="_blank">${choix.nom}</a>`;
  const popup = window.open("", "popup", "width=300,height=150");
  popup.document.write(`<p style="font-size:18px;text-align:center;margin-top:40px;">${message}</p>`);
}
</script>
