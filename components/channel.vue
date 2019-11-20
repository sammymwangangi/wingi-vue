<template>
    <div class="channel">
        <h1>{{ channel }}</h1>
    </div>
    <!-- <nuxt-link :to="'jokes/' + id">
        <div class="joke">
        <p>{{ joke }}</p>
        </div>
    </nuxt-link> -->
</template>


<script>
export default {
    name: 'channel',
    props: ['channel', 'id']
};
</script>

<style>
.channel {
    padding: 1rem;
    border: 1px dotted #cccccc;
    margin: 1rem 0;
}
</style>