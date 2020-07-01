<template>
    <div>
        RSS
        <button v-on:click="shitty_api">
            Count is: {{ state.count }}, double is: {{ state.double }}
        </button>
    </div>
</template>

<script>
import { reactive, computed, onMounted } from "vue";
// , onMounted

const main = function()
{
    const double = computed(() => state.count * 2);
    const shitty_api = () => { state.count++ };
    const state = reactive({
        count: 0,
        double,
    });

    onMounted( () =>
    {
        console.log( "Hello World!" );
    });

    return {
        state,
        shitty_api
    };
};

export default {
    setup: main,
}
</script>
