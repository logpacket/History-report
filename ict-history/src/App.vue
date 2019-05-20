<style>
	:root {
		--main: #2196F3;
	}
	.v-dialog {
		overflow-y: unset;
	}
</style>

<template>
	<div id="app">
		<v-toolbar dark color="blue-grey" style="background-color: var(--main)!important">
			<v-toolbar-title style="color: #fff; font-weight: bold;">우리나라 통신기술 발전사</v-toolbar-title>
				<v-spacer></v-spacer>
				<v-toolbar-items class="hidden-sm-and-down">
					<v-btn href="#" flat style="font-size: 1.2rem" >고대</v-btn>
					<v-btn href="#" flat style="font-size: 1.2rem" >중세</v-btn>
					<v-btn href="#" flat style="font-size: 1.2rem" >근대</v-btn>
					<v-btn href="#" flat style="font-size: 1.2rem" >현대</v-btn>
				</v-toolbar-items>
		</v-toolbar>

		<v-container align-center style="max-width: 1200px;">
			<v-timeline>
				<v-timeline-item v-for="(year, i) in years" :key="i" :color="year.color" small>
					<template v-slot:opposite>
						<span :class="`headline font-weight-bold ${year.color}--text`" v-text="year.year"></span>
					</template>

					<v-card class="elevation-10">
						<v-container>
							<h2 :class="`headline font-weight-light mb-3 ${year.color}--text`">{{year.title}}</h2>

							<div>
								<span v-text="year.text" style="font-size: 1.2rem;"></span>
								<v-dialog max-width="700px">
									<template v-slot:activator="{ on }">
										<v-btn color="green" dark v-on="on" style="display: block; margin: 1rem 0 -1rem auto;  background-color: var(--main) !important">상세내용</v-btn>
									</template>
									<v-card>
										<v-img height="300px" :src="`${ year.img }`"></v-img>
										<v-card-title>
											<span class="headline">{{year.title}}</span>
										</v-card-title>
										<v-card-text style="line-height: 1.7rem;">
                      						{{year.detail}}
											<hr style="margin: 1rem 0 1rem; color: #eee; border: 0; border-top: 1px solid #eee;">
											{{year.prosCons}}
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
		// 고대-중세 {
		years: [
		{
			color: "orange",
			title: "전서구",
			year: "BC 2000",
			text: "통신용으로 훈련된 비둘기 발목에 통신문을 매달아 귀소본능을 이용한 통신방법",
			img: "https://w.namu.la/s/54ef7a9498a47d4b81503c813e18abcd6a90bd7f3c0f44322ad1850eb83feb9ca7845c0003f4d6e3b40b634d346d0b24b1a4a07be9b5fd054a561ae83b32465dcebc8cd3ec673dd0c234f899acffea289c5160d55854bbc7d643fc36f31d35aa",
			detail: "전서구란 통신용으로 훈련된 비둘기를 의미하여 비둘기 발목에 긴급 통신문을 매달아 귀소본능을 이용한 통신방법입니다. 비둘기의 귀소본능을 이용한 원리는 비둘기의 부리와 머리 사이에 자성(磁性) 성분의 특수 세포가 있다고 합니다. 나침반과 같은 이 세포로 지구의 자장을 읽어 목적지를 찾아갈 수 있는 원리입니다. 1차 세계대전 과 2차세계대전, 6.25전쟁에서도 미국 통신부대가 전서구를 이용한 기록이 있을정도로 신뢰성이 입증되어있습니다.",
			prosCons: "운용이 어렵고 훈련이 번거로우며 새가 날 수 없는 날씨에는 사용할 수 없지만 적당히 자세한 내용을 빠르게 전달할 수 있으며 적군에게 메세지를 전달하고 있다는 사실 자체를 숨길 수 있는 장점이 있습니다."
		},
		{
			color: "orange",
			title:"횃불, 연기(봉화)",
			year: "BC 2000",
			text: "산봉우리처럼 높은 곳에 봉수대를 설치해 낮에는 연기, 밤에는 횃불로 멀리 떨어진 곳에 소식을 소식을 알리는 방법",
			img: "https://imagescdn.gettyimagesbank.com/500/201603/a10417599.jpg",
			detail: "산봉우리처럼 높은 곳에 봉수대를 설치해 낮에는 연기, 밤에는 횃불로 멀리 떨어진 곳에 긴급한 소식을 알렸습니다. 조선시대에는 전국에 600개가 넘는 봉수대 설치하였고, 대략 수십 리의 일정한 거리마다 산정(山頂)에 봉수대를 두어 지휘소까지 정보가 전달될 수 있도록 설계했습니다.평시엔 1개의 봉화를 피우고, 적이 나타나면 2개, 국경 접근 시 3개, 국경 침범 시 4개, 교전 시 5개를 피우는 규칙이 존재했습니다.우리나라는 산이 많아서 봉수는 가장 효율적인 통신수단 이었으며 남쪽의 빈번한 왜구의 침략과 서북변경 지역의 간헐적인 만주족의 침구, 신라통일 이후 1300여 년 동안 중앙집권적 통일국가의 지배가 계속되는 정치적 상황이었으므로, 봉수제도가 폐지된 조선후기까지 국방상 중요한 임무를 띤 속보(速報), 경비(警備), 전신(電信)의 중요한 역할을 담당했습니다.",
			prosCons: "봉수제는 경비가 적게 들고 신속하게 전달할 수 있는 장점이 있는 반면, 정보를 연기와 횃불에 의해 전달하기 때문에 자세한 내용을 전할 수 없었습니다."
		},
		{
			color: "cyan",
			title: "머리연",
			year: "1392",
			text: "대형 연을 이용하여 원기러 아군과 통신하는 정보 교환 방법",
			img: "https://t1.daumcdn.net/cfile/tistory/1777684B4F7AA4A90E",
			detail: "주로 해상에서 대형 연을 이용하여 원기러 아군과 통신하고 전략적 신호 로서 사용했습니다. 봉화를 설치하기 어려운 해상환경에서 정보를 전달하기 위해 사용하기 시작했으며, 400여년전인 임진왜란때 충무공 이순신장군께서 왜적을 물리치는데 통신 및 암호 수단으로 머리연을 사용하여 군용 신호로써 사용했습니다.",
			prosCons: "눈이나 비가 오면 사용할 수 없다는 단점, 가운데 방구멍이 있어 바람이 약하거나 강하게 불 때도 자유자재로 날릴 수 있으며, 날리는 사람의 손놀림에 따라 급상승과 급하강, 전진과 후퇴 등이 가능한 과학적 구조를 가지고 있습니다."
		},
		{
			color: "cyan",
			title: "파발",
			year: "1597",
			text: "이동 속도가 빠른 말을 타고 가서 소식을 전하는 파발 제도",
			img: "./DSC07111.jpg",
			detail: "조선시대 통신제도의 한 유형입니다. 군사 기밀문서를 신속히 전달하기 위해 설치한 통신제도로, 제도화된 것은 1597년(선조 30년) 정유재란때 김응남, 한준겸 등이 기능이 유명무실화된 봉수제에 대신해 중국의 파발제를 도입하고자 건의하면서 추진되었습니다. 파발은 긴급을 요하기 때문에 밤낮으로 달렸습니다. 우리나라 파발의 속도는 24시간에 약 300리 정도로 중국 파발의 500~400리보다 늦는데, 이는 산악이 많은 한반도 지형 때문이었습니다. 파발의 전송방법은 기밀문서를 봉투에 넣어 실봉하고 관인을 찍은 다음 피각대(가죽 통)에 넣어 전달했습니다.",
			prosCons: "파발제는 경비가 많이 들고 전달 속도가 느리지만 문서로 전달하기 때문에 자세한 보고를 할 수 있고 보안을 유지할 수 있는 장점이 있습니다."
		},
		// }

		// 근대 {
		{
			color: "green",
			title: "우편",
			year: "1884",
			text: "서신(書信) 및 일정한 물건을 일정한 조직에 의해 전 세계에 규칙적으로 송달하는 업무",
			img: "http://ojsfile.ohmynews.com/down/images/1/dncmcons_224321_1[308180].jpg",
			detail: "1884년 홍영식에 의해서 한성의 우정총국과 인천 우정분국 간의 우편업무를 개시하면서 시작했습니다. 개시된 신식 우편제도는 같은 해 12월 4일에 일어난 갑신정변이 실패함에 따라 20여일 만인 1884년 12월 6일에 폐지되었습니다. 그 후 10년이라는 긴 공백 기간을 거쳐 1895년에 우편업무는 다시 시작되었고, 1898년 전국에 임시 우체국을 설치하는 등 착실한 발전을 해나갔습니다. 하지만 곧 일본의 침략으로 한일합방에 앞선 1905년에 통신권을 박탈당했지만 1945년 8월 15일 광복과 함께 미군정을 거쳐 1948년 8월 15일 비로소 대한민국 체신부가 탄생하게 되었습니다.",
			prosCons: "우편이 활성화되면서 비로소 일반인들도 멀리 떨어진 지인에게 문서를 통해 소식을 전달할 수 있게 되었습니다. 하지만 당시의 우편은 전달 속도가 끔찍하게 느렸다는 단점이 있었습니다."
		},
		{
			color: "green",
			title: "전신 & 전화기",
			year: "1894",
			text: "문자나 숫자를 전기 신호로 바꾸어 전파나 전류로 보내는 통신",
			img: "https://t1.daumcdn.net/cfile/tistory/2244F83F58CF9F2C18",
			detail: "9세기 말 조선은 유교적 전통사회로부터 벗어나 새로운 근대사회로 거듭나기 위한 활발한 움직임이 있었는데요 민족의 근대화를 위한 대표적인 노력 중 하나가 바로 전기통신의 도입이었습니다. 과거 전기통신이란 크게 전신국과 전화국으로 나뉘는데요? 전신국은 전보를 접수하여 전송하기 위해 설치된 관서로 1885년 9월 28일에 한성전보총국과 인천 분국이 개국되고 평양과 의주 분국이 개국되는 증 우리나라 최초의 전신국이 설립되었습니다. 서울과 의주를 잇는 서로 전신선,서울과 부산 간의 남로 전신선, 서울과 원산의 북로 전신선이 개통되어 전국 주요 도시가 빠르게 연결되었습니다. 이로써 전신 시설은 주요 통신수단으로 정착되어 이 때를 기점으로 한국의 정보통신 속도가 크게 개선되었습니다.",
			prosCons: "통신할 대상자와 글이나 문서가 아니라 말로 소통할 수 있다는 점, 내가 정보를 전달하는 즉시 상대가 수신하는 점, 통신을 단방향이 아닌 쌍방향으로 즉시 정보교환이 가능하단 점에서 엄청난 발전을 이루었지만 당시 말소리를 전기신호로 바꾸는 기술력이 부족해 작게들리거나 통신상태가 불안정하는 등의 문제가 있었습니다."
		},
		// }

		// 현대 {
		{
			color: "pink",
			title:"통신위성, 광섬유",
			year: 1957,
			text: "통신을 주목적으로 우주에 머무르고 있는 인공위성과 빛 신호를 전달하는 가느다란 유리섬유",
			img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/Red_light_fibers.jpg/300px-Red_light_fibers.jpg",
			detail:"통신위성은 통신을 주목적으로 우주에 머무르고 있는 인공위성입니다. 현대의 통신위성은 두 지점 간에 마이크로파 무선 중계 기술을 제공하여 유선 통신을 보완하고있으며 선박, 비행기, 자동차, 휴대용 단말기 등의 이동 통신과 TV와 라디오의 방송 통신을 위해 사용되고있습니다. 광섬유는 쉽게 섬유 한쪽 끝에서 빛이 점멸하게 되면 반대쪽 끝에서 수광소자를 통해 점멸하는 빛을 받을 수 있는데 이를 이용하여 전기신호를 직접 전달하지 않고 빛을 통해 신호를 전달함으로서 빛의속도로 정보를 전달할 수 있는 섬유를 말합니다. 국가에서 국가로 정보를 주고받을 때 이 광섬유를 통해 정보가 오고가며, 이때문에 지구 반대편 사람과 정보를 교환해도 큰 대기시간 없이 소통할 수 있게 만들어줬습니다.",
			prosCons: "지금의 현대 사회를 존재할 수 있게 해준 속도, 편의성, 신뢰성 등 모든 부분이 장점이지만 굉장히 비싸고 외부 충격에 약하다는 점이 단점입니다."
		},
		{
			color: "pink",
			title: "인터넷, TV",
			year: 1960,
			text: "컴퓨터로 연결하여 통신 프로토콜을 이용해 정보를 주고받는 네트워크",
			img: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Internet_map_1024_-_transparent%2C_inverted.png/1024px-Internet_map_1024_-_transparent%2C_inverted.png",
			detail: "우리나라의 정보통신산업이 세계적인 수준으로 발전하는 매개가 되었던 것은 1995년부터 추진된 초고속정보통신망 구축 사업이라 할 수 있습니다. 1998년 7월에는 초고속인터넷 서비스가 상용화되기 시작하였고 이를 계기로 우리 사회 전반에 걸쳐 정보화가 급속히 촉진되었습니다. 2003년에는 인터넷 이용가구가 전체 가구의 60%를 상회하여 우리나라는 초고속인터넷 보급률 세계 1위를 달성하기에 이르렀습니다. 이와 함께 2003년부터는 유무선 종합 멀티미디어 서비스 제공이 가능한 IMT-2000(International Mobile Telecommunication-2000)에 대한 상용 서비스가 실시됨으로써 차세대 이동통신이 현실화되는 발전을 거두게 되었습니다. 방송 서비스의 고도화도 꾸준히 추진되었습니다. 1991년 서울방송(SBS)이 개국한 데 이어 1992년에는 서울 등 5개 도시에서 위성방송이 시작되었고 1995년부터는 지역 민영방송이 출현하여 지역 방송의 시대가 개막되었습니다. 또한 1995년에는 케이블 TV 방송이 상업방송을 개시함으로써 지상파방송에서 벗어나 다(多) 채널 시대로 진입하게 되었으며, 2001년에는 지상파방송이 디지털 시험방송을 개시하는 것을 계기로 디지털 방송 시대에 접어들었습니다. 이와 함께 2005년부터는 이동 중인 개인 단말기에서도 영상과 음성을 전송 받을 수 있는 DMB(digital multimedia broadcasting) 서비스가 시작되었습니다.",
			prosCons: "영상매체의 정보를 일반 대중들에게 전달할 수 있도록 발전하였으며, 인터넷을 통해 일반인이 다른 불특정 다수의 일반인들에게 정보를 공유할 수 있었지만, 이로 인해 검증되지 않은 정보가 퍼져나갈 수 있으며 이와같은 문제는 오늘날에도 여전히 화제가 되고있습니다."
		}
		// }
		]
	})
};
</script>