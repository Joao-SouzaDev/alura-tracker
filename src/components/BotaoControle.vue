<template>
    <button class="button">
        <span class="icon">
            <i class="fas"></i>
        </span>
        <span>{{ texto }}</span>
    </button>
</template>

<script lang="ts">
export default {
    props: {
        texto: String
    }
}
</script>