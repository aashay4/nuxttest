<template>
  <div>
    <header-app></header-app>
    <div class="w3-main" style="margin-left:250px">
      <div class="w3-row w3-padding-64">
        <div class="w3-twothird w3-container">
          <h1 class="w3-text-teal">Blog</h1>
          <input type="text" v-model="search" style="width: 100%;" placeholder="Custom Search" /><br>
        <section>
          <postpreview class="single-blog borderli" v-for="post in filteredPosts"
          :key="post.id"
          :title="post.title"
          :excert="post.previewText"
          :thumbnailImage="post.thumbnailURL"
          :id="post.id" />
        </section>
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
      <footer-app></footer-app>
  </div>
</div>
</template>

<script>
import postpreview from '@/components/Blog/postpreview.vue';
import header from '@/components/header.vue';
import footer from '@/components/footer.vue';

export default {


  components:{
    'postpreview': postpreview,
    'header-app': header,
    'footer-app': footer
  },
  data () {
    return {
    posts: [
      {
      title: 'LAN(Local Area Network) - Concept, Definition, Commands',
      previewText: 'LAN is the trend over the years, get to know about local area network(lan), useful commands to be an expert network technician and important networking components.',
      thumbnailURL: 'https://66.media.tumblr.com/dc0cac693a5c8bef8382e115fc01e621/tumblr_pvp5v7as0K1ytubllo1_1280.pnj',
      id: 'lan-local-area-network'
    },
      {
      title: 'Wake-On-LAN(WOL): Everything You Need to Know',
      previewText: 'Get the detailed information about wake on lan, from how does it work to MAC address, magic packet and the node.js code to deliver magic packet for the systems',
      thumbnailURL: 'https://66.media.tumblr.com/ae8fe925a97f368be217264f6ea0886e/tumblr_pvp9tx4Gtf1ytubllo1_400.png',
      id: 'wake-on-lan'
    }
],
search: ''
}
},
  head () {
    return {
      title: 'Blog | Get the latest new and know whats hapenning in tech world',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Read our blog posts find our what is happening in the technology world. Subcribe today for the news latter.' }
      ]
    }
  },
  computed: {
    filteredPosts: function(){
      return this.posts.filter((post) => {
        return post.previewText.match(this.search);
      });
    }
  }
  }
</script>

<style scoped>

#posts {
  padding-top: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.single-blog {
  box-sizing: border-box;
  border-bottom: 1px solid silver;
  padding-top: 10px;
}

.borderli {

}

@media (min-width: 35rem) {
  #posts {
    flex-direction: row;
  }
}
</style>
