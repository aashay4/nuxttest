<template>
  <div>
    <header-app></header-app>
    <div class="w3-main" style="margin-left:250px">
      <div class="w3-row w3-padding-64">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">Binary to Octal</h1>
          <p>Want to convert Binary to Octal value? Enter the desired binary number below and click on the button to get the conversion of a binary number into the octal. Enter numbers like 16, 32 or 64 here and find out the equivalent binary values of these numbers. Same way you can enter zeros and ones to find out the octal values of those numbers.</p>
          <input type="text" v-model="text_value" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Enter a value"/><br><br>
          <button v-on:click="bintooct()" style="width: 49%">Binary to Octal</button>
          <button v-on:click="reset()" style="width: 49%">clear all the fields</button><br><br>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll">Conversion: {{ ans }}</p>
        </div><br>
        <div class="w3-third w3-container">
          <h3 style="background-color: silver;">Other Useful Tools</h3>
          <ul>
            <nuxt-link to="/ascii-to-binary">
            <li>ASCII to Binary</li>
          </nuxt-link>
          <nuxt-link to="/decimal-to-binary">
            <li>
              Decimal to Binary
            </li>
          </nuxt-link>
            <nuxt-link to="/binary-to-hexadecimal">
            <li>Binary to Hexadecimal</li></nuxt-link>
            <nuxt-link to="/decimal-to-hexadecimal">
            <li>Decimal to Hexadecimal</li></nuxt-link>
            <nuxt-link to="/decimal-to-octal">
            <li>Decimal to Octal</li></nuxt-link>
            <nuxt-link to="/octal-to-binary-converter">
            <li>Octal to Binary</li></nuxt-link>
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
          <h1 class="w3-text-teal">Binary Numbers</h1>
            <p>In the digital world, binary numbers are everywhere. The biggest advantage of these numbers is nothing the simple implementation in the electronic hardware. Travel through this table and get to know about the conversions of different numbers.</p>
            <h2 class="w3-text-teal">How to convert binary to octal?</h2>
            <p>Converting zeros and ones into the equivalent octal is not a difficult task at all. First of all, divide the given binary number in the group of three. Once you separate the binary number in the groups, convert the group of three binary digits into the octal digits. You can find the octal numbers of the binary numbers from our tool. Enter a value of the binary number, for example enter "010" in the box and you will get "2" in the answer box. With this technique you can convert binary to octal number in the least amount of time.</p>
        </div>
      </div>
      <footer-app></footer-app>
  </div>
</div>
</template>

<script>
import header from '@/components/header.vue';
import footer from '@/components/footer.vue';

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
      title: 'Binary to Octal Converter | Best Online Tool for Conversion',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Looking for a binary to octal converter? Try our online converter totally for free.' }
      ]
    }
  },
  methods: {
    bintooct() {
      this.aaa = parseInt(this.text_value);
      var bintooct = parseInt(this.aaa, 2).toString(8);
      this.ans = bintooct;
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
</style>
