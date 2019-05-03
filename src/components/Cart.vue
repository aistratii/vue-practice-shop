<template>
    <div>
        <ul class="list-group">
            <li class="list-group-item" v-for="item in items" :key="item.id">
                {{ item.title }} - {{item.price}}
                <button v-on:click="$emit('remove-from-cart', item)" class="btn badge badge-danger floa-tright">Remove from cart</button>
            </li>
        </ul>

        <div class="card p-3 my-5">
            <h4 class="text-center">
                $ {{ total }}
            </h4>
        </div>

        <button :disabled="items.length === 0" v-on:click="$emit('pay')" class="btn btn-info form-control">Pay now</button>
    </div>
</template>


<script>
export default {
    props: ["items"],
    computed: {
        total() {
            return this.items.reduce((acc, item) => acc + Number(item.price), 0);
        }
    }
}
</script>
