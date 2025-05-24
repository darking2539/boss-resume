<script lang="ts">
	import Hideable from './Hideable.svelte';
	import HomeIcon from '../icons/home.svelte';
	import EmailIcon from '../icons/email.svelte';
	import TelephoneIcon from '../icons/telephone.svelte';
	import LinkedinIcon from '../icons/linkedin.svelte';
	import GithubIcon from '../icons/github.svelte';
	export let name: string = '';
	export let phone: string = '';
	export let email: string = '';
	export let github: string = '';
	export let linkedin: string = '';
	export let location: string = '';
	export let introduction: string = '';
</script>

<div class="flex flex-col text-sm sm:text-base">
	<h2
		class="text-start sm:order-none print:order-none text-2xl sm:text-3xl md:text-4xl lg:text-5xl print:pt-0 print:text-4xl"
	>
		{name}
	</h2>

	<div
		class="flex text-left sm:py-2 w-48 space-x-2 justify-between text-nowrap print:py-0 text-xs sm:text-xs md:text-base print:text-[15px]"
	>
		<div class="flex items-center justify-center">
			<HomeIcon />
			<div class="ml-1">{location}</div>
		</div>
		<div>
			| <EmailIcon />
			<a href={`mailto:${email}`}>
				{email}
			</a>
		</div>
		<div>
			| <TelephoneIcon />
			<a href={`tel:${phone}`}>
				{phone}
			</a>
		</div>
		<div>
			| <LinkedinIcon />
			<a href={`https://linkedin.com/in/${linkedin}`} target="_blank" rel="noreferrer">
				{linkedin}
			</a>
		</div>
		<div>
			| <GithubIcon />
			<a href={`https://github.com/${github}`} target="_blank" rel="noreferrer">
				{github}
			</a>
		</div>
	</div>
	<div class="flex text-center print:text-xs mt-2">
		<Hideable>
			<p>{introduction}</p>
		</Hideable>
	</div>
</div>

<style lang="postcss">
	a {
		text-decoration: underline;
	}
</style>
