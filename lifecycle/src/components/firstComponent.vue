<template>
 <div v-if="isRender">

  <div>Hello. I am first component</div>

  <div>{{ message }}</div>

  <button @click="message = 'hello'">Mesajı Değiştir</button>
 </div>
</template>

<script>
    export default {
       name: "firstComponent",
       data() {
        return {
         message: '',
         isRender: false,
        }
       },

       beforeCreate() {
        console.log('beforeCreate is here');
       },
       created() {
        setTimeout(()=> {
         this.isRender = true;
        }, 2000)
        console.log('created is here');
       },
       beforeMount() {
        console.log('beforeMount is here');
       },
       mounted() {
        console.log('mounted is here');
       },
       beforeUpdate() {
        console.log('beforeUpdate is here');
       },
       updated() {
         console.log('udpated is here');
        },
       beforeDestroy() {
        console.log('beforeDestroy is here');
       },
       destroyed() {
        console.log('destroyed is here');
       }
    }
</script>

<style scoped>

</style>
