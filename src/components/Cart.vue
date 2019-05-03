<template>
    <ul class="list-group">
        <li class="list-group-item" v-for="item in items" :key="item.id">
            {{ item.title }} - {{item.price}}
            <button v-on:click="$emit('remove-from-cart', item)" class="btn badge badge-danger floa-tright">Remove from cart</button>
        </li>
    </ul>
</template>


<script>
export default {
    props: ["items"]
}
</script>
