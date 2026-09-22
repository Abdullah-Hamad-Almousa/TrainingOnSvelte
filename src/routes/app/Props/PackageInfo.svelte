<script lang="ts">

	//You do on this way
	let stuff = $props();
	//Or on this way
	//let { name, version, description, website } = $props();

	//This is for tracing our objects
	console.log(stuff.name, stuff.version, stuff.description, stuff.website);

</script>

<p>

	The <code>{stuff.name}</code> package is {stuff.description}. Download version {stuff.version} from
	<a href="https://www.npmjs.com/package/{stuff.name}">npm</a> and
	<a href={stuff.website}>learn more here</a>
</p>