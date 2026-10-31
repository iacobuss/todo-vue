<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <div v-if="tarefas != 0" class="pendentes">
        <ul class="list-group mt-4">
            <li class="list-group-item" v-for="tarefa in props.tarefas">
                <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
                <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
                </label>
            </li>
        </ul>
    </div>
    <div v-else class="pendentes mt-4 ms-2">
        <span>Nenhuma tarefa pendente</span>
    </div>

</template>

<style scoped>
    .done {
    text-decoration: line-through;
    } 
</style>
