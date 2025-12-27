<script lang="ts">
	import image_utako from '$lib/assets/utako.jpg';
	import image_logo from '$lib/assets/logo.svg';
	import image_site from '$lib/assets/site_image.png';
	import image_comiket from '$lib/assets/comiket.jpg';

	const sections = [
		{
			id: 'hero',
			title: 'UTAKO TUNE memorial',
			underline: '関わってくれたすべての人へ、感謝を込めて。',
			body: ['9年間続いた個人プロジェクト UTAKO TUNE は、2025年をもって静かに幕を閉じました。', '支えてくれたすべての時間に、人に、つながりに、そして素敵な作品を作り続けてくれた人たちに、静かに感謝を込めて。']
		},
		{
			id: 'reflection',
			title: '始まりへの回想',
			body: [
				'2016 年の秋ごろ、ボカロの新曲を探し続ける中で、ふと「いい曲が多すぎて、どこから聴けばいいのか分からない」という戸惑いが生まれました。ランキングにも映らない、再生数 1,000 前後の、けれど確かに心を掴む楽曲たち。その気配に背中を押されて、UTAKO TUNE は生まれました。',
				'解析システムを組み、Web サービスを整え、コミックマーケットで同人誌としてまとめるまでの数年間は、技術と音楽と生活がひとつに溶け合っていた時間でした。うまくいかない深層学習モデルに悩み、生活リズムを犠牲にしながらも手を動かし続けた日々は、今でも鮮明に思い出せます。'
			],
			aside: 'このページは、その時間が確かにここにあったことを、ささやかに記しておくための場所です。'
		},
		{
			id: 'values',
			title: '持ち続けた理念',
			items: [
				{title: '埋もれた名曲へのまなざし', description: '再生数やランキングだけでは届かない楽曲たちに、光を当てたい。\n「どうしてこの曲がこの再生数なんだろう」と感じた違和感が、プロジェクトの出発点でした。'},
				{title: '文化へのささやかな貢献', description: '個人規模のプロジェクトであっても、VOCALOID という文化に向けて、もう一本別のルートを差し出したかった。UTAKO TUNE は、そのための小さな実験場でした。'},
				{title: '技術で世界を見通す試み', description: '深層学習やクラウドインフラなど、当時の最新技術を用いて、 「楽曲同士の近さ」を座標として捉え直す。技術は目的ではなく、視界を広げるためのレンズでした。'},
			]
		},
		{
			id: 'gratitude',
			title: '感謝を込めて',
			body: [
				'UTAKO TUNE を訪れてくれたすべての人へ。新着一覧を眺め、似ているかもしれない楽曲を辿り、そこで何かひとつでも「出会い」が生まれていたなら、このプロジェクトは十分すぎるほど報われています。',
				'VOCALOID楽曲に関わり続けてくれたすべてのクリエイターたちへ。みなさんが作品を公開してくれたからこそ、解析することも、推薦することもできました。勝手ながら、その宇宙の片隅で、ひとつの観測点として存在させてもらいました。',
				'深層学習フレームワークやクラウド基盤など、技術を提供してくれたコミュニティへ。多くのオープンソースやサービスの上に、この小さなプロジェクトは立っていました。',
				'そして、コミックマーケットで本を手に取ってくださった方へ。通りがかりのスペースから一冊を連れて帰ってもらえたことが、とても嬉しかったです。'
			],
			aside: '最後に、あの頃の自分へ。よくここまで続けました。無茶もしたけれど、その時間は確かに糧になりました。'
		},
		{
			id: 'turning-point',
			title: '区切りという決断',
			body: [
				'UTAKO TUNE を続けることは、だんだんと「維持するための時間」と「他にやりたいこと」のあいだで バランスを取る行為になっていきました。インフラの更新、フレームワークのディスコン、ランニングコストの増大。どれも避けて通れない現実です。',
				'生活と環境が変わり、まとまった時間を捻出することが難しくなったこと。インフラやライブラリの更新に追いつくための負担が、少しずつ重くなっていったこと。Kiite やボカコレなど、より大きなスケールで同じ課題に向き合うサービスが育ってきたこと。次のプロジェクトや生活に、違う形でエネルギーを使いたいと感じるようになったこと。',
				'これらを踏まえて、「ここでいったん閉じよう」と静かに決めました。終わりは後ろ向きなものではなく、次の一歩のために空けるスペースでもあります。'
			]
		},
		{
			id: 'exhibits',
			title: '記憶と追憶',
			images: [
				{ src: image_site, caption: 'UTAKO TUNEのスクリーンショット' },
				{ src: image_utako, caption: 'UTAKO TUNEのメインキャラクター「折原 詩子」' },
				{ src: image_logo, caption: 'UTAKO TUNEのロゴマーク。音符を鎖状に組み合わせ、中央を目に見立てています' },
				{ src: image_comiket, caption: 'コミックマーケット97(2019冬)で頒布した際の様子' }],
			body: [
				'当時のUTAKO TUNEの雰囲気を残すため、いくつかの画像をここに展示します。',
			],
			aside: 'たしかにここにあったプロダクトの、ささやかな記録として。'
		},
		{
			id: 'note-to-myself',
			title: '自分自身に宛てて',
			body: [
				'UTAKO TUNE は、小さな個人プロジェクトでした。それでも、解析モデルを組み上げ、実際に動くサービスとして公開し、本としてまとめ、コミュニティに投げかけるところまで辿り着きました。',
				'うまくいかなかった実験や、途中で消えていったアイデアもたくさんあります。けれど、それらを含めて、このプロジェクトは今の自分の基礎の一部になっています。次に何かを始めるとき、「小さく作って試し、少しずつ育てていく」という感覚を、どうか忘れないでください。'
			],
			aside: '未来の自分へ。あなたはきっと、また新しい何かを始めるでしょう。そのとき、この言葉が少しでも役に立ちますように。'
		},
		{
			id: 'epilogue',
			title: 'おわりに',
			body: [
				'2025年 — UTAKO TUNE はここでそっと幕を閉じます。',
				'これを一つの区切りとして、関わってくれたすべての人へ、改めて感謝を込めて。',
				'ありがとうございました。'
			]
		}
	];

	const revealOnce = (node: HTMLElement) => {
		const show = () => node.classList.add('visible');

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
			{ threshold: 0.5 }
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
			<p class="underline">{sections[0].underline}</p>
			<h1>{sections[0].title}</h1>
			<p class="lead">
				{#each sections[0].body as paragraph}
					{paragraph}
					<br />
				{/each}
			</p>
			<div class="scroll-cue">
				<span>scroll</span>
				<div class="line"></div>
			</div>
		</div>
	</section>

	<section class="content">
		{#each sections.slice(1) as section}
			<article class="section-block" id={section.id}>
				<div class="card" use:revealOnce>
					<p class="section-label">{section.id}</p>
					<div class="card-body">
						<h2>{section.title}</h2>
						{#if section.items}
							<ul class="values">
								{#each section.items as item}
									<li>
										<strong>{item.title}</strong>
										{#if item.description}
											<p>{item.description}</p>
										{/if}
									</li>
								{/each}
							</ul>
						{:else if Array.isArray(section.body)}
							{#each section.body as paragraph}
								<p>{paragraph}</p>
							{/each}
						{:else}
							<p>{section.body}</p>
						{/if}
						{#if section.images}
							<div class="image-grid">
								{#each section.images as image}
									<figure>
										<img src={image.src} alt={image.caption} />
										<figcaption>{image.caption}</figcaption>
									</figure>
								{/each}
							</div>
						{/if}
						{#if section.aside}
							<p class="aside">{section.aside}</p>
						{/if}
					</div>
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
		font-family: 'Manrope', 'IBM Plex Sans JP', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
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
		white-space: pre-wrap;
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

	.underline {
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
		font-family: 'Raleway', 'IBM Plex Sans JP', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
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

	.section-block {
		min-height: 100vh;
		display: flex;
		align-items: center;
		padding: 6vh 0;
	}

	.card {
		position: relative;
		background: rgba(255, 255, 255, 0.9);
		border: 1px solid #efe8ff;
		border-radius: 20px;
		padding: 2rem;
		box-shadow: 0 15px 45px rgba(69, 37, 116, 0.08);
		opacity: 0;
		transform: translateY(26px);
		transition: opacity 700ms ease, transform 700ms ease;
		width: 100%;
		max-width: 720px;
		margin: auto;
	}

	/* svelte-ignore css-unused-selector -- class is added dynamically by the revealOnce action */
	:global(.card.visible) {
		opacity: 1;
		transform: translateY(0);
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
		display: grid;
		gap: 0.55rem;
	}

	.card-body h2 {
		margin: 0;
		font-size: 1.35rem;
		font-weight: 700;
		color: #2a1d44;
	}

	.card-body p {
		margin: 0;
		line-height: 1.7;
		color: #372f4f;
		font-size: 1rem;
		white-space: pre-wrap;
	}

	.values {
		list-style: none;
		padding: 0;
		margin: 0.2rem 0 0;
		display: grid;
		gap: 1rem;
	}

	.values li {
		padding: 0.65rem 0.85rem;
		border: 1px dashed #d7ccf3;
		border-radius: 12px;
		background: #fbf9ff;
		color: #342a4f;
	}

	.aside {
		margin-top: 1rem;
		font-size: 0.95rem;
		color: #8e86a8 !important;
		font-style: italic;
	}

	.image-grid {
		display: grid;
		grid-template-columns: repeat(2, minmax(0, 1fr));
		gap: 1rem;
		margin-top: 0.5rem;
	}

	.image-grid figure {
		margin: 0;
		border: 1px solid #efe8ff;
		border-radius: 14px;
		overflow: hidden;
		background: #fbf9ff;
		box-shadow: 0 10px 30px rgba(69, 37, 116, 0.06);
		display: grid;
		grid-template-rows: auto 1fr;
	}

	.image-grid img {
		width: 100%;
		display: block;
		object-fit: cover;
	}

	.image-grid figcaption {
		padding: 0.75rem 0.9rem;
		font-size: 0.95rem;
		color: #342a4f;
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

		.section-block {
			min-height: 90vh;
		}

		.section-label {
			position: static;
			margin-bottom: 0.35rem;
			display: inline-block;
		}

		.image-grid {
			grid-template-columns: 1fr;
		}
	}
</style>
