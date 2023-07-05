<script setup>
import moment from 'moment';

import { BenefitTag, SkillTag } from '../components/';
import { Calendar, Company, Location, Salary, Vacancy } from '../icons/';

const { jobData } = defineProps(['jobData']);
const { 
    title,
    skillsRequired,
    company,
    location,
    salary,
    numVacancies,
    created_at,
    benefits,
    logo_url,
    job_url
 } = jobData;
</script>

<template>
    <div class="card m-3 border job-card">
        <div class="card-body p-2 p-md-3">
            <div class="row align-items-center">
                <div class="col-3 col-md-1 justify-content-center align-items-center">
                    <img class="rounded" :src="logo_url" alt="Logo empresa" width="70" height="70" />
                </div>
                <div class="col-9 col-md-11">
                    <div class="row align-items-center">
                        <div class="col mb-2">
                            <a :href="job_url" class="text-light stretched-link d-inline d-md-inline-flex" target="_blank">
                                <h5 class="me-3 mb-0">{{ title }}</h5>
                                <section class="pl-md-2 d-inline d-md-inline-flex align-items-center text-truncate">
                                    <SkillTag v-for="(skill, index) in skillsRequired" :key="index" :skillData="skill" />
                                </section>
                            </a>
                        </div>
                    </div>
                    <div class="row pl-md-2 mt-1 flex-column flex-md-row secondary-info">
                        <div class="text-capitalize col d-flex align-items-center">
                            <Company class="me-2" />
                            <span>{{ company }}</span>
                        </div>
                        <div class="text-capitalize col d-flex align-items-center">
                            <Location class="me-2" />
                            <span>{{ location }}</span>
                        </div>
                        <div class="text-capitalize col d-flex align-items-center">
                            <Salary class="me-2" />
                            <span>{{ salary }}</span>
                        </div>
                        <div class="text-capitalize col d-flex align-items-center">
                            <Vacancy class="me-2" />
                            <span>{{ numVacancies }} {{ (numVacancies > 1) ? 'Vacantes' : 'Vacante' }}</span>
                        </div>
                        <div class="text-capitalize col d-flex align-items-center">
                            <Calendar class="me-2" />
                            <span>{{ moment(created_at).fromNow()  }}</span>
                        </div>
                        <div class="text-capitalize col d-flex align-items-center">
                            <BenefitTag v-for="(benefit, index) in benefits" :key="index" :benefitData="benefit" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    a {
        text-decoration: none;
    }
    .border{
        border-color: #262d2f;
    }

    .job-card {
        background-color: #181A1B;
    }

    .job-card:hover{
        -webkit-box-shadow: 1px 4px 4px 1px rgba(157, 121, 121, 0.38);
        -moz-box-shadow: 1px 4px 4px 1px rgba(157, 121, 121, 0.38);
        box-shadow: 1px 4px 4px 1px rgba(157, 121, 121, 0.38);
    }

    .secondary-info{
        font-size: 0.9em;
    }
</style>