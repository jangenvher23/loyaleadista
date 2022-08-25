<template>
  <v-app>
    <v-card light flat>
      <v-card-title class="vcard_title">
        <h2>User Type</h2>
      </v-card-title>
      <v-card-text>
        <v-form class="signup_page">
          <v-container fluid>
            <v-col>
              <v-btn
                depressed
                color="black"
                block
                text
                nuxt
                to="/signup/farmer_registration"
              >
                <h2>Farmer</h2>
              </v-btn> </v-col
            ><v-col>
              <v-btn
                depressed
                color="black"
                block
                text
                nuxt
                to="/signup/dealer_registration"
              >
                <h2>Dealer</h2>
              </v-btn>
            </v-col>
            <v-col>
              <v-btn
                depressed
                color="black"
                block
                text
                nuxt
                to="/signup/distributor_registration"
              >
                <h2>Distributor</h2>
              </v-btn>
            </v-col>
            <v-row>
              <v-col></v-col>
              <v-col>
                <v-btn
                  depressed
                  text-align="end"
                  class="next_button"
                  color="success"
                  block
                  elevation="10"
                  nuxt
                  to="/signup"
                >
                  Next
                </v-btn>
              </v-col>
            </v-row>
          </v-container>
        </v-form>
      </v-card-text>
    </v-card>
  </v-app>
</template>

<style>
.vcard_title {
  justify-content: left;
}
.signup_page {
  padding: 3;
  margin: 20px;
}
.next_button {
  text-align: end;
  margin: 100px 10px;
}
</style>
