<script>
	let days = 3;
	let chartTemp = 7;
	let chartHum = 8;
	let titleTemp = "Sala Mostra - Temperature";
	let titleHum = "Sala Mostra - Humidity";
</script>

<section id="PlotSection" class="visible">
<h1>MUSA Monitoring</h1>
<label>Days</label>
<input type=number bind:value={days} min=0 max=100>
<div id="chart">
<iframe width="450" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/505552/charts/{chartTemp}?bgcolor=%23ffffff&color=%23d62020&days={days}&dynamic=true&title={titleTemp}&type=spline&update=1&xaxis=hh%3Amm&yaxis=%C2%B0C"></iframe>
<iframe width="450" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/505552/charts/{chartHum}?bgcolor=%23ffffff&color=%23d62020&days={days}&dynamic=true&title={titleHum}&type=spline&update=1&xaxis=hh%3Amm&yaxis=%C2%B0C"></iframe>
</div>
</section>
