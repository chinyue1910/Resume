<template lang="pug">
#app
  b-navbar(toggleable="sm")
    b-navbar-toggle.ml-auto(target="nav-collapse")
      template(v-slot:default="{ expanded }")
        font-awesome-icon(
          v-if="expanded",
          :icon="['fas', 'times']",
          color="white"
        )
        font-awesome-icon(v-else, :icon="['fas', 'list-ul']", color="white")
    b-collapse#nav-collapse.justify-content-center(is-nav)
      b-navbar-nav
        b-nav-item(href="#section02") About
        b-nav-item(href="#section03") Skills
        b-nav-item(href="#section04") Resume
        b-nav-item(href="#section05") Portfolio
  router-view
  transition(
    name="custom-classes-transition",
    enter-active-class="animate__animated animate__bounce animate__slow"
    leave-active-class="animate__animated animate__fadeOut"
  )
    .btn(v-if="scrollposition > 1000" @click="scrollTop")
      font-awesome-icon(:icon="['fas', 'chevron-up']", color="white")
</template>

<script>
export default {
  data () {
    return {
      scrollposition: ''
    }
  },
  mounted () {
    if (this.$route.path !== '/') {
      this.$router.push('/')
    }
    window.addEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      this.scrollposition =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop
    },
    scrollTop () {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  }
}
</script>

<style lang="scss" scoped>
@mixin sm {
  @media (min-width: 576px) {
    @content;
  }
}
* {
  margin: 0;
  padding: 0;
  list-style: none;
  box-sizing: border-box;
  transition: 0.5s;
  font-family: "微軟正黑體";
}
.navbar {
  background-color: black;
  @include sm {
    position: absolute;
    top: 0;
    z-index: 999;
    width: 100%;
    background-color: transparent;
  }
  button {
    svg {
      width: 30px;
      height: 30px;
    }
    outline: none;
  }
}
.navbar-toggler {
  margin: 9px 9px 9px auto;
}
li {
  margin: 0 1rem;
  a {
    font-size: 1rem;
    padding: 10px;
    text-align: center;
    color: white !important;
  }
}
.btn {
  position: fixed;
  bottom: 10px;
  right: 10px;
  font-size: 2rem;
  background-color: gold;
  border-radius: 50%;
  padding: 0;
  width: 40px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}
</style>
