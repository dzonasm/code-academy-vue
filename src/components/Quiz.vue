<template>
	<h2 v-if="quizCount > quiz.lenght">Your final score is:</h2>
	<h3>{{ points }}</h3>
	<button v-if="quizCount > quiz.length" @click="restart">Retry</button>
	<div v-for="(item, idx) in quiz" :key="item.question">
		<div v-if="idx === quizCount">
			<p>
				{{ item.question }}
			</p>
			<button v-for="(answer, index) in item.answers" :key="index">
				<strong>{{ index }}.</strong>{{ answer }}
			</button>
			<input v-model="answer" />
			<button @click="guess(answer, item.correct)">Guess!</button>
		</div>
	</div>
</template>
<script>
export default {
	name: "Quiz",
	methods: {
		checkAnswer(item, answerIdx) {
			this.quizCount++;
			if (answerIdx === item.correct) {
				this.points++;
			}
		},
		guess(answer, correct) {
			if (answer == correct) {
				this.points++;
				this.quizCount++;
				this.answer = "";
			}
		},
		restart() {
			this.points = 0;
			this.quizCount = 0;
		},
	},
	data() {
		return {
			quiz: [
				{
					question: "Kuriais metais krikštatėvis buvo išleistas pirmą kartą?",
					answers: ["1993", "1852", "1662", "1972"],
					correct: 3,
				},
				{
					question:
						"Kuris aktorius pelnė geriausią aktoriaus Oskarą už filmus „Filadelfija“ (1993) ir „Forrest Gump“ (1994)?",
					answers: ["Jonas Bulijonas", "Tomas Kukuruzas", "Tom Hanks", "Mikas plikas"],
					correct: 2,
				},
				{
					question:
						"Kiek savarankiškų komizionų padarė Alfredas Hitchcockas savo filmuose 1927–1976 metais - 33, 35 ar 37?",
					answers: ["12", "37", "100", "2"],
					correct: 1,
				},
				{
					question:
						"Kuris 1982 m. Filmas buvo labai gerbėjų sutiktas dėl meilės tarp jauno, tėvo neturinčio priemiesčio berniuko ir pasiklydusio, geranoriško bei namuose gyvenančio svečio iš kitos planetos vaizdavimo?",
					answers: ["IR Nežemiškas", "Gelbėtojai", "Terminatorius", "Titanikas"],
					correct: 0,
				},
				{
					question: "Kuri aktorė vaidino Mary Poppins 1964 m. Filme „Mary Poppins“?",
					answers: ["Andželina joly", " Julie Andrews", "Karen Gillan", "Lucy Liu"],
					correct: 1,
				},
			],
			points: 0,
			quizCount: 0,
		};
	},
};
</script>
<style></style>
