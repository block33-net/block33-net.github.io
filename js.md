Some text

<div id="textx"></div>
<script>
  fetch('https://mcapi.us/server/status?ip=mc.block33.net')
    .then(response => response.json())
    .then(data => {
		document.getElementById("textx").innerHTML = data.online ? "online" : "offline";
    });
</script>