<script setup>
const props = defineProps(['tarefaTemp', 'trocarFiltro', 'editaTarefaTemp', 'cadastraTarefa']);
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
        <div class="col">
            <input
            v-model="props.tarefaTemp"
            @input="props.editaTarefaTemp"
            required
            type="text"
            placeholder="Digite aqui a descrição da tarefa"
            class="form-control"
            />
        </div>
        <div class="col-md-2">
            <button type="submit" class="btn btn-primary">Cadastrar</button>
        </div>
        <div class="col-md-2">
            <select @change="props.trocarFiltro" class="form-control">
            <option value="todas">Todas tarefas</option>
            <option value="pendentes">Todas pendentes</option>
            <option value="finalizadas">Todas finalizadas</option>
            </select>
        </div>
        </div>
    </form>
</template>
