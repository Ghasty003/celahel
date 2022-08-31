<template>
  <div class="navv">
    <div class="image-s">
      <img src="./assets/celahel-logo.png" alt="logo">
      <p><i class="fa fa-bars" :class="{animate4:anim}"></i></p>
    </div>
    <nav>
      <div class="image"><img src="./assets/celahel-logo.png" alt="logo"></div>
      <div class="nav-links" :class="{animate:anim}">
        <router-link to="/" class="router">Home</router-link>
        <router-link to="/about" class="router">About</router-link>
        <router-link to="/contact" class="router">Contact</router-link>
      </div>

      <div class="nav-links2" :class="{animate2:anim}">
        <router-link to="" class="but">Sign in</router-link>
        <router-link to="" class="but">Log in</router-link>
      </div>
      <p><i class="fa fa-times" :class="{animate3:anim}"></i></p>
    </nav>
  </div>
  <router-view/>

  <footer>
    <div class="footer-div">
      <div class="first">
        <p><img src="./assets/celahel-logo.png" alt="image"></p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet cum aperiam recusandae sunt libero.</p>
      </div>

      <div class="second">
        <h2>Services</h2>
        <div>
          <p>Buy/See Pricing</p>
          <p>Case Studies</p>
          <p>Reviews</p>
          <p>Updates</p>
        </div>
      </div>

      <div class="third">
        <h2>Company</h2>
        <p>About</p>
        <p>Contact Us</p>
        <p>Careers</p>
        <p>Culture</p>
        <p>Blog</p>
      </div>

      <div class="fourth">
        <h2>Follow Us</h2>
        <p>Facebook</p>
        <p>Instagram</p>
        <p>Twitter</p>
        <p>Linkedln</p>
      </div>

      <div class="fifth">
        <h2>Get the App</h2>
        <p><img src="./assets/celahel-playstore.svg" alt="image"></p>
        <p><img src="./assets/celahel-apple.svg" alt="image"></p>
      </div>
    </div>

    <hr>

    <div class="copy"><p>Copyright © 2022 GHASTY | All Rghts reserved.</p></div>
  </footer>
</template>

<script>
export default {
  mounted () {
    window.addEventListener('load', this.winLoad)
  },
  data () {
    return {
      anim: false
    }
  },
  methods: {
    winLoad () {
      const barsContainer = document.querySelector('.image-s')
      const timesContainer = document.querySelector('nav')
      const bars = document.querySelector('.fa-bars')
      const routers = document.querySelectorAll('.router')
      if (innerWidth <= 890) {
        bars.addEventListener('click', () => {
          barsContainer.style.display = 'none'
          timesContainer.style.display = 'flex'
          this.anim = true
        })
        const times = document.querySelector('.fa-times')
        times.addEventListener('click', () => {
          barsContainer.style.display = 'flex'
          timesContainer.style.display = 'none'
        })
        routers.forEach((router) => {
          router.addEventListener('click', () => {
            timesContainer.style.display = 'none'
            barsContainer.style.display = 'flex'
          })
        })
      }
    }
  }
}

</script>
