<template>
  <div>
    <v-form>
      <v-container>
        <h3>SEND US A MESSAGE</h3>
        <v-row>
          <v-col cols="6">
            <input
            class="col"
              type="text"
              color="white"
              placeholder="Name"
              outlined
              v-model="firstname"
              :rules="nameRules"
              label="Name"
              required
            />
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="3">
            <input
            class="col"
              outlined
              v-model="firstname"
              :rules="nameRules"
              placeholder="Email"
              required
            />
          </v-col>
          <v-col cols="3">
            <input
            class="col"
              outlined
              v-model="firstname"
              :rules="nameRules"
              placeholder="Subject"
              required
            >
            
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="6">
            <textarea class="col" type="message" outlined placeholder="Message"/>
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="6">
            <v-btn block class="btn_submit">Submit</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-form>
  </div>
</template>
<style scoped lang="scss">
.btn_submit {
  background: #f9a828 !important;
  font-size: 1.5rem;
  display: block;
  letter-spacing: 0.2rem;
  height: 6rem;
  line-height: 6rem;
  padding: 0 3rem;
  width: 100%;
  background: #f9a828;
  color: #000000;
  margin-top: 0.6rem;
}
v-form h3 {
  font-size: 1.4rem;
  line-height: 1.7;
  text-transform: uppercase;
  letter-spacing: 0.2rem;
}

v-text-field {
  border: white !important;
  color: white !important;
}
v-form input,
textarea {
  background: white !important;
}
input,
v-textarea {
  background: white !important;
}
</style>
