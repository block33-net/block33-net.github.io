Some text

<div>
	<div>
		<span>Status:</span> <span id="status"></span>
	</div>
	<div>
		<span>Players:</span> <span id="players"></span>
	</div>
	<ol id="players-list">

	</ol>
</div>
<script>
  fetch('https://mcapi.us/server/query?ip=mc.block33.net')
    .then(response => response.json())
    .then(data => {
		document.getElementById("status").innerHTML = data.online ? "online" : "offline";
		document.getElementById("players").innerHTML = data.players.now;
		for (var name of data.players.list) {
			var ul = document.getElementById("players-list");
			var li = document.createElement("li");
		    li.appendChild(document.createTextNode(name));
		    ul.appendChild(li);
		}
    });
</script>