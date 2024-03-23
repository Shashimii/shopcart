<template>
    <div class="itemBox">
        <h4>✅{{ itemName }}</h4>
        <h4>₱{{ itemPrice }}</h4>
        <button :disabled="disable" @click="addToCart">🛒Add to Cart</button>
    </div>
</template>

<script>
    export default  {
        name: 'itemList',
        props: {
            itemName: String,
            itemPrice: Number,
            disable: Boolean
        },

        methods: {
            addToCart() {
                this.$emit('addCart', {item: this.itemName, price: this.itemPrice})
            }
        }
    }
</script>

<style>
    .itemBox {
        border: 1px solid black;
        border-radius: 5px;
        padding-inline: 10px;
        padding-block: 0px 10px;
        box-shadow: 5px 5px 5px 0px rgba(0, 0, 0, 0.3);
    }

    .itemBox:nth-child(1) {
        background-color: #A5DD9B;
    }

    .itemBox:nth-child(2) {
        background-color: #9ADE7B;
    }

    .itemBox:nth-child(3) {
        background-color: #74E291;   
    }

    .itemBox:nth-child(4) {
        background-color: #9BCF53;   
    }
</style>