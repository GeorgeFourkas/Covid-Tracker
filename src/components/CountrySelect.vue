<template>
    <select @change="onChange" v-model="selected" class="form-select mt-1 block w-full border p-3 rounded mt-10">
        <option selected="selected">Επιλέξτε Χώρα</option>
        <option v-for="country in countries" :value="country.ID">{{ country.Country }}</option>
    </select>
</template>

<script>
export default {
    name: "CountrySelect",
    props: ['countries'],
    data() {
        return {

            selected: 0
        }
    },
    emits:['country-selected'],
    methods: {
        onChange() {
            const country = this.countries.find((item) => item.ID === this.selected)
            this.$emit('country-selected', country)
        }
    }
}
</script>


