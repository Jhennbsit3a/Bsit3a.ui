<template>
  <div>
    <div class="d-flex align-center justify-center" style="height: 100vh">
      <v-card width="400">
        <div align="center">
          <v-img
           src="https://png.pngtree.com/template/20210320/ourmid/pngtree-real-estate-building-logo-image_501124.jpg"
          width="200"
          class="mt-4"
          >
          </v-img>
        </div>
        <div class="mx-6">
          <v-card-text>
            <v-row>
              <v-col cols="6" md="6">
                <v-btn block outlined>
                  <v-icon color="red"> mdi-google </v-icon>
                  google
                </v-btn>
              </v-col>

              <v-col cols="6" md="6">
                <v-btn block outlined>
                  <v-icon color="primary"> mdi-facebook </v-icon>
                  facebbok
                </v-btn>
              </v-col>
            </v-row>
          </v-card-text>

          <v-card-text>
            <v-form ref="form" lazy-validation v-model="valid">
              <v-text-field
                outlined
                label="Email"
                prepend-inner-icon="mdi-email"
                :rules="emailRules"
              >
              </v-text-field>

              <v-text-field
                outlined
                label="Password"
                prepend-inner-icon="mdi-lock"
                :rules="passwordRules"
                type="password"
              >
              </v-text-field>
              <v-btn block color="primary" @click="signin"> Login</v-btn>
            </v-form>
          </v-card-text>
        </div>
      </v-card>
    </div>
  </div>
</template>

<script>
export default {
  layout:"auth",
  data: () => ({
    valid: true,
    name: "",
    passwordRules: [(v) => !!v || "Password is required"],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    select: null,
    items: ["Item 1", "Item 2", "Item 3", "Item 4"],
    checkbox: false,
  }),

  methods: {
    signin() {
      if (this.$refs.form.validate){
        console.log("successfully Login");
        this.$router.push("/Dashboard");
      }
    }
    }
      }
    
</script>
