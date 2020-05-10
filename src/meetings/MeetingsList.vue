<template>
	<div>
		<div v-if="meetings.length > 0">
			<h3>Zaplanowane zajęcia ({{meetings.length}})</h3>
			<table>
				<thead>
				<tr>
					<th>Nazwa spotkania</th>
					<th>Opis</th>
					<th>Uczestnicy</th>
					<th></th>
				</tr>
				</thead>
				<tbody>
				<tr v-for="meeting in meetings" :key="meeting.name">
					<td>{{ meeting.name }}</td>
					<td>{{ meeting.description }}</td>
					<td></td>
					<td style="text-align: right">
						<button id="enrollButton" class="button button-outline">Zapisz się</button>
						<button>Usuń puste spotkanie</button>
					</td>
				</tr>
				</tbody>
			</table>
		</div>
		<div v-else>
			Brak zaplanowanych spotkań
		</div>
	</div>
</template>

<script>
    export default {
        props: ['meetings']
    }
</script>

<style>
    #enrollButton {
        margin-right: 5px;
    }
</style>