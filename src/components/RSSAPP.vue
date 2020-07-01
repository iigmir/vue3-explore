<template>
    <div>
        RSS
        <button @click="increment">
            Count is: {{ state.count }}, double is: {{ state.double }}
        </button>
    </div>
</template>

<script>
import { reactive, computed } from "vue";

export default {
    setup()
    {
        const double = computed(() => state.count * 2);
        const increment = () => { state.count++ };
        const state = reactive({
            count: 0,
            double,
        });
        
        return {
            state,
            increment
        };
    },
}
</script>