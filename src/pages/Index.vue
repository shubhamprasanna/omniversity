<template>
  <q-page class="flex flex-center scroll">
    <section class="banner q-pt-xl container">
      <div class="row full-width q-pa-md q-mt-xl q-pt-xl">
        <div class="cols col-sm-12 col-md-4">
          <div class="header-tagline noto text-weight-bold">A community to support you at every step</div>
          <div class="header-subline noto q-mt-md">We bridge students, faculty & alumni to boost skill development 
            through interdisciplinary projects, team building and mentorship.</div>
          <div class="flex q-mt-md">
            <q-btn unelevated color="primary" label="Register Now" no-caps class="noto q-mr-md"/>
            <q-btn outline color="accent" label="Learn More" no-caps class="noto"/>
          </div>
        </div>
        <div class="cols col-sm-12 col-md-8">
          <q-img src="statics/banner-img.svg" />
        </div>
      </div>
    </section>
    <section class="video-description full-width">
      <div class="noto faded-title q-pa-lg" style="transform-style: preserve-3d;">OMNIVERSITY</div>
      <div class="noto text-primary text-center text-h5">How We Transform Student Lives</div>
      <div class="video-bg q-px-xl q-pb-xl">
        <div class="q-px-xl q-pb-xl">
          <div class="q-video video-container">
            <iframe width="560" height="315" src="https://www.youtube.com/embed/WTdl2742m88" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          </div>
        </div>
      </div>
    </section>
    <section class="whats-in-store full-width container q-mt-xl">
      <div class="q-mt-xl">
        <div class="text-h3 noto text-weight-bold">What's In Store For You</div>
        <div class="row q-mt-xl">
          <div class="col-4" v-for="feature in getFeatures" :key="feature.id">
            <q-card class="role-card" flat>
              <q-card-section>
                <q-icon name="people" size="md" color="primary"/>
                <div class="text-h6 text-weight-bold noto role-card-header">{{feature.header}}</div>
              </q-card-section>
              <q-card-section class="no-top-padding">
                <ul class="no-list-padding noto q-pr-md" v-for="details in feature.details" :key="details.id">
                  <li>{{details.value}}</li>
                </ul>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>
    </section>
    <section class="features full-width q-mt-xl">
      <div class="features-bg">
        <div class="noto q-pa-lg text-white features-heading">FEATURES</div>
        <div class="container">
          <div class="row q-mt-xl">
            <div class="col-sm-12 col-md-6">
              <student-row />
            </div>
            <div class="col-sm-12 col-md-6 q-pa-xl">
              <q-img src="statics/student.svg" />
            </div>
          </div>
        </div>
      </div>
      <div class="container">
        <div class="row q-mt-xl q-pt-xl">
          <div class="col-sm-12 col-md-6 q-pb-xl q-pr-xl">
            <q-img src="statics/faculty.svg" />
          </div>
          <div class="col-sm-12 col-md-6">
            <faculty-row />
          </div>
        </div>
        <div class="row q-mt-xl q-pt-xl">
          <div class="col-sm-12 col-md-6">
            <alumni-row />
          </div>
          <div class="col-sm-12 col-md-6 q-pa-xl">
            <q-img src="statics/alumni.svg" />
          </div>
        </div>
      </div>
    </section>
    <section class="testimonials q-mt-xl full-width">
      <div class="container">
      <div class="text-center q-mt-xl">
        <q-icon size="150px" name="format_quote" color="white"/>
      </div>
      <div class="text-center noto text-weight-bold text-h4">What Our Users Say About Us</div>
      <div class="q-pt-xl">
        <q-carousel
          v-model="slide"
          swipeable
          animated
          control-type="unelevated"
          control-color="primary"
          padding
          arrows
          height="300px"
          class="rounded-borders bg-transparent"
        >
        <q-carousel-slide name="1" class="column no-wrap flex-center">
          <div class="row fit justify-start items-center">
            <div class="cols col-sm-12 col-md-6 q-pa-lg">
              <q-card class="testimonial-card bg-white q-px-md">
                <q-card-section class="noto q-pt-xl">
                  Junaid and Kamaran are awesome, they were always there to answer my questions and they're professional and reliable at any time.
                </q-card-section>
                <q-separator />
                <q-card-section>
                  <q-item>
                    <q-item-section avatar>
                      <q-avatar>
                        <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                      </q-avatar>
                    </q-item-section>

                    <q-item-section>
                      <q-item-label>VJTI University</q-item-label>
                      <q-item-label caption>
                        Pune, India
                      </q-item-label>
                    </q-item-section>
                  </q-item>
                </q-card-section>
              </q-card>
            </div>
            <div class="cols col-sm-12 col-md-6 q-pa-lg">
              <q-card class="testimonial-card bg-primary text-white q-px-md">
                <q-card-section class="noto q-pt-xl">
                  Junaid and Kamaran are awesome, they were always there to answer my questions and they're professional and reliable at any time.
                </q-card-section>
                <q-separator color="white"/>
                <q-card-section>
                  <q-item>
                    <q-item-section avatar>
                      <q-avatar>
                        <img src="https://cdn.quasar.dev/img/boy-avatar.png">
                      </q-avatar>
                    </q-item-section>

                    <q-item-section>
                      <q-item-label>VJTI University</q-item-label>
                      <q-item-label caption class="text-white">
                        Pune, India
                      </q-item-label>
                    </q-item-section>
                  </q-item>
                </q-card-section>
              </q-card>
            </div>
          </div>
        </q-carousel-slide>
        </q-carousel>
      </div>
      </div>
    </section>
    <section class="contact-us full-width q-pb-xl">
      <div class="container q-pt-xl q-px-xl q-pb-xl">
        <div class="q-px-xl">
          <div class="text-h5 noto text-weight-bold q-mt-xl q-pl-md">Let's Get In Touch</div>
          <div class="q-mt-xl">
            <q-form
              @submit="onSubmit"
              class="q-gutter-md"
            >
              <q-item>
                <q-item-section>
                  <q-input
                    outlined
                    v-model="name"
                    label="Name *"
                    lazy-rules
                    :rules="[ val => val && val.length > 0 || 'Please enter your name']"
                    dense
                    color="primary"
                  />
                </q-item-section>
              </q-item>
              <q-item>
                <q-item-section class="q-pr-xs">
                  <q-input
                    type="email"
                    v-model="email"
                    label="Email Address *"
                    lazy-rules
                    :rules="[
                      val => val !== null && val !== '' || 'Please enter your email',
                    ]"
                    dense
                    outlined
                    color="primary"
                  />
                </q-item-section>
                <q-item-section class="q-pl-xs">
                  <q-input
                    v-model="phoneNumber"
                    label="Phone Number *"
                    lazy-rules
                    :rules="[
                      val => val !== null && val !== '' || 'Please enter your phone number',
                    ]"
                    dense
                    outlined
                    color="primary"
                  />
                </q-item-section>
              </q-item>
              <q-item>
                <q-item-section>
                  <q-input
                    v-model="message"
                    label="Your Message *"
                    type="textarea"
                    outlined
                    color="primary"
                  />
                </q-item-section>
              </q-item>
              <q-item>
                <q-item-section>
                  <q-item-label class="text-primary text-weight-bold text-subtitle1">You are:</q-item-label>
                  <div class="q-gutter-sm">
                    <q-radio v-model="role" val="student" label="Student" />
                    <q-radio v-model="role" val="faculty" label="Faculty" />
                    <q-radio v-model="role" val="alumni" label="Alumni" />
                  </div>
                </q-item-section>
              </q-item>
              <div class="q-ml-lg q-pl-sm">
                <q-btn label="Submit" type="submit" color="primary" outline class="q-px-sm"/>
              </div>
            </q-form>
          </div>
        </div>
      </div>
    </section>
  </q-page>
</template>

<script>
import studentRow from 'src/components/studentRow.vue'
import facultyRow from 'src/components/facultyRow.vue'
import alumniRow from 'src/components/alumniRow.vue'

export default {
  name: 'PageIndex',
  components: {
    'student-row': studentRow,
    'faculty-row': facultyRow,
    'alumni-row': alumniRow
  },
  data() {
    return {
      slide: '1',
      name: '',
      email: '',
      phoneNumber: '',
      message: '',
      role: 'student'
    }
  },
  computed: {
    getFeatures() {
      return this.$store.getters['home/getFeatures']
    },
    getStudentFeatures() {
      return this.$store.getters['home/getStudentFeatures'];
    }
  },
  methods: {
    onSubmit() {

    }
  }
}
</script>
<style lang="stylus" scoped>

.header-tagline
  font-size 32px

.header-subline
  font-size 18px

.banner
  height 70vh

.faded-title
  font-size: 6rem!important;
  text-align: center;
  font-weight: 900;
  text-transform: uppercase;
  // color: hsla(0,0%,93.3%,.925);
  z-index: -1
  background: -webkit-linear-gradient(101deg, #F2F7FF 8%, #D3F7FF 125%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

.features-heading
  font-size: 6rem!important;
  text-align: center;
  font-weight: 900;
  text-transform: uppercase;

.video-description
  min-height 500px

.video-container
  width 734px
  height 360px
  border-radius 10px
  margin 0 auto
  margin-top 3rem !important

.video-bg
  background url(../statics/Bg1.png)
  background-position bottom
  background-size cover
  background-repeat no-repeat

.role-card-header
  position relative
  padding-bottom 5px
  display table-cell

.role-card-header:before
    content: "";
    position: absolute;
    width: 65%
    height: 1px
    bottom: 0
    left: 0
    border-bottom: 4px solid #58DFFF

.no-list-padding
  padding-inline-start 20px !important

.features-bg
  background url(../statics/Bg2.png)
  background-position bottom
  background-size cover
  background-repeat no-repeat

.testimonials
  background url(../statics/Bg3.png)
  background-size cover
  background-repeat no-repeat

.contact-us
  background url(../statics/Bg4.png)
  background-size cover
  background-repeat no-repeat
  background-position bottom
</style>
