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
		/* border: 1px solid #ddd; */
		border-radius: 3px;
		box-shadow:  10px 10px 20px #e3e3e3,
             -10px -10px 20px #ffffff;
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
	.code {
		background: #fff;
		box-shadow:  10px 10px 20px #e3e3e3,
             -10px -10px 20px #ffffff;
		margin-bottom: 2rem;
	}

	section {
		padding: 2rem 0;
		background-color: #fff;
		margin: 0 auto;
	}
	section:nth-child(even) {
		background: #fdfdfd;
	}
	.section-content {
		max-width: 48em;
		margin: 0 auto;
	}

	footer {
		text-align: center;
		margin: 2rem 0;
		filter: grayscale(1);
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
{`$ yarn persea dev
Master 70423 is running
Worker 70424 started
Worker 70425 started
Worker 70426 started
Worker 70427 started
Worker 70428 started
Worker 70429 started
Worker 70430 started
Worker 70431 started`.trim()}
		</pre>
		</div>
	</div>
</section>

<section>
	<div class="section-content">
		<h2>Features</h2>
		<ul>
			<li>Isolated context per-request</li>
			<li>Automatic routing</li>
			<li>Simple middleware</li>
			<li>Hot-reloading out of the box in development</li>
			<li>Self-healing workers</li>
			<li>TypeScript support</li>
		</ul>
	</div>
</section>

<section>
	<div class="section-content">
		<h2>Get Started</h2>
		<p>1. Install</p>
		<pre class="code">
{`
$ yarn add @persea/persea
$ # OR
$ npm install @persea/persea
`.trim()}
		</pre>

		<p>2. Run</p>
		<pre class="code">
{`$ yarn persea dev
Master 70423 is running
Worker 70424 started
Worker 70425 started
Worker 70426 started
Worker 70427 started
Worker 70428 started
Worker 70429 started
Worker 70430 started
Worker 70431 started`.trim()}
		</pre>

		<p>3. Add a route</p>
		<pre class="code">
{`$ mkdir routes
$ echo "module.exports.index = () =>
	response.send({ body: 'hello world' });" > routes/foo.js
$ # The master process should notice this new file and restart the workers
$ # with the new code`.trim()}
		</pre>

		<p>4. See it in action</p>
		<pre class="code">
{`$ curl http://localhost:8080/foo
hello world`.trim()}
		</pre>
	<div>
</section>

<footer>
	<span>🥑</span>
</footer>
