<script>
import jQuery from "jquery"
import IoTwAppHeader from './IoTwAppHeader.svelte';
import IoTwAppBottomMenu from './IoTwAppBottomMenu.svelte';
import IoTwAppName from './IoTwAppName.svelte';
import IoTwAppFooter from './IoTwAppFooter.svelte';
import IoTwAppDevStatus from './IoTwAppDevStatus.svelte';
import PageCembalo from './pageCembalo.svelte';
import PageRe from './pageRe.svelte';
import PageUdienze from './pageUdienze.svelte';
import PageMostra from './pageMostra.svelte';
import {state} from './stores';
import {previousState} from './stores';
import {bottomMenu} from './stores';
import {id} from './stores';
import {battery} from './stores';
import {connection} from './stores';
import {version} from './stores';
$state="PageCembalo";
$connection=undefined;
$id="Not connected";
$battery="unknown";
$version="v2.5";

$bottomMenu = [
{description: "Cembalo", icon: "icon ion-ios-exit", function: function () {
	$state="PageCembalo";
	}},
{description: "Re", icon: "icon ion-ios-exit", function: function () {
	$state="PageRe";
	}},
{description: "Udienze", icon: "icon ion-ios-exit", function: function () {
	$state="PageUdienze";
	}},
{description: "Mostra", icon: "icon ion-ios-exit", function: function () {
	$state="PageMostra";
	}}
];

sessionStorage.serialno = "log";

export function goBack() {
	alert("goBack")
	$state=$previousState;
	}

function closeWindow() {}
function readData() {}
function download() {}


</script>

<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <title>IoThingsWare MUSA monitoring v2.0</title>
    <link rel="stylesheet" href="assets/css/style.css">
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta name="description" content="MUSA monitoring app" />
    <meta name="keywords" content="bootstrap, mobile template, cordova, phonegap, mobile, html, responsive" />
    <link rel="apple-touch-icon" sizes="180x180" href="assets/img/Cloud.png" />
    <link rel="icon" type="image/png" href="assets/img/favicon.png" sizes="32x32" />
    <link rel="shortcut icon" href="assets/img/favicon.png" />

	<!-- CODELAB: Add link rel manifest -->
	<link rel="manifest" href="manifest.json" />
</head>
<body>
<IoTwAppHeader class="visible"/>
<div id="appCapsule">
	<section id="MenuSection" class="visible">
		<div>
			   {#if $state === "PageCembalo"}
				<PageCembalo />
			   {:else if $state === 'PageRe'}
				<PageRe />
			   {:else if $state === 'PageUdienze'}
				<PageUdienze />
			   {:else if $state === 'PageMostra'}
				<PageMostra />
				{:else}
				<div>Questionable choice.</div>
			{/if}
			<IoTwAppFooter />
		</div>
	</section>
</div>
<IoTwAppBottomMenu />
</body>


