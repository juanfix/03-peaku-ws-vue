<script setup>
    const { skillData } = defineProps(['skillData']);
</script>

<template>
    <div class="me-2 px-2 skill-tag border border-dark text-dark text-capitalize">
        {{ skillData }}
    </div>
</template>

<style>
    .skill-tag{
        border-radius: 10px;
        font-size: small;
        margin-bottom: 0px !important;
    }
</style>