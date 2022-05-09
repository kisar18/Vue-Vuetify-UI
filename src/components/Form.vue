<template>
  <v-container fluid class="form-container">
    <v-form
      class="form"
      @submit="submitForm"
    >
      <h2 class="title">Please fill out the form</h2>

      <v-label v-if="firstNameError" class="warning">First name is required</v-label>
      <v-text-field
        label="First name*"
        color="info"
        variant="outlined"
        v-model="firstName"
      ></v-text-field>

      <v-label v-if="lastNameError" class="warning">Last name is required</v-label>
      <v-text-field
        label="Last name*"
        color="info"
        variant="outlined"
        v-model="lastName"
      ></v-text-field>

      <v-label v-if="emailError" class="warning">Email is required</v-label>
      <v-text-field
        label="Email*"
        color="info"
        variant="outlined"
        v-model="email"
      ></v-text-field>

      <v-radio-group v-model="gender" class="center-inner-elements radios">
        <v-label class="title">Gender</v-label>
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
        <v-label>Favourite color</v-label>
        <select class="select" v-model="favouriteColor">
          <option value="" disabled selected>Favourite color</option>
          <option value="Red">Red</option>
          <option value="Green">Green</option>
          <option value="Blue">Blue</option>
        </select>
      </v-container>

      <v-checkbox
        label="Employed"
        class="center-inner-elements employed"
        v-model="employed"
      ></v-checkbox>

      <v-textarea
        label="Notes"
        color="info"
        bg-color="light"
        rows="1"
        auto-grow
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
    favouriteColor: "",
    employed: false,
    notes: "",
    firstNameError: false,
    lastNameError: false,
    emailError: false,
  }),

  methods: {
    submitForm() {
      if(this.firstName != "" &&
          this.lastName != "" &&
          this.email != "" &&
          /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.email)
        ) {
        this.$router.push({ 
          name: 'results',
          params: {
            firstName: this.firstName,
            lastName: this.lastName,
            email: this.email,
            gender: this.gender,
            favouriteColor: this.favouriteColor,
            employed: this.employed,
            notes: this.notes
          }
        });
      }
      else {
        if(this.firstName == "") this.firstNameError = true;
        if(this.lastName == "") this.lastNameError = true;
        if(this.email == "" ||
          /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.email) == false
        ) {
          this.emailError = true;
        }
      }
    },

    clearForm() {
      this.firstName = "";
      this.lastName = "";
      this.email = "";
      this.gender = "";
      this.favouriteColor = "";
      this.employed = false;
      this.notes = "";
    },

    emailErrors () {
        const errors = []
        if (!this.$v.email.$dirty) return errors
        !this.$v.email.email && errors.push('Must be valid e-mail')
        !this.$v.email.required && errors.push('E-mail is required')
        return errors
    },
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
  }

  .center-inner-elements {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
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

  .select {
    border: 1px solid gray;
    color: gray;
    width: 102%;
    padding: 15px;
    border-radius: 5px;
    margin-top: 15px;
  }

  .employed {
    height: 40px;
  }

  .radios {
    height: 150px;
  }

  .warning {
    color: red;
  }

  @media (max-width: 960px){
    .form-container {
      margin-bottom: 15%;
    }
    .select {
      width: 110%;
      margin-top: 5%;
    }
  }

</style>