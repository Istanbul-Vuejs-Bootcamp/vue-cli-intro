<template>
    <div class="mt-5 px-2">
        <div class="row">
        <div class="col-sm-6">
            <ul>
                <li v-for="user in users">
                    <a @click="selectedUser=user"
                       class="text-danger">{{ `${user.name} ${user.surname}` }}
                    </a>
                    <IdentityComponent
                        :name="user.name"
                        :surname="user.surname"
                        :driver-license-object="user.driverLicense"
                    />
                </li>
            </ul>
        </div>
        <div class="col-sm-6">
            <IdentityComponent v-if="selectedUser != null"
                :name="selectedUser.name"
                :surname="selectedUser.surname"
                :driverLicenseObject="selectedUser.driverLicense"
            />
        </div>
        </div>
    </div>
</template>

<script>
import IdentityComponent from "./components/IdentityComponent";
export default {
    name: 'App',
    components: {
        IdentityComponent,
    },
    data() {
        return {
            users: [
                {
                    name: 'John',
                    surname: 'Doe',
                    driverLicense: {
                        photo: 'https://randomuser.me/api/portraits/men/45.jpg',
                        licenseId: 'ABC56524',
                        licenseType: 'B/A2',
                        publishDate: '01.05.2019',
                        expireDate: '01.05.2030',
                    },
                    adress: {
                        city: '',
                        postCode: '',
                    }
                },
                {
                    name: 'Kobe', surname: 'Braynt',
                    driverLicense: {
                        photo: 'https://randomuser.me/api/portraits/men/62.jpg',
                        licenseId: 'YTG58220',
                        licenseType: 'A/A2',
                        publishDate: '05.05.2019',
                        expireDate: '05.05.2030',
                    },
                    adress: {
                        city: '',
                        postCode: '',
                    }
                },
                {
                    name: 'Jenifer', surname: 'Lopez',
                    driverLicense: {
                        photo: 'https://randomuser.me/api/portraits/women/67.jpg',
                        licenseId: '852TRTS00',
                        licenseType: 'B/A2',
                        publishDate: '01.01.2015',
                        expireDate: '01.01.2025',
                    },
                    adress: {
                        city: '',
                        postCode: '',
                    }
                }
            ],
            selectedUser: null,
        }
    },
}
</script>

