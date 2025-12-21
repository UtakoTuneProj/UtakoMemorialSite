<script lang="ts">
	const sections = [
		{
			id: 'hero',
			title: 'UTAKO TUNE memorial',
			overline: '静かな終幕',
			body: '9年間続いた個人プロジェクト UTAKO TUNE は、ここで静かに幕を閉じます。これは終わりの宣言であり、歩んだ姿勢を残すための短い記録です。'
		},
		{
			id: 'reflection',
			title: 'Quiet Reflection',
			body: '初期の小さな実験から始まり、技術と生活が変わっても「歌に手ざわりを与える」ことを軸に続けた。これは成果の棚卸しではなく、当時の呼吸を思い出すための回想。'
		},
		{
			id: 'heart',
			title: 'The Heart of UTAKO TUNE',
			items: [
				'プロダクトより人格を先に置く',
				'量より感度、速さより誠実さ',
				'匿名性と個性のバランスを保つ',
				'聴く人の余白を奪わない',
				'技術は媒介、意図は静かに'
			]
		},
		{
			id: 'gratitude',
			title: 'Quiet Gratitude',
			body: '音を拾ってくれた人、ボカロ文化に関わるすべての人、時代に合わせて道具を生み続けてくれた技術者たち、そして過去の自分へ。静かに受け取ってくれてありがとう。'
		},
		{
			id: 'turning-point',
			title: 'Turning Point',
			body: '暮らしのリズム、技術基盤、創作の時間配分が大きく変わった。維持のための更新より、意図の鮮度を優先して「区切る」ことを選んだ。'
		},
		{
			id: 'exhibits',
			title: 'Exhibits',
			body: '残すのは断片だけ。折原詩子という人格のフォルム、初期のロゴ、UI の試作、歌の地図。ここでは画像を置かない。思い出す人の中にだけ展示される。',
			aside: '素材は別途保管。必要なら未来の自分が取りに行けばいい。'
		},
		{
			id: 'note',
			title: 'Note to Myself',
			body: '「やめることを決める勇気」を褒めてほしい。ここから別の場所へ行くとしても、静けさを保ったまま手を動かし続けること。'
		},
		{
			id: 'epilogue',
			title: 'Epilogue',
			body: '2025 — UTAKO TUNE は静かに閉じた。これで終わり。ここからまた始める。'
		}
	];

	const revealOnce = (node: HTMLElement) => {
		const show = () => node.classList.remove('hidden');

		if (typeof IntersectionObserver === 'undefined') {
			show();
			return { destroy: () => undefined };
		}

		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						show();
						observer.unobserve(entry.target);
					}
				});
			},
			{ threshold: 0.15 }
		);

		observer.observe(node);

		return {
			destroy() {
				observer.disconnect();
			}
		};
	};
</script>

<svelte:head>
	<title>UTAKO TUNE Memorial</title>
	<meta
		name="description"
		content="UTAKO TUNE を静かに終えるための 1 ページの記録。理念と感謝、区切りの理由を静かなトーンで残します。"
	/>
</svelte:head>

<main class="page">
	<section class="hero" id="hero">
		<div class="hero-inner">
			<p class="overline">{sections[0].overline}</p>
			<h1>{sections[0].title}</h1>
			<p class="lead">{sections[0].body}</p>
			<div class="scroll-cue">
				<span>scroll</span>
				<div class="line"></div>
			</div>
		</div>
	</section>

	<section class="content">
		{#each sections.slice(1) as section}
			<article class="card hidden" id={section.id} use:revealOnce>
				<p class="section-label">{section.id}</p>
				<div class="card-body">
					<h2>{section.title}</h2>
					{#if section.items}
						<ul class="values">
							{#each section.items as item}
								<li>{item}</li>
							{/each}
						</ul>
					{:else}
						<p>{section.body}</p>
					{/if}
					{#if section.aside}
						<p class="aside">{section.aside}</p>
					{/if}
				</div>
			</article>
		{/each}
	</section>
</main>

<style>
	:global(body) {
		margin: 0;
		background: radial-gradient(160% 160% at 80% 20%, #f1eaff, #f8f6fb 45%, #fefefe);
		color: #1f1a2c;
		font-family: 'Manrope', 'Noto Sans JP', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
		letter-spacing: 0.01em;
	}

	:global(*) {
		box-sizing: border-box;
	}

	main.page {
		min-height: 100vh;
	}

	.hero {
		position: relative;
		min-height: 100vh;
		display: grid;
		place-items: center;
		padding: 4rem 1.5rem 2rem;
	}

	.hero-inner {
		max-width: 880px;
		background: rgba(255, 255, 255, 0.72);
		border: 1px solid #efe8ff;
		box-shadow: 0 25px 70px rgba(69, 37, 116, 0.12);
		border-radius: 24px;
		padding: 2.75rem 2.5rem;
		backdrop-filter: blur(6px);
		text-align: left;
	}

	.overline {
		text-transform: uppercase;
		font-size: 0.85rem;
		letter-spacing: 0.08em;
		color: #7c6fa3;
		margin: 0 0 0.75rem;
		font-weight: 700;
	}

	h1 {
		font-size: clamp(2.4rem, 4vw + 1rem, 3.4rem);
		margin: 0 0 1rem;
		line-height: 1.1;
		font-family: 'Noto Serif JP', 'Times New Roman', serif;
		color: #1b0f2e;
	}

	.lead {
		font-size: 1.05rem;
		line-height: 1.7;
		color: #3c3556;
		margin: 0 0 1.5rem;
	}

	.scroll-cue {
		display: inline-flex;
		align-items: center;
		gap: 0.6rem;
		color: #7c6fa3;
		font-size: 0.9rem;
	}

	.scroll-cue .line {
		width: 44px;
		height: 1px;
		background: linear-gradient(90deg, #b9a6ff 0%, #7c6fa3 100%);
	}

	.content {
		max-width: 980px;
		margin: 0 auto;
		padding: 0 1.25rem 2rem;
		display: flex;
		flex-direction: column;
		gap: 1.25rem;
	}

	.card {
		position: relative;
		background: rgba(255, 255, 255, 0.9);
		border: 1px solid #efe8ff;
		border-radius: 20px;
		padding: 1.4rem 1.35rem 1.5rem;
		box-shadow: 0 15px 45px rgba(69, 37, 116, 0.08);
		opacity: 1;
		transform: translateY(26px);
		transition: opacity 700ms ease, transform 700ms ease;
		min-height: 100vh;
		display: flex;
		align-items: center;
	}

	.card.hidden {
		opacity: 0;
		transform: translateY(26px);
	}

	.card:hover {
		translate: 0 -2px;
	}

	.section-label {
		position: absolute;
		top: 1.05rem;
		right: 1.2rem;
		font-size: 0.75rem;
		color: #9b8dc4;
		text-transform: uppercase;
		letter-spacing: 0.08em;
		margin: 0;
	}

	.card-body {
		width: 100%;
	}

	.card-body h2 {
		margin: 0 0 0.55rem;
		font-size: 1.35rem;
		font-weight: 700;
		color: #2a1d44;
	}

	.card-body p {
		margin: 0.1rem 0 0;
		line-height: 1.7;
		color: #372f4f;
		font-size: 1rem;
	}

	.values {
		list-style: none;
		padding: 0;
		margin: 0.6rem 0 0;
		display: grid;
		gap: 0.35rem;
	}

	.values li {
		padding: 0.65rem 0.85rem;
		border: 1px dashed #d7ccf3;
		border-radius: 12px;
		background: #fbf9ff;
		color: #342a4f;
	}

	.aside {
		margin-top: 0.75rem;
		font-size: 0.95rem;
		color: #6a5f87;
		font-style: italic;
	}

	@media (prefers-reduced-motion: reduce) {
		.card {
			opacity: 1;
			transform: none;
			transition: none;
		}
	}

	@media (max-width: 720px) {
		.hero {
			padding: 3rem 1.1rem 1.5rem;
		}

		.hero-inner {
			padding: 2.3rem 1.7rem;
		}

		.section-label {
			position: static;
			margin-bottom: 0.35rem;
			display: inline-block;
		}
	}
</style>
