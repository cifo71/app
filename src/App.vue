<template>
  <div id="app">
    <header class="header">
      <router-link :to="{ name: 'home' }">
        <img src="@/assets/img/logo.png" />
      </router-link>
      <nav>
        <a href="#home">home</a>
        <a href="#contact">contact</a>
        <a href="#about">about</a>
      </nav>
    </header>

    <section>
      <router-view/>
    </section>
  </div>
</template>

<style lang="scss">
@import "~@/assets/scss/reset";
@import "~@/assets/scss/variables";
@import "~@/assets/scss/mixins";

.header {
  width:           100%;
  height:          80px;
  padding:         0 40px;
  display:         flex;
  align-items:     center;
  justify-content: space-between;
  position:        fixed;
  top:             0;
  left:            0;

  img {
    max-width: 100px;
  }

  nav {
    display: none;
    @include media(md) {
      display: flex;
    }

    a {
      padding:   12px;
      color:     $accent;
      font-size: 18px;
      display:   block;

      &:not(:last-of-type) {
        margin-right: 60px;
      }
      
      &:hover {
        color: $white;
      }
    }
  }
}
</style>
