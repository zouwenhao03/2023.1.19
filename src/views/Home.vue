<template>
  <div class="home">
    <HelloWorld msg="WELOCME"/>
    <Test :str="str" @click="changeStr"/>
    {{fullStr}}
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import Test from '@/components/test.vue';
export default defineComponent({
  name: 'Home',
  components: {
    HelloWorld,
    Test,
  },
  data(){
    return{
      str:'test'
    }
  },
  methods:{
    changeStr(){
      this.str = 'you'
    }
  },
  computed:{
    fullStr(){
      if(this.str == 'you'){
        return 'WELCOM YOU'
      }else{
        return null
      }
    }
  }
});
</script>
