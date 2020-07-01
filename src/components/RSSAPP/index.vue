<template>
    <div>
        RSS
        <button v-on:click="shitty_api">
            Count is: {{ state.count }}, double is: {{ state.double }}
        </button>
        <p>{{ state }}</p>
    </div>
</template>

<script>
import { reactive, computed, onMounted } from "vue";
import axios from "axios";

const setup = function()
{
    const shitty_api = () => { state.count++ };

    const state = reactive({
        count: 0,
        double: computed(() => state.count * 2),
        rss: "",
    });

    const rss_request = async() =>
    {
        // const url = "https://dq.yam.com/rss.php";
        // const url = "https://medium.com/feed/@dwu182";
        const url = "https://pansci.asia/feed";
        try {
            const req = await axios.get( url );
            state.rss = req.data;
        } catch (error) {
            state.rss = error;
        } finally {
            console.log( state );
        }
        
    };

    onMounted( () =>
    {
        rss_request();
    });

    return {
        state,
        shitty_api
    };
};

export default {
    setup,
}
</script>
