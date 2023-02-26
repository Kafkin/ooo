<template>

  <div class="carousel">
    <div class="carousel__container-items">
      <slot></slot>
    </div>

    <div class="carousel__container-btn">
      <img @click="prev" class="carousel__arrow" src="@/assets/icon/arrow_left.svg" alt="arrow_left">
      <img @click="next" class="carousel__arrow" src="@/assets/icon/arrow_right.svg" alt="arrow_right">
    </div>

    <div class="carousel__container-dots" v-if="dots">
      <span
        :class="['carousel__dot', { 'carousel__dot_active': currentItem === index }]"
        v-for="( dot, index ) in items" :key="`dot-${ index }`"
      >
      </span>
    </div>
  </div>

</template>

<script>
export default {
  name: 'vCarousel',

  props: {
    items: {
      required: true,
      type: Array
    },

    currentItem: {
      required: true,
      type: Number
    },

    direction: {
      required: true,
      type: String
    },
    
    default: {
      default: () => 0,
      required: false,
      type: Number
    },

    dots: {
      default: () => false,
      required: false,
      type: Boolean
    },
  },

  data: () => ({
    disabled: false,
  }),

  methods: {

    next() {
      if( this.disabled ) return
      this.$emit( 'update:direction', 'slide-out' )

      this.currentItem < this.items.length - 1 
        ? this.$emit( 'update:currentItem', this.currentItem + 1 )
        : this.$emit( 'update:currentItem', this.default )

      this.disabledBtn()
    },

    prev() {
      if( this.disabled ) return
      this.$emit( 'update:direction', 'slide-in' )

      this.currentItem > 0
        ? this.$emit( 'update:currentItem', this.currentItem - 1 )
        : this.$emit( 'update:currentItem', this.items.length - 1  )

      this.disabledBtn()
    },

    disabledBtn() {
      this.disabled = true

      setTimeout(() => {
        this.disabled = false
      }, 700)
    }
    
  },
  
}
</script>