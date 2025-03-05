<template>
   <ProfileInfo
     photo="https://avatars.githubusercontent.com/u/107324700?v=4"
     title="Dêvide Andrio"
     subtitle="devide.andrio@gmail.com"
   />
 
   <section class="max-w-xs mx-auto">
     <ButtonAction
       link="https://www.linkedin.com/in/devidealves/"
       icon="🔗"
       text="Linkedin"
     />
     <ButtonAction link="https://github.com/Axion986" icon="😺" text="GitHub" />
     <ButtonAction
       link="https://wa.me/+5541996657402"
       icon="📞"
       text="Whatsapp"
     />
   </section>
      <div class="max-w-xs mx-auto text-center "> 
         <p class="p-2 text-2xl">Minhas Experiências:</p>
      </div>

   <main class="max-w-xs mx-auto">
     <Bussiness :dados="dados_empresa" />
   </main>
 
 
   <!-- Componente Modal -->
   <Modal
     :isOpen="isModalOpen"
     title="Título do Modal"
     content="Este é o conteúdo do modal."
     @close="closeModal"
     @confirm="handleConfirm"
   />
 </template>
 
 <script setup>
 import { ref } from 'vue';
 import Modal from './components/Modal.vue'; // Caminho corrigido
 import Bussiness from './components/Bussiness.vue';
 
 const isModalOpen = ref(false);
 
 const openModal = () => {
   isModalOpen.value = true;
 };
 
 const closeModal = () => {
   isModalOpen.value = false;
 };
 
 const handleConfirm = () => {
   alert('Ação confirmada!');
   closeModal();
 };
 
 // Dados das empresas
 const dados_empresa = [
   {
     bussiness: 'RH Nossa',
     site: 'https://rhnossa.com.br',
     image:
       'https://ccsafoz.wordpress.com/wp-content/uploads/2014/06/rh-nossa_thumb.png?w=128&h=109.png',
     text: 'Coordenador de TI',
   },
   {
     bussiness: 'CWBem ',
     site: 'https://cwbem.com.br',
     image:
       'https://www.cwbem.com.br/wp-content/themes/kakoi/assets/img/logo.png',
     text: 'Engenheiro de Processos',
   },
   {
     bussiness: 'Comp Laser',
     site: 'https://complaser.com.br/',
     image:
       'https://complaser.com.br/wp-content/uploads/2023/01/logo1-240x55.png',
     text: 'Analista de Qualidade',
   },
  
 ];
 </script>
 
 
 
 