<template>
    <section>
        <strong>
            {{ tempoDecorrido }}
        </strong>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: "CompCronometro",
    props: {
        tempoDecorrido: {type: String,required: true}
    }
})
</script>