<template>
  <header class="trello-header" role="banner" ref="root" :class="{'is-scrolled' : isViewportScrolled}">
    <div class="trello-header__container">
      <h1><app-logo/></h1>

      <ul class="trello-header__menu trello-header__menu--right">
        <router-link tag="li" to="/" class="trello-header__link">Log In</router-link>
        <router-link tag="li" to="/" class="btn btn--secondary trello-header__link">Sign Up</router-link>
      </ul>
    </div>
  </header>
</template>

<script>
import baseHeader from '_proto_/base.header.js';



export default {
  mixins: [baseHeader],
  data() {
    return {}
  },
  mounted() {}
}
</script>

<style>
.trello-header {
  width: 100%;
  position: fixed;
  height: 80px;
  top: 0;
  z-index: 2;
  padding: 1em 0.75em;
}

.trello-header__menu {
  float: right;
}

.trello-header__menu .btn {
  padding: .25em 1em .35em;
  font-size: 0.9em;
  color: #0079bf;
  margin: 0;
}

.trello-header__link {
  float: left;
}


.trello-header__container {
  height: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

.trello-header__container:after {
  content: '';
  display: block;
  clear: both;
}

.trello-header .app-logo,
.trello-header h1  {
  float: left;
  height: 100%;
  margin: 0;
}

.trello-header:before {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  transition: opacity 1s ease, box-shadow 1s ease;
  opacity: 0;
  background: #0079bf !important;
  z-index: -1;
}

.trello-header.is-scrolled:before {
  opacity: 1;
  box-shadow: 0 0 10px rgba(0,0,0,0.3);
}
</style>
