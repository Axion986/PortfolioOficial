<template>
  <div class="overflow-x-auto whitespace-nowrap p-4 bg-blue-100">
    <div class="flex flex-col space-y-4">
      <!-- Renderização Dinâmica dos Dados -->
      <div class="flex space-x-5 w-30 h-30">
        <div
          v-for="(empresa, index) in dados"
          :key="index"
          @click="openModalWithDetails(empresa)"
          class="text-sm w-80 flex flex-col items-center space-y-3 bg-white p-4 rounded-lg shadow hover:bg-gray-200 transition cursor-pointer"
        >
          <img
            :src="empresa.image"
            :alt="empresa.bussiness"
            class="w-20 h-10 rounded-full"
          />
          <span class="font-medium text-black-800 text-center">{{
            empresa.bussiness
          }}</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Componente Modal -->
  <Modal
    :isOpen="isModalOpen"
    :title="selectedEmpresa?.bussiness || 'Detalhes da Empresa'"
    :site="selectedEmpresa?.site ||''" 
    :text="selectedEmpresa?.text || 'Texto da Empresa'"
    @close="closeModal"
    @confirm="handleConfirm"
  />
</template>

<script setup>
import { ref } from 'vue';
import Modal from './Modal.vue'; // Caminho corrigido

// Props recebidas do componente pai
const props = defineProps({
  dados: {
    type: Array,
    required: true,
  },
});

// Estado para controlar o modal
const isModalOpen = ref(false);
const selectedEmpresa = ref(null); // Armazena a empresa selecionada

// Abre o modal com os detalhes da empresa
const openModalWithDetails = (empresa) => {
  selectedEmpresa.value = empresa; // Define a empresa selecionada
  isModalOpen.value = true; // Abre o modal
};

// Fecha o modal
const closeModal = () => {
  isModalOpen.value = false;
  selectedEmpresa.value = null; // Limpa a empresa selecionada
};

// Lida com a confirmação do modal
const handleConfirm = () => {
  alert('Ação confirmada!');
  closeModal();
};
</script>
