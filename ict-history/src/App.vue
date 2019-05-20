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
					<v-btn href="#" flat>고대-중세</v-btn>
					<v-btn href="#" flat>근대</v-btn>
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
							<h2 :class="`headline font-weight-light mb-3 ${year.color}--text`">{{year.title}}</h2>

							<div>
								<span v-text="year.text"></span>
								<v-dialog max-width="700px">
									<template v-slot:activator="{ on }">
										<v-btn color="green" dark v-on="on">상세내용</v-btn>
									</template>
									<v-card>
										<v-img height="300px" :src="`${ year.img }`"></v-img>
										<v-card-title>
											<span class="headline">{{year.title}}</span>
										</v-card-title>
										<v-card-text>
                      						{{year.detail}}
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
        title:"횃불, 연기(봉화)",
        year: "고대~중세",
        text:
          "산봉우리처럼 높은 곳에 봉수대를 설치해 낮에는 연기, 밤에는 횃불로 멀리 떨어진 곳에 긴급한 소식을 알렸습니다.",
        img: "https://imagescdn.gettyimagesbank.com/500/201603/a10417599.jpg",
        detail:"조선시대에는 전국에 600개가 넘는 봉수대 설치하였고, 대략 수십 리의 일정한 거리마다 산정(山頂)에 봉수대를 두어 지휘소까지 정보가 전달될 수 있도록 설계했습니다.평시엔 1개의 봉화를 피우고, 적이 나타나면 2개, 국경 접근 시 3개, 국경 침범 시 4개, 교전 시 5개를 피우는 규칙이 존재했습니다.우리나라는 산이 많아서 봉수는 가장 효율적인 통신수단 이었으며 남쪽의 빈번한 왜구의 침략과 서북변경 지역의 간헐적인 만주족의 침구, 신라통일 이후 1300여 년 동안 중앙집권적 통일국가의 지배가 계속되는 정치적 상황이었으므로, 봉수제도가 폐지된 조선후기까지 국방상 중요한 임무를 띤 속보(速報), 경비(警備), 전신(電信)의 중요한 역할을 담당했습니다."
      },
      {
        color: "cyan",
        title:"파발",
        year: "고대~중세",
        text:
          "이동 속도가 빠른 말을 타고 가서 소식을 전하는 파발 제도 조선시대 통신제도의 한 유형입니다.",
        img: "http://postfiles12.naver.net/MjAxNzAxMjJfMTA4/MDAxNDg1MDkwODc5NjQw.lsFboAAAtBV61z9h_7AP-bxOXvtDFefvFnmxqXC00fQg.YdnRjweVg4id-WWgm5yIXTo7dHufLkY9oHf6RQ3IEfwg.JPEG.jaeminski/DSC07111.JPG?type=w966",
        detail:"이동 속도가 빠른 말을 타고 가서 소식을 전하는 파발 제도조선시대 통신제도의 한 유형입니다. 군사 기밀문서를 신속히 전달하기 위해 설치한 통신제도로, 제도화된 것은 1597년(선조 30년) 정유재란때 김응남, 한준겸 등이 기능이 유명무실화된 봉수제에 대신해 중국의 파발제를 도입하고자 건의하면서 추진되었습니다.파발은 긴급을 요하기 때문에 밤낮으로 달렸습니다. 우리나라 파발의 속도는 24시간에 약 300리 정도로 중국 파발의 500~400리보다 늦는데, 이는 산악이 많은 한반도 지형 때문이었습니다. 파발의 전송방법은 기밀문서를 봉투에 넣어 실봉하고 관인을 찍은 다음 피각대(가죽 통)에 넣어 전달했습니다. 파발제는 경비가 많이 들고 전달 속도가 느리지만 문서로 전달하기 때문에 자세한 보고를 할 수 있고 보안을 유지할 수 있는 장점이 있습니다."
      },
      {
        color: "pink",
        title:"temp",
        year: 1980,
        text:
          "Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae. ",
        img: "https://cdn.vuetifyjs.com/images/cards/docks.jpg",
        detail:"asdf"
      }
    ]
  })
};
</script>