<template>
    <div>
        <h1 >{{str}}</h1>
    </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
    name:'Test',
    props:{
        str:String
    }
})
</script>