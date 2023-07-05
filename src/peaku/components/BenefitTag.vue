<script setup>
    import { Calendar, Check, Check2, Clock, Heart, Joystick, Location, Padlock, Salary, Smile, Vacancy, World } from '../icons/';
    const { benefitData } = defineProps(['benefitData']);
</script>

<template>
    <span class="me-1 px-2 py-1 skill-tag text-truncate border border-dark text-dark text-capitalize hovertext" :title="benefitData">
        <Calendar v-if="benefitData === 'Flexibilidad de horarios'" class="d-flex justify-content-center" />
        <Check v-else-if="benefitData === 'Capacitaciones'" class="d-flex justify-content-center" />
        <Check2 v-else-if="benefitData === 'Certificaciones'" class="d-flex justify-content-center" />
        <Clock v-else-if="benefitData === 'Horario flexible' || benefitData === 'Día completo o medio día libre de cumpleaños'" class="d-flex justify-content-center" />
        <Heart v-else-if="benefitData === 'Medicina prepagada'" class="d-flex justify-content-center" />
        <Joystick v-else-if="benefitData === 'Juegos online'" class="d-flex justify-content-center" />
        <Location v-else-if="benefitData === 'Trabajo remoto' || benefitData === 'Trabajo remoto parcial' || benefitData === 'Lecciones en programación'" class="d-flex justify-content-center" />
        <Padlock v-else-if="benefitData === 'Seguros'" class="d-flex justify-content-center" />
        <Salary v-else-if="benefitData === 'Vesting'" class="d-flex justify-content-center" />
        <Smile v-else-if="benefitData === 'Celebración de días especiales' || benefitData === 'Fiesta de fin de año'" class="d-flex justify-content-center" />
        <Vacancy v-else-if="benefitData === 'Ambiente de trabajo amigable' || benefitData === 'Team building'" class="d-flex justify-content-center" />
        <World v-else class="d-flex justify-content-center" />
    </span>
</template>

<style scoped>

    .hovertext{
        z-index: 1;
    }

    .hovertext:hover {
        cursor: pointer;
    }
</style>