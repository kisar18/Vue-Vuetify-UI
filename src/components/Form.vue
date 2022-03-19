<template>
  <v-container fluid class="form-container">
    <v-form
      class="form"
    >
      <v-text-field
        label="First name"
        required
      ></v-text-field>

      <v-text-field
        label="Last name"
        required
      ></v-text-field>

      <v-text-field
        label="E-mail"
        required
      ></v-text-field>

      <v-radio-group class="center-inner-elements">
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
          v-model="rating"
          :item-labels="['Sad', '', '', '', 'Happy']"
          item-label-position="top"
          color="blue"
        ></v-rating>
      </v-container>

      <v-checkbox
        label="Employed"
        class="center-inner-elements"
      ></v-checkbox>

      <v-textarea
          label="Notes"
          rows="1"
          auto-grow
      ></v-textarea>

      <v-container class="btns">
        <v-btn
          :disabled="!valid"
          color="info"
          variant="contained"
          size="large"
        >
          Submit
        </v-btn>

        <v-btn
          color="info"
          class="clear-btn"
          variant="outlined"
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
      rating: 3,
      valid: true,
      checkbox: false,
    }),

    methods: {
    },
}

</script>

<style>

.form {
  margin-top: 64px;
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

</style>