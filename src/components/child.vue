<template>
<div >
    child
    <h1>{{msg}}</h1>
    <h1>reaciveGift:{{msg2.gift}}</h1>
</div>
</template>
<script lang="ts" setup >
import { ref,onMounted } from "@vue/runtime-core"
const emit = defineEmits(['tofather'])
const toFather = ref('hello,msg is from son')
emit('tofather',toFather)
    
    const props = defineProps({
        msg:String,
        msg2:Object
    })
    onMounted(()=>{
        console.log(props)
    })
</script>