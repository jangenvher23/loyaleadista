<template>
  <v-app>
    <!-- 
      <Nav />
     -->
    <v-main light>
      <v-card light flat>
        <v-card-title class="vcard_title">
          <h2>Distributor Registration</h2>
        </v-card-title>
        <v-card-text>
          <v-form class="distributor_registration_form">
            <v-container fluid>
              <v-text-field
                label="Contact #"
                type="number"
                outlined
                v-model="contact_no"
                :rules="[rules.required]"
              ></v-text-field>
              <v-text-field
                label="First Name"
                outlined
                v-model="first_name"
                :rules="[rules.required]"
              ></v-text-field>
              <v-text-field
                label="Last Name"
                outlined
                v-model="last_name"
                :rules="[rules.required]"
              ></v-text-field>
              <v-text-field
                v-model="password"
                label="password"
                outlined
                hint="At least 8 characters"
                :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                :rules="[rules.required, rules.min]"
                :type="show1 ? 'text' : 'password'"
                counter
                @click:append="show1 = !show1"
              ></v-text-field>

              <v-text-field
                v-model="confirm_password"
                label="confirm password"
                outlined
                :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
                :rules="[rules.required, rules.matching_password]"
                :type="show2 ? 'text' : 'password'"
                @click:append="show2 = !show2"
              ></v-text-field>

              <v-text-field
                label="FPA Permit"
                outlined
                v-model="fpa_permit"
                :rules="[rules.required]"
              ></v-text-field>

              <v-text-field
                label="Bank Account"
                outlined
                v-model="bank_account"
                :rules="[rules.required]"
              ></v-text-field>

              <v-text-field
                label="Business Registration"
                outlined
                v-model="business_registration"
                :rules="[rules.required]"
              ></v-text-field>

              <v-btn depressed color="success" block elevation="10">
                Register
              </v-btn>
            </v-container>
          </v-form>
        </v-card-text>
        <v-card-title class="vcard_title"> </v-card-title>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      show1: false,
      show2: false,
      contact_no: "",
      first_name: "",
      last_name: "",
      password: "",
      confirm_password: "",
      fpa_permit: "",
      bank_account: "",
      business_registration: "",
      rules: {
        required: (value) => !!value || "Required.",
        min: (v) => v.length >= 8 || "Min 8 characters",
        matching_password: (v) =>
          this.password === this.confirm_password || "Password does not match",
      },
    };
  },
};
</script>

<style>
.vcard_title {
  justify-content: center;
}
.distributor_registration_form {
  padding: 3;
  margin: 10px;
}
</style>
