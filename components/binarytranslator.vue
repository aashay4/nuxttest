<template>
  <div>
          <input type="text" v-model="text_value" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Enter a value"/><br><br>
          <button v-on:click="binarytotext(); bintodec(); bintooct(); bintohex();" style="width: 49%">Convert</button>
          <button v-on:click="reset()" style="width: 49%">clear all fields</button><br><br>
            <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll"><b>Tp binary Conversion:</b> {{ ans }}</p><br><br><br><br>
            <h3><b>({{ text_value}}) to Dec - Base-10</b></h3>
              <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll"><b>Conversion:</b> {{ btod }}</p>
              <h3><b>({{ text_value}}) to Oct - Base-8</b></h3>
                <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll"><b>Conversion:</b> {{ btoo }}</p>
                <h3><b>({{ text_value}}) to Hex - Base-16</b></h3>
                  <p class="w3-border w3-padding-large w3-padding-32 w3-right" style="width: 100%; overflow: scroll"><b>Conversion:</b> {{ btoh }}</p>
        </div>
</template>

<script>
import { BigNumber } from 'bignumber.js';

export default {

  components:{
  },
  data () {
    return {
      text_value: null,
            ans: "",
            aaa: null,
            title: 'Binary to Text Converter(Translator)',
            btod: "",
            btoo: "",
            xxx: null,
            btoh: ""
    }
  },
  head () {
    return {
      title: this.title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Conveter binary to text with this free translator. Just enter zeros and ones and convert it into the equivalent ASCII values with this binary translator.' }
      ]
    }
  },
  methods: {
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
      bintodec() {
        var cc = new BigNumber(this.text_value, 2);
         this.btod = cc;
     },
     bintooct() {
      this.xxx = parseInt(this.text_value);
      var bintooct = parseInt(this.xxx, 2).toString(8);
      this.btoo = bintooct;
            },
            bintohex() {
      var binnn = this.text_value;
      var mol = new  BigNumber(binnn, 2)
      var binnx = mol.toString(16);
      this.btoh = binnx;
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
