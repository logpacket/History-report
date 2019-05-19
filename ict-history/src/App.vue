<style>
	.v-dialog {
		overflow-y: unset;
	}
</style>

<template>
	<div id="app">
		<v-toolbar dark color="blue">
			<v-toolbar-title>우리나라 통신기술 발전사</v-toolbar-title>
				<v-spacer></v-spacer>
				<v-toolbar-items class="hidden-sm-and-down">
					<v-btn href="#" flat>고대</v-btn>
					<v-btn href="#" flat>중세</v-btn>
					<v-btn href="#" flat>현대</v-btn>
				</v-toolbar-items>
		</v-toolbar>

		<v-container align-center>
			<v-timeline>
				<v-timeline-item v-for="(year, i) in years" :key="i" :color="year.color" small>
					<template v-slot:opposite>
						<span :class="`headline font-weight-bold ${year.color}--text`" v-text="year.year"></span>
					</template>

					<v-card class="elevation-10">
						<v-container>
							<h2 :class="`headline font-weight-light mb-3 ${year.color}--text`">Lorem ipsum</h2>

							<div>
								<span v-text="year.text"></span>
								<v-dialog width="500px">
									<template v-slot:activator="{ on }">
										<v-btn color="green" dark v-on="on">상세내용</v-btn>
									</template>
									<v-card>
										<v-img height="300px" :src="`${ year.src }`"></v-img>
										<v-card-title>
											<span class="headline">title</span>
										</v-card-title>
										<v-card-text>
											Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo dolor, debitis aspernatur, excepturi
											quod optio eaque necessitatibus numquam nam beatae laboriosam dolore aut vel ducimus totam nulla
											molestiae blanditiis non!
										</v-card-text>
									</v-card>
								</v-dialog>
							</div>
						</v-container>
					</v-card>
				</v-timeline-item>
			</v-timeline>
		</v-container>
	</div>
</template>

<script>
export default {
  name: "app",
  data: () => ({
    years: [
      {
        color: "cyan",
        year: 1960,
        text:
          "Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae. ",
        src: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      },
      {
        color: "green",
        year: 1970,
        text:
          "Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae. ",
        src: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      },
      {
        color: "pink",
        year: 1980,
        text:
          "Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae. ",
        src: "https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      }
    ]
  })
};
</script>