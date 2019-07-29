<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        test-lodash
      </h1>
      <h2 class="subtitle">
        My funkadelic Nuxt.js project
      </h2>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import cloneDeep from 'lodash/cloneDeep'
import merge from 'lodash/merge'
import findIndex from 'lodash/findIndex'
import isString from 'lodash/isString'
import get from 'lodash/get'
import invert from 'lodash/invert'
import isEmpty from 'lodash/isEmpty'
import isFunction from 'lodash/isFunction'
import isPlainObject from 'lodash/isPlainObject'



export default {
  components: {
    Logo
  },
  mounted () {
    // CloneDeep
    let obj = {
      a: 11,
      b: 15
    }
    let obj1 = cloneDeep(obj)
    obj1.c = 111
    console.log('Obj1 = ', obj1, 'And main Object is => ', obj)

    // Merge
    let mergeObject = {
      'a': [{ 'b': 2 }, { 'd': 4 }]
    }
    
    let mergeObject1 = {
      'a': [{ 'c': 3 }, { 'e': 5 }]
    }
    let finalMergedObject = merge(mergeObject, mergeObject1)
    console.log('finalMergedObject ===> ', finalMergedObject)

    // findIndex
    let users = [
      { 'user': 'barney',  'active': false },
      { 'user': 'fred',    'active': false },
      { 'user': 'pebbles', 'active': true }
    ]
    console.log('index ===> ', findIndex(users, function(o) { return o.user == 'barney' }))

    // isString
    console.log('isString? ===> ', isString('abc'))

    // get
    let getObject = { 'a': [{ 'b': { 'c': 3 } }] };
    console.log('Get ans ==> ', get(getObject, 'a[0].b.c'))

    // invert
    let invertObject = { 'a': 1, 'b': 2, 'c': 1 };
    console.log('Invert ===> ', invert(invertObject))

    // isEmpty
    console.log('isEmpty', isEmpty(null))
    console.log('isEmpty', isEmpty(true))
    console.log('isEmpty', isEmpty(1))
    console.log('isEmpty', isEmpty([1, 2, 3]))
    console.log('isEmpty', isEmpty({ 'a': 1 }))

    // isFunction
    console.log('isFunction???? ===> ', isFunction(isFunction))
    console.log('isFunction???? ===> ', isFunction(/abc/))

    // isPlainObject
    function Foo() {
      this.a = 1;
    }
    console.log('isPlainObject ==> ', isPlainObject(new Foo))    
    console.log('isPlainObject ==> ', isPlainObject([1, 2, 3]))    
    console.log('isPlainObject ==> ', isPlainObject({ 'x': 0, 'y': 0 }))    
    console.log('isPlainObject ==> ', isPlainObject(Object.create(null)))    
  }
}
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
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
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
