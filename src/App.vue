<template>
  <div class="section">
    <div class="container">
      <div class="columns">
        
        <div class="contacts">
          <header>
            <img class="header-avatar" src="https://365psd.com/images/istock/previews/1009/100996291-male-avatar-profile-picture-vector.jpg" alt="profile">
            <div class="header-buttons">
              <div class="header-btn">
                <span class="material-icons header-icon">donut_large</span>
              </div>
              <div class="header-btn">
                <span class="material-icons header-icon">chat</span>
              </div>
              <div class="header-btn">
                <span class="material-icons header-icon">more_vert</span>
              </div>              
            </div>
          </header>

          <div class="search">
            <div class="search-input">
              <span class="material-icons search-icon">search</span>
              <input type="search" placeholder="Procurar ou começar uma nova conversa">
            </div>
            
          </div>
          
          <div class="contactslist">
            <p v-for="conversa in conversas" :key="conversa.usuario">{{conversa.usuario}}</p>
            <p>...</p>
          </div>
          
        </div>
        <div class="chats">
          <div class="description">
              <div class="user">
                <img class="header-avatar" src="https://365psd.com/images/istock/previews/1009/100996291-male-avatar-profile-picture-vector.jpg" alt="profile">
                <span>Nome Contato</span>
              </div>              
              <div class="header-buttons">      
                <div class="header-btn">
                  <span class="material-icons header-icon">search</span>
                </div>
                <div class="header-btn">
                  <span class="material-icons header-icon">more_vert</span>                
                </div>              
              </div>
                     
          </div>
          <p>...</p>
        </div>
      </div>
    </div>
  </div>
  <!-- <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Welcome to Your Vue.js App</h1>
  </div> -->
</template>

<script>

import conversasIniciais from '../public/js/scripts'
  
export default{
  data: function(){
    return{
      conversas: conversasIniciais
    }      
  }
}
</script>