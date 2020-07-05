<template>
    <table>
        <thead>
        <tr>
            <td>Name</td>
            <td>Surname</td>
            <td>City</td>
            <td>IsActive</td>
            <td>Gender</td>
            <td>Actions</td>
        </tr>
        </thead>
        <tbody>
        <tr v-for="user in userList">
            <td>{{ user.name }}</td>
            <td>{{ user.surname }}</td>
            <td>{{ user.city }}</td>
            <td>{{ user.isActive }}</td>
            <td>{{ user.gender }}</td>
            <td>
                <a @click="gotoUpdate(user)">Update</a>
            </td>
        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        name: "userList",
        props: {
            userList: {
                type: Array,
                required: true,
            }
        },
        methods: {
            gotoUpdate(user) {
                this.$emit('onUpdate', user);
            }
        }
    }
</script>

<style scoped>

</style>
