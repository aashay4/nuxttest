<template>
  <div>
    <header-app></header-app>
    <div class="w3-main" style="margin-left:250px">
      <div class="w3-row w3-padding-64">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">Decimal to Binary</h1>
          <p>To use this decimal to binary tool, enter a decimal number up to 19 characters and click on the conversion button. For example, enter a decimal number "44" into the text box and click on the button, you will get the binary number "101100". If you want to convert a binary number into the decimal then enter zeros and ones into the box and click on specific converter button. You will get the specific decimal number for the zeros and ones.</p>
          <input type="text" v-model="text_value" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Enter a value"/><br><br>
          <button v-on:click="dectobin(); dectohex(); dectooct();" style="width: 49%">Decimal to Binary</button>
          <button v-on:click="reset()" style="width: 49%">clear all the fields</button><br><br>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll">Conversion: {{ ans }}</p>
            <h3><b>{{ text_value }} to base-8</b></h3>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll">Conversion: {{ ansoct }}</p>
            <h3><b>{{ text_value }} to base-16</b></h3>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll">Conversion: {{ anshex }}</p>
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
          <nuxt-link to="/binary-to-decimal">
          <li>Binary to Decimal</li>
        </nuxt-link>
            <nuxt-link to="/binary-to-hexadecimal">
            <li>Binary to Hexadecimal</li></nuxt-link>
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
          <h2 class="w3-text-teal">Decimal Numbers</h2>
          <p>The Decimal numbers are nothing but zero and set of other counting numbers. In the number system, all the digits are placed to the left and right of the decimal point. All the decimal points let us know where the place of a specific number is.</p>
        </div>
      </div>
      <div class="w3-row" style="text-align: justify;">
        <div class="w3-twothird w3-container">
          <h2 class="w3-text-teal">The decimal converter structure</h2>
            <p>Just for an example, if you want to convert the decimal number to binary number then follow these steps. Firstly, divide the given number by 2. After you are dividing it by 2, get the float for the next iteration. Note the reminder for the binary digit. For example, if you enter the number "4422" in the textbox and you will get this answer: 1000101000110.</p><br>
        </div>
        <div class="w3-third w3-container">
          <p class="w3-border w3-padding-large w3-padding-32 w3-center">AD</p>
          <p class="w3-border w3-padding-large w3-padding-64 w3-center">AD</p>
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
            ans: "",
    }
  },
  head () {
    return {
      title: 'Decimal to Binary Online Converter | Convert Numbers with this tool',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'With Decimal to Binary converter, get the numbers converted really easily. Get to know about the conversion process of binary to decimal and vice a versa.' }
      ]
    }
  },
  methods: {
    dectobin() {
      var x = new BigNumber(this.text_value, 10)
    var dectobin = x.toString(2);
    this.ans = dectobin;
            },
      dectohex() {
            var xzc = new BigNumber(this.text_value, 10)
            var dectohexo = xzc.toString(16).toUpperCase ();
            this.anshex = dectohexo;
                    },
                    dectooct() {
                    var xmm = new BigNumber(this.text_value, 10)
                    var dectoocto = xmm.toString(8);
                    this.ansoct = dectoocto;
                            },
   reset() {
     this.ans = '',
     this.text_value= null
   },
  }
}
</script>

<style scoped>
#box {
  background-color: lightgrey;
   width: 300px;
   border: 5px solid gray;
   padding: 10%;
   margin-left: 30%;

}
</style>
