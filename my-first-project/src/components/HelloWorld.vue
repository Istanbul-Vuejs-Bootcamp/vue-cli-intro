<template>
   <div>
     Hello {{ name }} {{ surname }} <br><br>

       Hello {{ user.name }} {{ user.surname }}
   </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        name: {
            type: String,
            default: 'Ömer',
        },
        surname: {
            type: String,
            required: true
        },
        user: {
            type: Object,
            required: true
        }
    },
}
</script>
