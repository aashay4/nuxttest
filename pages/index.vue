<template>
  <div>
    <header-app></header-app>
    <div class="w3-main" style="margin-left:250px">
      <div class="w3-row w3-padding-64">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">Binary To Text</h1>
          <p>To use the binary to text tool, enter a binary number into the box, click on the button and get the equivalent text into the output. For example, insert “01000011 01101111 01101110 01110110 01100101 01110010 01110100” into the box and click on the button, you will get the text string “Convert”.
If you want to convert text to binary, then enter any text into the text box and click on the button “Text to binary”. You will get the equivalent binary value in the converter.
</p>
          <input type="text" v-model="text_value" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Enter a value"/><br><br>
          <button v-on:click="binarytotext()" style="width: 32%">Binary to Text</button>
          <button v-on:click="texttobinary()" style="width: 32%">Text to Binary</button>
          <button v-on:click="reset()" style="width: 33%">clear all fields</button><br><br>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll"><b>Conversion:</b> {{ ans }}</p><br><br>
            <h1 class="w3-text-teal">Binary Translator</h1>
            <div>
              <p>Want to convert dec, hex or oct to the equivalent binary number? Here is the full binary translator. Please find it below. Enter any binary number in the box and click of the conversion, you will find out the conversion of that binary number into its equivalent hex, dec or octal number in just a second with our binary translator.</p>
            <binarytranslator />
          </div>
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
          <h1 class="w3-text-teal">Binary</h1>
            <p>Binary is just a number system that uses only two digits, o and 1 to rectify different queries. This number system one of the most popular systems in modern computer processing, electronics, wireless networking systems, data process over a network layer. A computer system can only understand the binary numbers and for that reason, it has become one of the most popular terms in the digital world.</p>
        </div>
      </div>

      <div class="w3-row w3-padding-64" style="text-align: justify;">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">How to convert Binary to Text?</h1>
          <p>For example, if you want to convert a binary number "01000001" into its equivalent text number. Take the first eight characters binary given to you(That's probably 01000001) and convert it into the ASCII values. Now find out the ASCII value of the specific character. And you will get the number "A" for that binary number. If you have been given number (0100000101010111). Now take the first eight characters, find the equivalent text number. After the completion, take another eight characters and find their relevant values.</p>
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
import binarytranslator from '@/components/binarytranslator.vue';
import { BigNumber } from 'bignumber.js';

export default {

  components:{
    'header-app': header,
    'footer-app': footer,
    'binarytranslator': binarytranslator
  },
  data () {
    return {
      text_value: null,
            ans: "",
            aaa: null,
    }
  },
  head () {
    return {
      title: 'Binary to Text Converter(Translator)',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Convert binary to text with this free translator. Just enter zeros and ones and convert it into the equivalent text values with this free binary translator.' },
        { hid: 'og:title', property: 'og:title', content: 'Binary to Text Converter(Translator)' }
      ]
    }
  },
  methods: {
    texttobinary() {

            for (var i=0; i < this.text_value.length; i++)
            {
              var e = this.text_value[i].charCodeAt(0);
              var s = "";
              do {
                var a = e % 2;
                e = (e - a) / 2;
        s = a + s;
      }while(e!=0);
        while(s.length<8) {
          if(s.length === 7) {
            s = " 0" + s;
            this.ans += s;
          }
          if(s.length === 6) {
          s = " 00" + s;
          this.ans += s;
          }
          if(s.length === 5) {
          s = " 000" + s;
          this.ans += s;
          }
          if(s.length === 4) {
          s = " 0000" + s;
          this.ans += s;
          }
          if(s.length === 3) {
          s = " 00000" + s;
          this.ans += s;
          }
        }
              }
            },
    binarytotext() {
        var bintext, textresult="", binlength;
        this.aaa = this.text_value;
        bintext = this.aaa.replace(/[^01]/g, "");
			binlength = bintext.length-(bintext.length%8);
			for(var z=0; z<binlength; z=z+8) {
				textresult += String.fromCharCode(parseInt(bintext.substr(z,8),2));
                                this.ans = textresult;
        }
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
