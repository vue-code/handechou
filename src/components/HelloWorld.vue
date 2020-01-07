<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex
       
      >
        <h2 class="headline font-weight-bold mb-3">Form</h2>

        <v-layout justify-center>
          <v-form>
            <v-row>
              <v-col>
                <v-text-field
                  v-model="firstnum"
                  label="First"
                ></v-text-field>
              </v-col>
              <v-col
                align-self="center">
              +
              </v-col>
              <v-col>
                
                <v-text-field
                v-model="secondnum"
                label="Second"
                ></v-text-field>
              </v-col>
              <v-col
                align-self="center">
              =
              </v-col>
              <v-col>
                <v-text-field
                v-model="resultnum"
                label="Result"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              
            </v-row>
            <v-btn
              class="mr-4"
              color="error"
              @click="reset"
            >ret</v-btn>

            <v-btn
              color="success"
              class="mr-4"
              @click="add"
            >get result</v-btn>
          </v-form>
        </v-layout>
      </v-flex>

      
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'HelloWorld',

  data: () => ({
    firstnum: '99',
    secondnum: '99',
    resultnum: 0
  }),
  methods: {
    add() {
      this.resultnum = Number(this.firstnum) + Number(this.secondnum);
    },
    reset() {
      this.firstnum = '';
      this.secondnum = '';
      this.resultnum = 0;
    }
  }
});
</script>
