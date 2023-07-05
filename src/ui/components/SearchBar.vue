<script setup>
    const { searchJob } = defineProps(['searchJob']);
</script>

<template>
    <div class="m-3">
        <form @submit.prevent="(event) => searchJob(event)">
        <div className="input-group rounded">
            <input type="search" className="form-control rounded" name="keyword" placeholder="Search" aria-label="Search" aria-describedby="search-addon" />
            <button className="input-group-text">
                <i className="fa fa-search"></i>
            </button>
        </div>
    </form>
    </div>
</template>

<style lang="scss" scoped>

</style>