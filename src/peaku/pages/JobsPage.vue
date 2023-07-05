<script setup>
import { ref } from 'vue';

import JobCard from '../components/JobCard.vue';
import SearchBar from '../../ui/components/SearchBar.vue'
import { jobsList } from '../data/getJobs';

const jobsListReactive = ref([]);
const allJobsList = jobsList;

jobsListReactive.value = jobsList;

const searchJob = (event) => {
    jobsListReactive.value = allJobsList.filter((job) => 
        job.title.toLowerCase().includes(event.target[0].value.toLowerCase()) || job.skillsRequired.some(skill => {
            return skill.toLowerCase().includes(event.target[0].value.toLowerCase())
        })
    );
}

</script>

<template>
    <main>
        <SearchBar :searchJob="searchJob" />
        <JobCard v-for="job in jobsListReactive" :key="job.id" :jobData ="job" />
    </main>
</template>

<style scoped>

</style>