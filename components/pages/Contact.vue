<template>
  <section class="commonSection ContactPage">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h4 class="sub_title">Contact with us</h4>
          <h2 class="sec_title">write us a message</h2>
          <p class="sec_desc">
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-8 col-lg-offset-2 col-sm-12 col-md-10 col-md-offset-1">
          <form action="#" method="post" class="contactFrom" id="contactForm">
            <div class="row">
              <div class="col-lg-6 col-sm-6">
                <input
                class="input-form required"
                type="text"
                name="name"
                v-model="name"
                id="f_name"
                placeholder="Your Name">
              </div>
              <div class="col-lg-6 col-sm-6">
                <input
                class="input-form required"
                type="email"
                v-model="email"
                name="email"
                id="email"
                placeholder="Email Address">
              </div>
              <div class="col-lg-12 col-sm-12">
                <textarea
                class="input-form required"
                name="message"
                v-model="message"
                id="con_message"
                placeholder="Write Message"></textarea>
              </div>
            </div>
            <button class="common_btn red_bg" type="submit" value="Send" id="con_submit"><span>Send Message</span></button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  name: 'Contact',
  data() {
    return {
      name: '',
      email: '',
      message: ''
    }
  },
  methods: {
    sendEmail(e) {
      try {
        emailjs.sendForm('service_81plffg', 'service_81plffg', e.target,
        'hi@dzargo.id', {
          name: this.name,
          email: this.email,
          message: this.message
        })

        console.log('SUCCES!')

      } catch(error) {
          console.log({error})
      }
      // Reset form field
      this.name = ''
      this.email = ''
      this.message = ''
    },
  }
}
</script>

<style scoped>

</style>
