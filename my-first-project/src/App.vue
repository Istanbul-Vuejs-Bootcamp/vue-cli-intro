<template>
  <div>
    <HelloWorld name="Mustafa" surname="Demir" :user="myUser" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      myUser: {
        name: 'John',
        surname: 'Doe',
      }
    }
  },
}
</script>
