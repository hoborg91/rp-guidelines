<script>
	import GuidelineChunk from './GuidelineChunk.svelte';
	import * as data from './data.json';
	const guidelines = data.default;
</script>

<h1>Пиши правильно!</h1>

<div class="faq-div">
	<span class="faq-question">Что это за страница?</span> Бывает, перед честным русским либералом встаёт непростая задача осветить сложные и противоречивые тенденции современного общества. 
	Следует помнить, что методы освещения существенно зависят от местности, в которой происходят события. 
	С целью облегчить добросовестный труд благожелателей, на этой странице в форме шпаргалки собраны указания на то, в каких выражениях следует изъясняться и на чём следует акцентировать внимание при написании новостей и заметок. 
	Некоторые указания удалось снабдить подходящими примерами, найденными у корифеев пера и «Ютьюба». 
</div>

<table class="main-table">
	<thead>
		<tr>
			<th>Тема</th>
			<th>Если речь идёт о западной Европе, США и Канаде</th>
			<th>Если речь идёт о России</th>
		</tr>
	</thead>
	<tbody>
		{#each guidelines as guideline}
		<tr>
			<td class="topic-td">{guideline.topic || ''}</td>
			<td><GuidelineChunk guideline={guideline.west}/></td>
			<td><GuidelineChunk guideline={guideline.russia}/></td>
		</tr>
		{/each}
	</tbody>
</table>

<div class="faq-div">
	<span class="faq-question">И помните!</span> 
	В некоторых случаях полезно делать отдельные уступки и оговорки; не нужно, чтобы под натиском неприятной правды читатель или зритель отказался воспринимать материал. 
	Постарайтесь доказать, что вы все силы прикладываете к тому, чтобы объективно исследовать ситуацию, ведь так и есть на самом деле! 
	К сожалению, волшебная фраза «Это другое!» была в последнее время дискредетирована плохо подготовленными благожелателями. 
	От вас потребуется изобрести несколько более продуманный подход к чувствам потребителей.  
</div>

<style>
	h1 {
		color: lightskyblue;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		margin: 0px;
	}

	.faq-div {
		margin-top: 10px;
		margin-bottom: 10px;
	}

	.faq-question {
		background-color: lightskyblue;
		border-radius: 10px;
		padding-left: 7px;
		padding-right: 7px;
	}

	.main-table {
		margin-top: 20px;
	}

	.main-table th {
		vertical-align: top;
		padding: 10px;
		text-align: left;
	}

	.main-table td {
		vertical-align: top;
		padding: 10px;
	}

	.main-table .topic-td {
		font-weight: bold;
	}
</style>