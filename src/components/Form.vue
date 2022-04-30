<template>
  <v-container fluid class="form-container">
    <v-form
      class="form"
      @submit="submitForm"
    >
      <h2 class="title mb-2">Please fill out the form</h2>
      <v-text-field
        label="First name*"
        color="info"
        variant="outlined"
        v-model="firstName"
        :rules="textRules"
      ></v-text-field>

      <v-text-field
        label="Last name*"
        color="info"
        variant="outlined"
        v-model="lastName"
        :rules="textRules"
      ></v-text-field>

      <v-text-field
        label="Email*"
        color="info"
        variant="outlined"
        v-model="email"
        :rules="emailRules"
        required
      ></v-text-field>

      <v-radio-group v-model="gender" class="center-inner-elements">
        <v-radio
          label="Male"
          value="male"
        ></v-radio>
        <v-radio
          label="Female"
          value="female"
        ></v-radio>
        <v-radio
          label="Other"
          value="other"
        ></v-radio>
      </v-radio-group>

      <v-container class="center-inner-elements">
        <div>Mood</div>
        <v-rating
          v-model="mood"
          :item-labels="['Sad', '', '', '', 'Happy']"
          item-label-position="top"
          color="blue"
        ></v-rating>
      </v-container>

      <v-checkbox
        label="Employed"
        class="center-inner-elements"
        v-model="employed"
      ></v-checkbox>

        <v-textarea
            label="Notes"
            color="info"
            bg-color="light"
            rows="1"
            auto-grow
            class="text-area"
            v-model="notes"
        ></v-textarea>

      <v-container class="btns">
        <v-btn
          color="info"
          variant="contained"
          size="large"
          type='submit'
        >
          Submit
        </v-btn>

        <v-btn
          color="info"
          class="clear-btn"
          variant="outlined"
          @click="clearForm"
        >
          Clear values
        </v-btn>
      </v-container>
    </v-form>

  </v-container>
</template>

<script>

export default {
  data: () => ({
    firstName: "",
    lastName: "",
    email: "",
    gender: "",
    textRules: [
      v => !!v || 'Name is required',
    ],
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+/.test(v) || 'E-mail must be valid',
    ],
    mood: 3,
    employed: false,
    notes: "",
  }),

  methods: {
    submitForm() {
      if(this.firstName != "" && this.lastName != "" && this.email != "") {
        this.$router.push({ 
          name: 'results',
          params: {
            firstName: this.firstName,
            lastName: this.lastName,
            email: this.email,
            gender: this.gender,
            mood: this.mood,
            employed: this.employed,
            notes: this.notes
          }
        });
      }
    },

    clearForm() {
      this.firstName = "";
      this.lastName = "";
      this.email = "";
      this.gender = "";
      this.mood = 3;
      this.employed = false;
      this.notes = "";
    }
  },
}

</script>

<style scoped>
  .form {
    margin-top: 64px;
    margin-bottom: 64px;
    width: 75%;
    cursor: default;
  }

  .form-container {
    display: flex;
    justify-content: center;
    cursor: default;
    height: 100%;
  }

  .center-inner-elements {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .btns {
    display: flex;
    justify-content: space-around;
  }

  .clear-btn {
    border: 1px solid #1976d2;
  }

  .title {
    text-align: center;
  }

  @media (max-width: 960px){
    .form-container {
      margin-bottom: 15%;
    }
  }

</style>