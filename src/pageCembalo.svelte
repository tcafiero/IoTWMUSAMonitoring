<script>
	let channel=1317985;
	let chartTemp = 1;
	let chartHum = 2;
	let titleTemp = "Sala Cembalo - Temperature";
	let titleHum = "Sala Cembalo - Humidity";
	import {days} from './stores';
	import {version} from './stores';
</script>

<section id="PlotSection" class="visible">
<h1>MUSA Monitoring {$version}</h1>
<label>Days</label>
<input type=number bind:value={$days} min=0 max=300>

<div id="chart1">
<iframe width="85%" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/{channel}/charts/{chartTemp}?width=auto&heigth=auto&api_key=EJ353LFDC7W3WJER&bgcolor=%23ffffff&color=%23d62020&days={$days}&dynamic=false&title={titleTemp}&type=spline&yaxis=%C2%B0C"></iframe>
<iframe width="85%" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/{channel}/charts/{chartHum}?width=auto&heigth=auto&api_key=EJ353LFDC7W3WJER&bgcolor=%23ffffff&color=%230033cc&days={$days}&dynamic=false&title={titleHum}&type=spline&yaxis=%25"></iframe>
</div>
</section>
