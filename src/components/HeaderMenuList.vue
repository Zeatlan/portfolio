<template>
  <div class="content">
    <div class="menu-list">
      <!-- Home -->
      <div class="link">
        <RouterLink to="/">Accueil</RouterLink>
        <span>// En apprendre plus sur moi</span>
      </div>

      <!-- Technology -->
      <div class="link">
        <RouterLink to="/about">Technologies</RouterLink>
        <span>// Ma liste de mes compétences</span>
      </div>

      <!-- Projects -->
      <div class="link">
        <RouterLink to="/about">Mes projets</RouterLink>
        <span>// La liste des projets que j'ai réalisé</span>
      </div>

      <!-- Contact -->
      <div class="link">
        <RouterLink to="/about">Me contacter</RouterLink>
        <span>// Envie de travailler avec moi ?</span>
      </div>
    </div>
  </div>
</template>