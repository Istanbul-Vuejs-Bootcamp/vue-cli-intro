<template>
    <div>
        <form @submit.prevent="saveUser">
        <div>
            <label>Name</label><br>
            <input type="text" v-model="formModel.name" style="width: 100%" />
        </div>
        <br>
        <div>
            <label>Surname</label><br><br>
            <input type="text" v-model="formModel.surname" style="width: 100%" />
        </div>
        <br>
        <div>
            <label>City</label><br><br>
            <select style="width: 100%" v-model="formModel.city">
                <option value="01">ADANA</option>
                <option value="34">İSTANBUL</option>
                <option value="35">İZMİR</option>
            </select>
        </div>
        <br>
        <div>
            <label>is active</label><br>
            <input type="checkbox" v-model="formModel.isActive" />
        </div>

        <div>
            <label>Gender</label><br>
            <input type="radio" id="M" name="gender" value="MAN" v-model="formModel.gender">
            MAN
            <input type="radio" id="W" name="gender" value="WOMAN" v-model="formModel.gender">
            WOMAN
        </div>
        <br><br>
        <div>
            <button type="submit" >SAVE</button>
        </div>
    </form>
    </div>
</template>

<script>
    export default {
        name: "userForm",
        data() {
            return {
                formModel: {
                    name: '',
                    surname: '',
                    city: null,
                    isActive: false,
                    gender: null,
                },
            }
        },
        methods: {
            saveUser() {
                this.$emit('userSubmit', {...this.formModel});
                this.clearForm();
            },
            clearForm() {
                this.formModel = {
                    name: '',
                    surname: '',
                    city: null,
                    isActive: false,
                    gender: null,
                };
            }
        },
    }
</script>
