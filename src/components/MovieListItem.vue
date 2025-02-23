<template>
    <li class="list-group-item" style="background-color: transparent;" :class="{ 'text-warning': movie.favorite }">
        <div class="d-flex alignl-itmes-center justify-content-between">
            <div>
                <h4>{{ movie.name }}</h4>
            </div>
            <div class="d-flex align-items-center gap-5">
                <h4 class="mb-0 me-5">{{ movie.viewers }}</h4>
                <div class="list-item__icons d-flex gap-3">
                    <button @click="$emit('toggle-favorite', movie)" type="button" class="btn btn-sm">
                        <i class="bi bi-film text-warning"></i>
                    </button>
                    <button @click="$emit('toggle-delete', movie)" type="button" class="btn btn-sm">
                        <i class="bi bi-trash-fill text-danger"></i>
                    </button>
                    <button @click="$emit('toggle-like', movie)" type="button" class="btn btn-sm">
                        <i class="bi text-warning" :class="[movie.like ? 'bi-star-fill' : 'bi-star']"></i>
                    </button>
                </div>
            </div>
        </div>
    </li>
</template>
<script>
export default {
    props: {
        movie: {
            type: Object,
            required: true
        }
    }
}
</script>
<style>
.list-item__icons button {
    background-color: #F1F0E9;
}
</style>