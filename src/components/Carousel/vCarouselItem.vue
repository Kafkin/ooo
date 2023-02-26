<template>

  <transition :name="dir">
    <div class="carousel__item" v-show="current === index">
      <img :src="require( `@/assets/img/${ item }` )" :alt="item" />
    </div>
  </transition>

</template>

<script>
export default {
  name: 'vCarouselItem',

  props: {
    item: {
      required: true,
      type: String
    },

    dir: {
      required: true,
      type: String
    },

    current: {
      required: true,
      type: Number
    },

    index: {
      required: true,
      type: Number
    },
  },

}
</script>