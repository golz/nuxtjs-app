<template>
  <nuxt-link :to="'/products/' + id">
    <b-card
      :img-src="imgUrl"
      :title="title"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="mb-2 product"
    >
      <b-card-text>
        {{ previewText }}
      </b-card-text>
      <b-button href="#">
        More info
      </b-button>
    </b-card>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    },
    title: {
      type: String,
      default: ''
    },
    imgUrl: {
      type: String,
      default: ''
    },
    previewText: {
      type: String,
      default: ''
    }
  }
}
</script>
