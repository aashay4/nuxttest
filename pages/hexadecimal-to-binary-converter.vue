<template>
  <div>
    <header-app></header-app>
    <div class="w3-main" style="margin-left:250px">
      <div class="w3-row w3-padding-64">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">Hexadecimal to Binary</h1>
          <p>Use this hexadecimal to binary converter to convert any base-16 hex number into the zeros and ones. Enter a hex number value into the box and convert that hex number into the correct binary number with ease. Hex numbers contain 0-9 in numbers and A-z in letters. Just for an example, enter "4444" into text area and click on the convert button, you will get "100010001000100" answer in the conversion box.</p>
          <input type="text" v-model="text_value" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Enter a value"/><br><br>
          <button v-on:click="hextobin()" style="width: 49%">Hexadecimal to binary</button>
          <button v-on:click="reset()" style="width: 49%">clear all the fields</button><br><br>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll">Conversion: {{ ans }}</p>
        </div><br>
        <div class="w3-third w3-container">
          <h3 style="background-color: silver;">Other Useful Tools</h3>
          <ul>
            <nuxt-link to="/">
              <li>
                Binary to Text
              </li>
            </nuxt-link>
            <nuxt-link to="/ascii-to-binary">
            <li>ASCII to Binary</li>
          </nuxt-link>
          <nuxt-link to="/decimal-to-binary">
          <li>Decimal to Binary</li>
        </nuxt-link>
        <nuxt-link to="/binary-to-decimal">
        <li>Binary to Decimal</li>
      </nuxt-link>
            <nuxt-link to="/decimal-to-hexadecimal">
            <li>Decimal to Hexadecimal</li></nuxt-link>
            <nuxt-link to="/decimal-to-octal">
            <li>Decimal to Octal</li></nuxt-link>
            <nuxt-link to="/binary-to-octal">
            <li>Binary to Octal</li></nuxt-link>
            <nuxt-link to="/hexadecimal-to-octal">
            <li>Hexadecimal to Octal</li></nuxt-link>
            <nuxt-link to="/qr-code-generator">
            <li>QR Code Generator</li></nuxt-link>
            <nuxt-link to="/qr-code-reader">
            <li>QR Code Reader</li></nuxt-link>
          </ul><br><br>
          <h3 style="background-color: silver;">Useful Resources</h3>
          <ul>
            <nuxt-link to="/about-creator">
            <li>About</li>
          </nuxt-link>
            <nuxt-link to="/blog">
            <li>Blog</li>
          </nuxt-link>
          </ul>
        </div>
      </div>
      <div class="w3-row" style="text-align: justify;">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">How to Convert Hexadecimal to Binary?</h1>
          <article>
            Converting hexadecimal to binary numbers is not that difficult task. As a matter of fact, hex numbers are used to showcase the binary numbers in the shortest way. Binary number is the base 2 while hex numbers are the bast - 16. First, get the decimal number equivalent of that hexadecimal number from the table and you are done. You will get the binary number equivalent to the hex number.
          </article><br>
        </div>
      </div>
      <footer-app></footer-app>
  </div>
</div>
</template>

<script>
import header from '@/components/header.vue';
import footer from '@/components/footer.vue';
import { BigNumber } from 'bignumber.js';

export default {

  components:{
    'header-app': header,
    'footer-app': footer
  },
  data () {
    return {
      text_value: null,
            ans: ""
    }
  },
  head () {
    return {
      title: 'Hex to binary converter | convert base 16 to zeros and ones',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Convert hexadecimal to binary numbers with this tool. Enter a hex number and get the equivalent base 2 number easily with this amazing tool.' }
      ]
    }
  },
  methods: {
    bintohex() {
      var bin = this.text_value;
      var m = new  BigNumber(bin, 2)
      var binn = m.toString(16);
      this.ans = binn;
            },
    hextobin() {
      var hex = this.text_value;
      var x = new BigNumber(hex, 16);
      var dect = x.toString(2);
      this.ans = dect;
     },
   reset() {
     this.ans = '',
     this.text_value= null
   },
  }
}
</script>

<style>
#box {
  background-color: lightgrey;
   width: 300px;
   border: 5px solid gray;
   padding: 10%;
   margin-left: 30%;
 }
table, th, td {
  border: 1px solid black;
}
</style>
