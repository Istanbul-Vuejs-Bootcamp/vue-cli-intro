<template>
    <div style="width: 450px">
      <userForm @userSubmit="userAdd" ref="myUserForm" />
      <br>
      <userList :userList="userList"
                @onUpdate="setUpdateUserData"  />
    </div>
</template>

<script>
   import userForm from "./components/userForm";
   import userList from "./components/userList";
    export default {
      name: 'App',
      components: {
        userForm, userList,
      },
      data() {
        return {
            userList: [],
        }
      },
      methods: {
         userAdd(data) {
             this.userList.push(data);
         },
         setUpdateUserData(data) {
            this.$refs.myUserForm.formModel = {...data }
         }
      },
    }
</script>
