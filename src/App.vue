<script setup lang="ts">
import { ref } from 'vue';
import { useToast } from 'primevue/usetoast';

const text = ref();
const toast = useToast();
const greet = () => {
  toast.add({ severity: 'success', summary: 'Changed', detail: text.value })
}
</script>

<template>
  <Toast></Toast>
  <div class="container">
    <span class="p-float-label p-input-filled" style="margin-right:.5rem">
      <InputText id="txt" type="text" v-model="text" />
      <label for="txt">A note</label>
    </span>
    <Button label="Greet" @click="greet" icon="pi pi-user"></Button>
  </div>

</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
</style>
