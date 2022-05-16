<template>
  <div>
    <v-sheet color="pink  py-10">
      <v-container>
        <v-card color="transparent" tile flat>
          <v-card-title class="justify-center display-1 white--text"
            >CONTACT ME</v-card-title
          >
        </v-card>
      </v-container>
    </v-sheet>
    <v-sheet color="blue lighten-2" height="100%" class="py-10">
      <v-container fill-height>
        <v-card class="mx-auto pt-10" width="250" height="200">
          <v-card-title class="subtitle-2 justify-center">
            You can reach me via email at:
          </v-card-title>
          <v-card-text class="subtitle-1 text-center">
            <v-row align="center" class="mx-0">
              ayenimichael1998@gmail.com dapope140@gmail.com
            </v-row>
          </v-card-text>
        </v-card>
      </v-container>
      <!-- <v-container>
        <v-row>
          <v-col cols="12" sm="12" md="6" lg="6">
            <v-card class="pa-3">
              <v-container
                ><v-form
                  v-model="valid"
                  lazy-validation
                  @submit.prevent="submit"
                >
                  <v-text-field
                    v-model="form.fullname"
                    :rules="nameRules"
                    label="Name"
                    :counter="30"
                    outlined
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="form.email"
                    outlined
                    :rules="emailRules"
                    label="E-mail"
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="form.phone_no"
                    :rules="phoneRules"
                    outlined
                    :counter="11"
                    label="Phone Number"
                    required
                  >
                  </v-text-field>

                  <v-text-field
                    v-model="form.subject"
                    :rules="subjectRules"
                    outlined
                    label="Subject"
                    required
                  >
                  </v-text-field>

                  <v-textarea
                    background-color="grey lighten-2"
                    color="pink"
                    v-model="form.message"
                    :rules="messageRules"
                    label="message"
                    outlined
                    required
                  ></v-textarea>

                  <v-btn
                    color="pink"
                    :disabled="!valid"
                    class="mr-4 white--text"
                    :loading="loading"
                  >
                    Submit
                  </v-btn>
                </v-form></v-container
              >
            </v-card>
          </v-col>
          <v-col> </v-col>
        </v-row>
      </v-container> -->
    </v-sheet>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: this.initializeForm(),
      valid: true,
      nameRules: [
        (v) => !!v || "Name is required",
        (v) => (v && v.length <= 30) || "Name must be less than 30 characters",
      ],
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      phoneRules: [
        (v) => !!v || "Phone number is required",
        (v) => (v && v.length <= 11) || "Name must be less than 30 characters",
      ],
      subjectRules: [(v) => !!v || "Subject is required"],
      messageRules: [(v) => !!v || "Message is required"],
    };
  },
  methods: {
    initializeForm: () => ({
      id: "",
      fullname: "",
      email: "",
      phone_no: "",
      subject: "",
      message: "",
    }),
  },
};
</script>

<style lang="scss" scoped></style>
