<template>
    <div>
        <button @click="isShow = !isShow">Göster / Gizle</button>
        <firstComponent v-if="isShow"/>
        <hr>

        <!-- template tag'i dom'a asla render edilmez -->
        <template v-if="isShow">
            <firstComponent />
        </template>
        <!-- div tag'i dom'a render edilecek (isShow = true ise) -->
        <div v-if="isShow">
            <firstComponent />
        </div>


    </div>
</template>

<script>
    export default {
        name: 'App',
        components: {
            firstComponent: () => import('./components/firstComponent')
        },
        data() {
            return {
                isShow: false,
            }
        },
    }
</script>
