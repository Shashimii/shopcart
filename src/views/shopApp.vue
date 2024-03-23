<template>
  <div class="content">
    <div class="login-items">
      <h3>💯Not so EasyPC Graphic Cards💯</h3>
        <div class="login-itemlist">
          <itemList itemName="GTX 1050TI" :itemPrice="5000" @addCart="addToArray"/>
          <itemList itemName="GTX 1660TI" :itemPrice="15000" @addCart="addToArray"/>
          <itemList itemName="RTX 3090TI" :itemPrice="80000" @addCart="addToArray"/>
          <itemList itemName="RTX 4090TI" :itemPrice="100000" @addCart="addToArray"/>
        </div>
      </div>
    <div class="cart-list">
      <h3>🛒Shopping Cart</h3>
      <cartList :cartList="cartList" @removeCart="removeToArray" />
    </div>
  </div>
</template>

<script>
import itemList from '@/components/itemList.vue'
import cartList from '@/components/cartList.vue'

export default {
  name: 'ShopApp',
  components: {
    itemList,
    cartList
  },

  data() {
    return {
      cartList: []
    }
  },

  methods: {
    addToArray(item) {
      this.cartList.push(item);
      console.log('Cart List:', this.cartList); // Log the cartList array
    },

    removeToArray(index) {
      this.cartList.splice(index, 1);
    },
  }
}
</script>

<style>
.content {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

table {
  border-collapse: collapse;
  width: 100%;
}

th {
  background-color: #80BCBD;
}

td {
  background-color: #FFFC9B;
}

th, td {
  border: 1px solid black;
  text-align: center;
  padding: 5px;
}
</style>