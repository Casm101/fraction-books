
<script lang="ts">

	import Navigation from "../components/navigation.svelte";
	import PageWrapper from "../components/PageWrapper.svelte";

	const test = () => {
		console.log("test");
	}

	interface IFractionInput {
		input: string;
		dictionary: string[];
	}

	// Must extended to include capitalized letters
	const myDictionary = {
		space: "000",
		a: "001",
		b: "002",
		c: "003",
		d: "004",
		e: "005",
		f: "006",
		g: "007",
		h: "008",
		i: "009",
		j: "010",
		k: "011",
		l: "012",
		m: "013",
		n: "014",
		ñ: "015",
		o: "016",
		p: "017",
		q: "018",
		r: "019",
		s: "020",
		t: "021",
		u: "022",
		v: "023",
		w: "024",
		x: "025",
		y: "026",
		z: "027",
	}

	const userInput = "Hello World";
	let output: string = "";
	const fractionInput = ({ input, dictionary}: IFractionInput) => {
		for (let char = 0; char < input.length; char++) {
			console.log(output);
			if (input[char] === " ") output += dictionary["space"];
			else { output += dictionary[input[char].toLocaleLowerCase()]; }
		}
		console.log(parseFloat("." + output));
	}

</script>

<style lang="css">

	.tester {
		color: red;
		cursor: pointer;
	}
</style>

<Navigation />
<PageWrapper>
	<h1></h1>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
</PageWrapper>


{fractionInput({input: userInput, dictionary: myDictionary})}