<template>
  <div class="hello" :class="{dark:dark}">
    <a @click="use(images[idx] && images[idx].src || images[idx])">
      <img :src="images[idx] && images[idx].src || images[idx]" :style="{left: left + 'px', top: top + 'px'}">
    </a>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
  },
  methods: {
    use (s) {
      localStorage.src = s
      this.$router.push('/drawing')
    },
    next () {
      this.idx += 1
      if (this.idx === this.images.length) {
        this.idx = 0
      }
    },
    move () {
      this.top += 1 * this.dir2
      this.left += 1 * this.dir
      if (this.left === window.innerWidth - 300 || this.left === 0) {
        this.dir *= -1
        this.next()
      }
      if (this.top === window.innerHeight - 200 || this.top === 0) {
        this.dir2 *= -1
        this.next()
      }
    }
  },
  mounted () {
    setInterval(this.move, 15)
  },
  data () {
    return {
      left: 0,
      top: 0,
      dir: 1,
      dir2: 1,
      idx: 0,
      images: [
        {
          id: 0,
          src: require('@/assets/paper/p0.jpeg'),
          thumbnail: require('@/assets/paper/p0.jpeg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 1,
          src: require('@/assets/paper/p1.jpg'),
          thumbnail: require('@/assets/paper/p1.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 2,
          src: require('@/assets/paper/p2.jpg'),
          thumbnail: require('@/assets/paper/p2.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 3,
          src: require('@/assets/paper/p3.jpg'),
          thumbnail: require('@/assets/paper/p3.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 4,
          src: require('@/assets/paper/p4.jpg'),
          thumbnail: require('@/assets/paper/p4.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 5,
          src: require('@/assets/paper/p5.jpg'),
          thumbnail: require('@/assets/paper/p5.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 6,
          src: require('@/assets/paper/p6.jpg'),
          thumbnail: require('@/assets/paper/p6.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 7,
          src: require('@/assets/paper/p7.jpg'),
          thumbnail: require('@/assets/paper/p7.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 8,
          src: require('@/assets/paper/p8.jpg'),
          thumbnail: require('@/assets/paper/p8.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 9,
          src: require('@/assets/paper/p9.jpg'),
          thumbnail: require('@/assets/paper/p9.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 10,
          src: require('@/assets/paper/p10.jpg'),
          thumbnail: require('@/assets/paper/p10.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 11,
          src: require('@/assets/paper/p11.jpg'),
          thumbnail: require('@/assets/paper/p11.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 12,
          src: require('@/assets/paper/p12.jpg'),
          thumbnail: require('@/assets/paper/p12.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 13,
          src: require('@/assets/paper/p13.jpg'),
          thumbnail: require('@/assets/paper/p13.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 14,
          src: require('@/assets/paper/p14.jpg'),
          thumbnail: require('@/assets/paper/p14.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 15,
          src: require('@/assets/paper/p15.jpg'),
          thumbnail: require('@/assets/paper/p15.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 16,
          src: require('@/assets/paper/p16.jpg'),
          thumbnail: require('@/assets/paper/p16.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 17,
          src: require('@/assets/paper/p17.jpg'),
          thumbnail: require('@/assets/paper/p17.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        },
        {
          id: 18,
          src: require('@/assets/paper/p18.jpg'),
          thumbnail: require('@/assets/paper/p18.jpg'),
          w: 400,
          h: 500,
          alt: 'image'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.hello {
  padding-top: 4em;
  width: 100vw;
  height: 100vh;
  position: fixed;
  z-index: -1;
  top: 0;
  left: 0;
}

.dark {
  filter: grayscale(100%);
  background-color: black;
}

h1 {
  color: #EAC257;
}
p {
  color: #9CDA68;
  margin-top: 25em;
  margin-left: 50em;
}
img {
  width: 250px;
  position: fixed;
  z-index: -9;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #229954;
}

a:visited {
  color: #229954;
}
</style>
