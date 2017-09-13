<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }}</h1>
    <!-- <ul>
      <li v-for="item in items" :key="item.cart_item_id">
        <ul>
          <li>{{item.cart_item_id}}</li>
          <li>{{item.item_name}}</li>
        </ul>
      </li>
    </ul> -->
    
    <table>
      <thead>
        <tr>
          <td>cart item id</td>
          <td>item item name</td>
          <td> item quantity</td>
          <td style="width :300px;">item price</td>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.cart_item_id">
          <td>{{item.cart_item_id}}</td>
          <td>{{item.item_name}}</td>
          <td>{{item.quantity}}</td>
          <td>{{item.price}}<button style="width:80px; height:30px;" v-on:click="greet(item.cart_item_id)" >remove </button></td>
        </tr>
      </tbody>
    </table>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
    
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      items: [
        { cart_item_id: 1, item_name: "Baseball" ,quantity: 4,price: "5.50"},
        { cart_item_id: 2,item_name: "Hockey stick",quantity: 2,price: "29.99"}
      ]
    }
  },
  methods: {
    greet: function (id) {
      // `this` inside methods points to the Vue instance
      alert('Hello ' + id + '!')
      // `event` is the native DOM event

    }
  }
}
</script>

<style lang="scss">
table, th, td {
    border: 1px solid black;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
