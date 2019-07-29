<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">test-lodash</h1>
      <h2 class="subtitle">My funkadelic Nuxt.js project</h2>
      <div class="links">
        <a href="https://nuxtjs.org/" target="_blank" class="button--green">Documentation</a>
        <a href="https://github.com/nuxt/nuxt.js" target="_blank" class="button--grey">GitHub</a>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import _ from 'lodash'
// import assignIn from "lodash/assignIn";
// import omit from "lodash/omit";
// import some from "lodash/some";

export default {
  components: {
    Logo
  },
  mounted() {
    // // AssignIn
    // function Foo() {
    //   this.a = 1;
    // }
    // function Bar() {
    //   this.c = 3;
    // }
    // Foo.prototype.b = 2;
    // Bar.prototype.d = 4;
    // console.log("AssignIn ==> ", assignIn({ a: 0 }, new Foo(), new Bar()));

    // // Omit
    // let object = { a: 1, b: "2", c: 3 };
    // console.log("Omit ===> ", omit(object, ["a", "c"]));

    // // Some
    // console.log('Some ===> ', some([null, 0, "yes", false], Boolean))
    // let users = [
    //   { user: "barney", active: true },
    //   { user: "fred", active: false }
    // ]
    // console.log('Some of users, { user: "barney", active: false } ==> ', users, { user: "barney", active: false })
    // console.log('Some of some(users, ["active", false]) ==> ', some(users, ["active", false]))
    // console.log('Some of some(users, "active") ==>',some(users, "active"))

    // AssignIn
    function Foo() {
      this.a = 1;
    }
    function Bar() {
      this.c = 3;
    }
    Foo.prototype.b = 2;
    Bar.prototype.d = 4;
    console.log("AssignIn ==> ", _.assignIn({ a: 0 }, new Foo(), new Bar()));

    // Omit
    let object = { a: 1, b: "2", c: 3 };
    console.log("Omit ===> ", _.omit(object, ["a", "c"]));

    // Some
    console.log('Some ===> ', _.some([null, 0, "yes", false], Boolean))
    let users = [
      { user: "barney", active: true },
      { user: "fred", active: false }
    ]
    console.log('Some of users, { user: "barney", active: false } ==> ', _.some(users, { user: "barney", active: false }))
    console.log('Some of some(users, ["active", false]) ==> ', _.some(users, ["active", false]))
    console.log('Some of some(users, "active") ==>',_.some(users, "active"))

  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
