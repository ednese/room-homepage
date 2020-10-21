<template>
  <div class="burger">
    <div class="burger__icon" v-on:click="toggle" v-bind:class="{active: burgerToggle}">
      <span/>
    </div>
    <ul class="burger__sidebar" v-bind:class="sideToggle">
      <li v-for="element in elements" :key="element.name">
        <a v-bind:href="`#${element}`">{{ element }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
import './burger.css'

export default {
  name: 'Burger',
  props: ['elements'],
  methods: {
    toggle: function () {
      this.burgerToggle = !this.burgerToggle;
      if (this.sideToggle !== 'open') {
        this.sideToggle = 'open';
      }
      else {
        this.sideToggle = 'close';
      }
      if (this.burgerToggle) {
        this.$emit('clicked', true)
      } else {
        this.$emit('clicked', false)
      }
    }
  },
  data () {
    return {
      burgerToggle: false,
      sideToggle: 'none'
    }
  }
}
</script>
