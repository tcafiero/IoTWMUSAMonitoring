<script>
	let channel=505552;
	let chartTemp = 3;
	let chartHum = 4;
	let titleTemp = "Sala del Re - Temperature";
	let titleHum = "Sala del Re - Humidity";
	import {days} from './stores';
</script>

<section id="PlotSection" class="visible">
<h1>MUSA Monitoring</h1>
<label>Days</label>
<input type=number bind:value={$days} min=0 max=100>

<div id="chart1">
<iframe width="85%" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/{channel}/charts/{chartTemp}?width=auto&heigth=auto&api_key=EJ353LFDC7W3WJER&bgcolor=%23ffffff&color=%23d62020&days={$days}&dynamic=false&title={titleTemp}&type=spline&yaxis=%C2%B0C"></iframe>
<iframe width="85%" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/{channel}/charts/{chartHum}?width=auto&heigth=auto&api_key=EJ353LFDC7W3WJER&bgcolor=%23ffffff&color=%230033cc&days={$days}&dynamic=false&title={titleHum}&type=spline&yaxis=%25"></iframe>
</div>
</section>
