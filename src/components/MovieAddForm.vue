<template>
    <div class="mb-5 px-4 py-3 shadow rounded">
        <h3 class="mb-3">Kino Qo'shish</h3>
        <form @submit.prevent="addNewMovie">
            <div class="d-flex gap-3">
                <input v-model="name" type="text" placeholder="Kinoni Nomi" class="form-control">
                <input v-model.number="viewers" type="number" placeholder="Nechi Marta Ko'rilgan ?" class="form-control">
            </div>
            <button type="submit" class="w-100 btn btn-success mt-3">Qo'shish</button>
        </form>
    </div>
</template>
<script>
export default {
    data(){
        return{
            name:"",
            viewers: ""
        }
    },
    methods: {
        addNewMovie(){
            if(!this.name || !this.name){
                alert("Iltimos Barcha  Inputlarni To'ldiring")
                return
            }

            const newMovie = {
                name : this.name,
                viewers: this.viewers,
                like:false,
                favorite:false
            }

            this.$emit('new-movie', newMovie)

            this.name = "",
            this.viewers = ""
        }
        
    },
}
</script>
<style>
    
</style>