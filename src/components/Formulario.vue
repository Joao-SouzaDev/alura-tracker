<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?">
            </div>
            <div class="column">
                <div class="is-flex is-align-items-center is-justify-content-space-between">
                    <Cronometro :tempoDecorrido="tempoDecorrido" />
                    <BotaoControle :texto="'play'" v-on:click="iniciarContagem" v-bind:class="'fa-play'"/>
                    <BotaoControle :texto="'stop'" v-on:click="finalizarContagem" v-bind:class="'fa-stop'"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Cronometro from './Cronometro.vue';
import BotaoControle from './BotaoControle.vue';
export default defineComponent({
    name: 'FormularioTracker',
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0
        }
    },
    computed: {
        tempoDecorrido(): string {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8)
        }
    },
    methods: {
        iniciarContagem() {
            this.cronometro = setInterval(() => this.tempoEmSegundos++, 1000)

        },
        finalizarContagem() {
            clearInterval(this.cronometro)
            this.tempoEmSegundos = 0;


        }
    },
    components :{Cronometro ,BotaoControle}
})
</script>

<style scoped></style>