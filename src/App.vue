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
            <div v-for="(conversa,index) in conversas" :key="conversa.index" @click="indiceAtivo = index" class="card-contact" >
              <img class="contact-picture" v-bind:src="conversa.picture" alt="profile">
              <div class="group-contact">
                <div class="name-date">
                  <div class="contact-name">{{conversa.usuario}}</div>
                  <div class="date">{{conversa.mensagens.at(-1).horario}}</div>
                </div>
                
                <div class="last-message">{{conversa.mensagens.at(-1).Conteudo}}</div>
              </div>              
            </div>            
          </div>
          
        </div>
        <div class="chats">
          <div class="description">
              <div class="user">
                <img class="header-avatar" v-bind:src="conversas[indiceAtivo].picture" alt="profile">
                <span>{{conversas[indiceAtivo].usuario}}</span>
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
          <div class="list-messages">
             <Mensagem
              v-for="(mensagem, index) in conversas[indiceAtivo].mensagens"
              :key="index"
              :conteudo="mensagem.Conteudo"
              :horario="mensagem.horario"
              :verde="mensagem.verde"
             />
          </div>
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

import conversasIniciais from '../public/js/dados'
import Mensagem from '../public/component_message.vue'
  
export default{
  data: function(){
    return{
      conversas: conversasIniciais,
      indiceAtivo: 0
    }      
  },
  components:{
    Mensagem
  }
}
</script>