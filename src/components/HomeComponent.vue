<template>
  <div class="hello">
    <div v-for="item in items" class="product">
      <AddItem></AddItem>
      <h1>{{item.name}} : {{item.stock}}</h1>

      <div v-if="item.stock > 0" class="display">
        <button @click="buy(item)">Buy</button>
        <img :src="item.img" height="200" alt="">
        <div v-if="item.stock < 5">
          <h4>Low Stock!</h4>
        </div>
      </div>
      <div v-else>
        <h4>Out of Stock!</h4>
      </div>

    </div>

  </div>
</template>

<script>
  import AddItem from "@/components/AddItem"
  export default {
    name: 'HomeComponent',
    data() {
      return {
        newItem: {},
        items: [{
          name: 'Netherlands\'s T-shirt',
          img: 'https://thumbor-titelmediaug.netdna-ssl.com/nDhpKBFL6ASzlTt0hqr_XFB0nWE=/480x320/filters:strip_icc()/http%3A%2F%2Fwhatdropsnow.s3.amazonaws.com%2Fproduct_images%2Fimages%2F51035%2Fae480549ff08ba8c5baa8f3f79e59c74543f2f90.jpg',
          stock: 10
        }, {
          name: 'Netherlands\'s Hat',
          img: 'http://fanatics.frgimages.com/FFImage/thumb.aspx?i=/productImages/_3053000/ff_3053847_full.jpg&w=340',
          stock: 5
        }, {
          name: 'Netherlands\'s Scarf',
          img: 'https://s.s-bol.com/imgbase0/imagebase3/large/FC/7/0/5/3/1004004013583507.jpg',
          stock: 7
        }, {
          name: 'Netherlands\'s Jacket',
          img: 'https://cdn.shopify.com/s/files/1/0005/1747/2371/products/download_5__clipped_rev_1_1024x1024.png?v=1530742110',
          stock: 20

        }]
      }
    },
    methods: {
      buy(item) {
        item.stock--
      }
    },
    components: {
      AddItem
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
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