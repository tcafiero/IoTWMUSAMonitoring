<script>
	let chartTemp = 5;
	let chartHum = 6;
	let titleTemp = "Sala Udienze - Temperature";
	let titleHum = "Sala Udienze - Humidity";
	import {days} from './stores';
</script>

<section id="PlotSection" class="visible">
<h1>MUSA Monitoring</h1>
<label>Days</label>
<input type=number bind:value={$days} min=0 max=100>

<div id="chart1">
<iframe width="350" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/505552/charts/{chartTemp}?bgcolor=%23ffffff&color=%23d62020&days={$days}&dynamic=true&title={titleTemp}&type=spline&update=1&xaxis=hh%3Amm&yaxis=%C2%B0C"></iframe>
<iframe width="350" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/505552/charts/{chartHum}?bgcolor=%23ffffff&color=%230033cc&days={$days}&dynamic=true&title={titleHum}&type=spline&update=1&xaxis=hh%3Amm&yaxis=%25"></iframe>
</div>
</section>
