<template>
    <div class="card bg-secondary">
        <div class="row">
            <div class="col-3 pt-1">
                <img :src="driverLicenseObject.photo" width="100" />
            </div>
            <div class="col-9 text-left text-white">
                <div>{{ name }} {{ surname }}</div>
                <div>{{ driverLicenseObject.licenseId }}</div>
                <div>{{ driverLicenseObject.licenseType }}</div>
                <div>{{ driverLicenseObject.publishDate }}</div>
                <div>{{ driverLicenseObject.expireDate }}</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "IdentityComponent",
        props: {
            name: {
                type: String,
                required: true,
            },
            surname: {
                type: String,
                required: true,
            },
            driverLicenseObject: {
                type: Object,
                required: true,
            }
        }

    }
</script>
