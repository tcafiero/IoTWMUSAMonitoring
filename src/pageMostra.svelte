<script>
	let channel=505552;
	let chartTemp = 7;
	let chartHum = 8;
	let titleTemp = "Sala Mostra - Temperature";
	let titleHum = "Sala Mostra - Humidity";
	import {days} from './stores';
</script>

<section id="PlotSection" class="visible">
<h1>MUSA Monitoring</h1>
<label>Days</label>
<input type=number bind:value={$days} min=0 max=100>

<div id="chart1">
<iframe width="85%" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/{channel}/charts/{chartTemp}?width=auto&heigth=auto&bgcolor=%23ffffff&color=%23d62020&days={$days}&dynamic=true&title={titleTemp}&type=spline&update=1&xaxis=hh%3Amm&yaxis=%C2%B0C"></iframe>
<iframe width="85%" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/{channel}/charts/{chartHum}?width=auto&heigth=auto&bgcolor=%23ffffff&color=%230033cc&days={$days}&dynamic=true&title={titleHum}&type=spline&update=1&xaxis=hh%3Amm&yaxis=%25"></iframe>
</div>
</section>
