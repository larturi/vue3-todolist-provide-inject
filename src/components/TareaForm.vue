<template>
  <form @submit.prevent="agregarTarea">

    <div class="input-group mb-3">
        <input type="text"
               placeholder="Ingrese tarea"
               class="form-control"
               v-model.trim="texto">
        <div class="input-group-append">
            <button class="btn btn-primary radio">
                Agregar
            </button>
        </div>
    </div>

  </form>
</template>

<script>
import { inject, ref } from 'vue';
export default {
    setup(){
        const texto = ref('');
        const tareas = inject('tareas');

        const agregarTarea = () => {
            if(texto.value === ''){
                return console.log('texto vacio');
            }
            const tarea = {
                texto: texto.value,
                estado: false,
                id: Date.now()
            }

            tareas.value.push(tarea);

            texto.value = '';
        }

        return {agregarTarea, texto};
    }
}
</script>

<style scoped>
    .btn, input[type=text] {
       border-radius: 0 !important;
    }
</style>