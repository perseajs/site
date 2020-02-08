<style>
	@import url('https://fonts.googleapis.com/css?family=IBM+Plex+Mono:400,300i&display=swap');

	h1, h2 {
		text-align: center;
		margin: 0 auto;
		padding: 0;
	}

	h1 {
		letter-spacing: 0.3em;
		font-size: 4em;
	}
	h2 {
		font-style: italic;
		margin-bottom: 2rem;
	}

	hr {
		margin: 2rem 0;
		border: none;
		height: 1px;
		width: 100%;
		background: #ddd;
	}

	.terminal {
		border: 1px solid #ddd;
		border-radius: 5px;
	}
	.terminal-topbar {
		content: '';
		display: flex;
		width: 100%;
		background: #ddd;
		align-items: center;
		padding: 0.5rem 1rem;
	}
	.terminal-topbar-button {
		content: '';
		display: block;
		height: 15px;
		width: 15px;
		background: #eee;
		border-radius: 100%;
		margin-right: 0.5rem;
	}
	pre {
		font-family: 'IBM Plex Mono', monospace;
		margin: 0;
		padding: 1rem;
		background: #fff;
	}

	section {
		padding: 2rem 0;
		background-color: #fff;
		margin: 0 auto;
	}
	section:nth-child(even) {
		background: #fcfcfc;
	}
	.section-content {
		max-width: 48em;
		margin: 0 auto;
	}
</style>

<svelte:head>
	<title>Persea - intentionally simple and quick http server for node.js</title>
</svelte:head>

<section>
	<div class="section-content">
		<h1>Persea</h1>
		<h2>
			Intentionally simple and quick
			<br>
			An http server for node.js</h2>

		<hr />

		<div class="terminal">
			<div class="terminal-topbar">
				<div class="terminal-topbar-button"></div>
				<div class="terminal-topbar-button"></div>
				<div class="terminal-topbar-button"></div>
			</div>
			<pre>
$ yarn persea dev
Master 70423 is running
Worker 70424 started
Worker 70425 started
Worker 70426 started
Worker 70427 started
Worker 70428 started
Worker 70429 started
Worker 70430 started
Worker 70431 started
			</pre>
		</div>
	</div>
</section>

<section>
	<div class="section-content">
		<h2>Get Started</h2>
		<pre>
$ # Step 1: install
$ yarn add persea
$ # OR
$ npm install persea

$ # Step 2: run
$ yarn persea dev
Master 70423 is running
Worker 70424 started
Worker 70425 started
Worker 70426 started
Worker 70427 started
Worker 70428 started
Worker 70429 started
Worker 70430 started
Worker 70431 started

$ # Step 3: from another terminal, create an endpoint
$ mkdir routes
$ echo "{`
module.exports.index = () => {
	response.send({ body: 'hello world' });
};
`}" > routes/foo.js
$ # The master process should notice this new file and restart the workers
$ # with the new code

$ # Step 4: ...
$ curl http://localhost:8080/foo
hello world
		</pre>
	<div>
</section>
