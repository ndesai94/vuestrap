<template>
  <b-table striped hover :items="allData" :fields="fields"></b-table>
</template>

<script>

export default {
    name: "Table",
    props: ['allData'],
    data () {
        return {
            fields: ['email', 'name', { key: 'food', label: 'Favorite Food' }]
        }
    }
}
</script>