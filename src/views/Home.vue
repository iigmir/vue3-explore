<template>
    <div class="home">
        <img alt="Vue logo" src="../assets/logo.png" />
        <RSSAPP />
    </div>
</template>

<script>
import RSSAPP from "../components/RSSAPP.vue";

export default {
    name: "Home",
    components: {
        RSSAPP,
    },
}
</script>
