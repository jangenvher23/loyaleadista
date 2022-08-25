<template>
  <v-card light flat>
    <v-card-title class="vcard_title">
      <h2>Loyaleadsta</h2>
    </v-card-title>
    <v-card-text>
      <v-form class="login_form">
        <v-container fluid>
          <v-text-field
            label="Mobile No."
            outlined
            v-model="mobile_no"
            :rules="[rules.required]"
          ></v-text-field>
          <v-text-field
            v-model="password"
            label="Password"
            outlined
            hint="At least 8 characters"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            counter
            @click:append="show1 = !show1"
          ></v-text-field>
          <v-col>
            <v-btn depressed color="success" block elevation="10">
              Login
            </v-btn>
          </v-col>
          <v-col>
            <v-btn
              depressed
              color="success"
              block
              elevation="10"
              nuxt
              to="/signup"
            >
              Registration
            </v-btn>
          </v-col>

          <v-col>
            <v-btn depressed color="success" block text>
              Forgot password?
            </v-btn>
          </v-col>

          <v-row>
            <v-col>
              <v-btn nuxt to="/contact_us" depressed color="success" block text>
                Contact Us
              </v-btn>
            </v-col>
            <v-col>
              <v-btn
                nuxt
                to="/leadista_faqs"
                depressed
                color="success"
                block
                text
              >
                Leadista FAQ's
              </v-btn>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      show1: false,
      password: "",
      mobile_no: "",
      rules: {
        required: (value) => !!value || "Required.",
        min: (v) => v.length >= 8 || "Min 8 characters",
      },
    };
  },
};
</script>

<style>
.vcard_title {
  justify-content: center;
}
.login_form {
  padding: 3;
  margin: 10px;
}
</style>
