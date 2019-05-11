<template>
  <div id="app">
     <v-toolbar light>
       <v-toolbar-title>
        우리나라 통신기술 발전사
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat>고대</v-btn>
        <v-btn flat>중세</v-btn>
        <v-btn flat>현대</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-container align-center>
      <v-timeline>
        <v-timeline-item v-for="(year, i) in years" :key="i" :color="year.color" small>
          <template v-slot:opposite>
            <span :class="`headline font-weight-bold ${year.color}--text`" v-text="year.year"></span>
          </template>

          <div class="py-3">
            <h2 :class="`headline font-weight-light mb-3 ${year.color}--text`">Lorem ipsum</h2>
            <div>
              Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod
              convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an
              salutandi sententiae.
            </div>
          </div>
        </v-timeline-item>
      </v-timeline>
    </v-container>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data: () => ({
      years: [{
          color: "cyan",
          year: 1960
        },
        {
          color: "green",
          year: 1970
        },
        {
          color: "pink",
          year: 1980
        }
      ]
    })
  }
</script>