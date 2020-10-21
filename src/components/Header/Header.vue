<template>
  <div class="header">
    <div v-if="filter" class="burger__filter"/>
    <div class="header__inner">
      <img src="../../assets/logo.svg" class="header__logo" alt="logo"/>
      <ul class="header__navbar">
        <li v-for="element in elements" :key="element.name">
          <a v-bind:href="`#${element}`">{{element}}</a>
        </li>
      </ul>
    </div>
    <Burger @clicked="onClickChild" v-bind:elements="elements"/>
  </div>
</template>

<script>
import './header.css'
import Burger from './Burger/Burger'


export default {
  name: 'Header',
  components: {
    Burger
  },
  methods: {
    onClickChild (value) {
      this.$emit('clicked', value)
      this.filter = value
    }
  },
  data () {
    const tab = ['home', 'shop', 'about', 'contact'];
    return {
      elements: tab,
      filter: false
    }
  }
}
</script>