<template lang="pug">
  .content
    h1
      | Hi there! We provide an amazing opportunity for you to
      | raise funds for any question and comments please feel free t contact us.
    section.email
      h2.aside-title CONTACT US
      form.email-form
        .input-box
          input.input-line(type='text' placeholder='First Name...'
          name='firstName')
          input.input-line(type='text', placeholder='Second Name...'
          name='secondName')
        .input-box
          input.input-line(type='email' placeholder='Email...'
          name='email')
          input.input-line(type='text' placeholder='Company...'
          name='company')
        .input-box
          textarea.input-line(type='text' placeholder='Text...'
          name='text')
        a.action-btn Submit
      .contact
        p.contact-address ,
        p.contact-address  Marsabit Plaza,
        p.contact-address 6th floor,
        p.contact-address Ngong Road.
        ul.social-list
          li.social-item(v-for='social in socials')
            a.social-link
              img(:src='"../../assets/icons/" + social + ".svg"')
    section.map
      h2.aside-title FIND US
      iframe(src='https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3988.7909670305535!2d36.77072771403247!3d-1.3002602990516343!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x182f1a718e626fc1%3A0x6304c210baf486c2!2sMarsaBit+Plaza!5e0!3m2!1sen!2ske!4v1505052062829' width='100%' height='450' frameborder='0' style='border:0'
      allowfullscreen)
</template>

<script>
import Firebase from '../../appconfig/firebase';

export default {
  name: 'contacts',
  firebase: {
    products: Firebase.dbProductsRef,
  },
  data() {
    return {
      socials: ['twitter', 'facebook', 'youtube', 'instagram'],
    };
  },
};
</script>

<style lang="scss" scoped>
$color-dark: #252525;
$color-grey: #666;
$color-green: #7BEFB2;
$color-pink: #D9879C;
$color-light: #fff;

h1 {
  padding: 12vh 10vw 0 10vw;
}
.aside-title {
  left: 3vw;
}
.email, .map {
  position: relative;
  padding: 6vh 10vw;
}
.map {
  background-color: $color-green;
}
.email {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.contact,
.email-form {
  display: flex;
  flex-direction: column;
}
.email-form {
  flex-basis: 60%;
  border-top: 2px solid $color-green;
}
.contact {
  flex-basis: 20%;
  text-align: right;
}
.social-list {
  width: 90%;
  align-self: flex-end;
}
.action-btn {
  margin: 1rem;
  width: 25%;
}

@media screen and (max-width: 991px) {
  .input-box {
    flex-direction: column;
  }
  .email {
    display: block;
  }
  .email, .map {
    padding: 4vh 12vw;
  }
  .contact {
    text-align: left;
  }
  .social-list {
    width: 30%;
    align-self: flex-start;
  }
}
</style>
