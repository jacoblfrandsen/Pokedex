<template>
<div id="app">
  <div class="header">
    <router-link to="/">
      <div class="logo">
        <img src="/PokemonLogo.jpg" style="width:15em; height:7em;">
      </div>
    </router-link>
    <div class="title">
      <h1>Welcome to your own personal Pokedex</h1>
      
    </div>
    <div class = title>
      <h3>With guess the Pokemon game</h3>
    </div>
    <div>
      
    </div>
  </div>
  <div class="content">
    <router-view />
  </div>
  <div class = footer>
        <router-link to="/guess" class = footer1>Guess Pokemon </router-link>
        <br>
        <router-link to="/admin" class = footer1>Add/Delete Pokemon</router-link>
        <br>
        <a href="https://github.com/jacoblfrandsen/pokedex.git">Github Repository</a> 
  </div>
  
</div>
</template>

<style>
html {
  box-sizing: border-box;
}

body {
  font-family: '', Cambria;
  font-size: 16px;
  background: #fff;
  padding: 0px;
  margin: 0px;
}

/* Header */
.header {
  display: flex;

  flex-direction: column;
  padding: 10px 100px 0px 100px;
  background-color: #ffffff;
  color: #1C454F;
  content: center;
  align-items: center;
}

.title {
  margin-top: 40px;
}

.title h1 {
  font-size: 30px;
}



.content {
  padding: 20px 100px;
  min-height: 500px;
}

/* Footer */
.footer {
  display: flex;
  flex-direction: column;
  height: 150px;
  padding: 50px 100px 0px 50px;
  background: #5b5bd3;
  font-size: 12px;
  align-items: center;
}

.footer a {
  color: #000;
  align-content: center;
}

.footer1{
  font-size: 24px;
  
}

h1 {
  font-size: 20px;
}

h2 {
  font-size: 14px;
}


</style>
