<template>
  <v-card
    id="app"
    :loading="loading"
    class="mx-auto my-15 rounded-xl"
    max-width="1200"
    height="600"
    style=" box-shadow: 4px 4px 8px 4px rgba(0, 0, 0, 0.2), 6px 6px 20px 6px rgba(0, 0, 0, 0.19);"
  >
    <template slot="progress">
      <v-progress-linear
        color="light-blue lighten-1"
        height="10"
        indeterminate
      />
    </template>
    <v-container fluid>
      <v-row dense>
        <v-col
          cols="7"
        >
          <img src="~/assets/login_img.jpg">
          <div style="font-size:14px" class="font-weight-bold text-center">
            Hospital Management System<br>
            <small>© Logic Research Labs 2021<br>www.logicresearchlabs.com</small>
          </div>
        </v-col>
        <v-col
          cols="5"
          elevation="12"
          class="my-auto mx-auto pa-12 rounded-xl"
        >
          <div style="font-size:24px" class="font-weight-bold mb-12">
            Login your account
          </div>
          <v-form>
            <v-spacer />
            <v-text-field
              v-model="name"
              :error-messages="nameErrors"
              :counter="10"
              label="Name"
              required
              class="mb-6"
            />
            <v-text-field
              v-model="password"
              :error-messages="passwordErrors"
              label="Password"
              required
            />
            <div class="text-right mb-12">
              <a :href="url"> forget Password ? </a>
            </div>
            <v-btn
              color="light-blue darken-3"
              text
              elevation="2"
              class="mx-2"
              large
              style="background-color:#E1F5FE "
              @click="login"
            >
              Login
            </v-btn>
            <v-btn
              color="blue-grey darken-5"
              text
              elevation="2"
              class="mx-2"
              large
              style="background-color:#ECEFF1 "
              @click="clear"
            >
              clear
            </v-btn>
          </v-form>
        </v-col>
      </v-row>
      <v-row>
        <v-chip-group
        v-model="selection"
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip>
           <v-btn
              icon
              color="pink"
            >
              <v-icon>mdi-heart</v-icon>
            </v-btn></v-chip>

        <v-chip>7:30PM</v-chip>

        <v-chip>8:00PM</v-chip>

        <v-chip>9:00PM</v-chip>
      </v-chip-group>
        </v-row>
    </v-container>
  </v-card>
</template>
<script>
export default {
  css: [
    // SCSS file in the project
    '~/assets/css/styles.scss'
  ],

  data: () => ({
    loading: false,
    selection: 1
  }),

  methods: {
    login () {
      this.loading = true

      setTimeout(() => (this.loading = false), 2000)
    }
  }
}
</script>
