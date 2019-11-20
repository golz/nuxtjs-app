<template>
  <b-container>
    <b-jumbotron header="Welcome to Nuxt.js" lead="Nuxt.js will support your Vue.js with SSR <3">
      <p>Created by Goldwin</p>
      <b-button variant="primary" href="https://facebook.com/goldwin.japar">
        Visit me!
      </b-button>
    </b-jumbotron>
    <b-row>
      <b-col v-for="product in products" :key="product.id">
        <Product
          :imgUrl="product.imgUrl"
          :previewText="product.previewText"
          :id="product.id"
          :title="product.title"
        />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Product from '@/components/Product'

export default {
  components: {
    Product
  },
  asyncData () {
    return new Promise((resolve, reject) => {
      // eslint-disable-next-line nuxt/no-timing-in-fetch-data
      setTimeout(() => {
        resolve({
          products: [
            {
              id: '1',
              title: 'My Beloved Product',
              imgUrl: 'https://picsum.photos/600/300/?image=25',
              previewText: 'Lorem ipsum dolot sit amet'
            },
            {
              id: '2',
              title: 'My Beloved Product',
              imgUrl: 'https://picsum.photos/600/300/?image=25',
              previewText: 'Lorem ipsum dolot sit amet'
            },
            {
              id: '3',
              title: 'My Beloved Product',
              imgUrl: 'https://picsum.photos/600/300/?image=25',
              previewText: 'Lorem ipsum dolot sit amet'
            }
          ]
        })
      }, 1500)
    })
  }
}
</script>

<style scoped>
.products {
  display: flex;
  flex-flow: row wrap;
}

.product {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
}
</style>
