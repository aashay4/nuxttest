<template>
  <div>
    <header-app></header-app>
    <div class="w3-main" style="margin-left:250px">
      <div class="w3-row w3-padding-64">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">About Creator</h1>
          <div class="container-fluid bg-1 text-center">
<p style="text-align: justify;">Aashay Trivedi is the creator of BinarytoText and CEO of Lantech Infocom. Because of his enthusiasm towards learning new technologies, he has worked on
modern technologies like Vue.js, D3.js, Socket.IO, and Node.js. Being the CEO, Aashay takes care of business development activities and explores new technologies to get the
best possible results for the clients.</p><br>
<i class="fa fa-envelope" style="width:30px"> </i> <b><a href="mailto:aashay@lantechinfocom.com">aashay@lantechinfocom.com</a></b><br>
<i class="fa fa-skype" style="width:30px"> </i> <b><a href="skypeto:live:aashay.trivedi1">live:aashay.trivedi1</a></b><br>
</div>
        </div>
        <div class="w3-third w3-container">

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
    }
  },
  head () {
    return {
  title: 'About Creator - Get to know about Aashay Trivedi',
  meta: [
    // hid is used as unique identifier. Do not use `vmid` for it as it will not work
    { hid: 'description', name: 'description', content: 'Aashay Trivedi is the creator of this tool.' }
  ]
}
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
