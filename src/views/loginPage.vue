<template>
    <div class="login-content">
        <div class="login-items">
            <h3>💯Not so EasyPC Graphic Cards💯</h3>
            <div class="login-itemlist">
                <itemList itemName="GTX 1050TI" :itemPrice="5000" :disable="btndisabled" />
                <itemList itemName="GTX 1660TI" :itemPrice="15000" :disable="btndisabled" />
                <itemList itemName="RTX 3090TI" :itemPrice="80000" :disable="btndisabled" />
                <itemList itemName="RTX 4090TI" :itemPrice="100000" :disable="btndisabled" />
            </div>
        </div>
    
        <div class="login-form">
            <div class="login-input">
                <h3>Login</h3>
                <h5>Enter Username <br> {{ error }}</h5>
                <input type="text" v-model="username">
                <h5>Enter Password</h5>
                <input type="password" v-model="password">
                <button @click="login()">Login</button>
                <p>username: User</p><p>password: 12345</p>
            </div>
        </div>
    </div>
</template>

<script>
import itemList from '@/components/itemList.vue'

export default {
    name: 'loginPage',
    components: {
        itemList,
    },
    
    data() {
        return {
            username: '',
            password: '',
            error: '',
            btndisabled: true
        }
    },

    methods: {
        login() {
            if (this.username !== 'User' || this.password !== '12345') {
                this.error = 'Wrong Username or Password';
            } else {
                localStorage.setItem('authToken', 'true'); // Set the 'logged' item in localStorage to 'true'
                this.$router.push('/shop')
            }
        }
    }
};

</script>

<style>

.login-content {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
    }

.login-form {
    display: flex;
    align-items: center;
    justify-content: center;
}

.login-input {
    border: 1px solid black;
    border-radius: 5px;
    padding-inline: 20px;
    padding-block: 0px 20px;
    background-color: #BBE2EC;
}

.login-items {
    border: 1px solid black;
    border-radius: 5px;
    padding-inline: 20px;
    padding-block: 0px 20px;
    height: 80vh;
    background-color: #EFF396;
}

.login-itemlist {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}
</style>