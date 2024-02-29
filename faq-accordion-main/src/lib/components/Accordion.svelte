<script lang="ts">
	let activeIndex: number | null = null;

	interface FAQ {
		question: string;
		answer: string;
	}

	let questions: FAQ[] = [
		{
			question: 'What is Frontend Mentor, and how will it help me?',
			answer:
				"Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for all levels and ideal for portfolio building."
		},
		{
			question: 'Is Frontend Mentor free? ',
			answer:
				'Yes, Frontend Mentor offers both free and premium coding challenges, with the free option providing access to a range of projects suitable for all skill levels.'
		},
		{
			question: 'Can I use Frontend Mentor projects in my portfolio?',
			answer:
				"Yes, you can use projects completed on Frontend Mentor in your portfolio. It's an excellent way to showcase your skills to potential employers!"
		},
		{
			question: "How can I get help if I'm stuck on a Frontend Mentor challenge?",
			answer:
				"The best place to get help is inside Frontend Mentor's Discord community. There's a help channel where you can ask questions and seek support from other community members."
		}
	];

	function toggleAccordion(index: number) {
		activeIndex = activeIndex === index ? null : index;
	}
</script>

<div class="accordion">
	<div class="faqs">
		<img src="/assets/images/icon-star.svg" alt="star" />
		<h1>FAQs</h1>
	</div>
	{#each questions as { question, answer }, index}
		<div class="container">
			<button class="questions" on:click={() => toggleAccordion(index)}>
				<p class="question">
					{question}
				</p>
			</button>
			<button
				class="question-btn"
				on:click={() => toggleAccordion(index)}
				class:selected={activeIndex === index}
			>
				{#if activeIndex === index}
					<img src="/assets/images/icon-minus.svg" class="btn-img" alt="Collapse" />
				{:else}
					<img src="/assets/images/icon-plus.svg" class="btn-img" alt="Expand" />
				{/if}
			</button>
		</div>
		<div class="answer" class:visible={activeIndex === index}>
			{answer}
		</div>
	{/each}
</div>

<style>
	.accordion {
		margin-bottom: 20px;
		display: flex;
		flex-direction: column;
		background-color: #ffffff;
		width: 327px;
		z-index: 1000;
		padding: 24px;
		border-radius: 8px;
	}

	.faqs {
		display: flex;
		padding: 24px 0;
		align-items: center;
	}

	.faqs h1 {
		font-size: 32px;
		padding-left: 32px;
	}

	.faqs img {
		height: 32px;
	}

	.container {
		display: flex;
		align-items: center;
		border-bottom: 1px solid hsl(275, 100%, 97%);
		padding-bottom: 20px;
	}

	.questions {
		display: flex;
		align-items: center;
		border: none;
		background-color: transparent;
		text-align: left;
	}

	.questions:last-child {
		border-bottom: none;
	}

	.question {
		color: hsl(292, 42%, 14%);
		font-weight: 600;
		font-size: 16px;
		border: 1px solid red;
	}

	.question:hover {
		cursor: pointer;
		color: #ad28eb;
	}

	.question-btn {
		cursor: pointer;
		padding: 10px;
		background-color: transparent;
		border: 1px solid;
	}

	.answer {
		display: none;
		padding: 24px 0 20px 0;
		color: hsl(292, 16%, 49%);
		font-size: 16px;
	}

	.answer.visible {
		display: block;
	}
</style>
