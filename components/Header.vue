<script lang="ts" setup>
const settings = useSettings();
</script>

<template>
	<Bounded
		as="header"
		class="py-4 md:py-6 lg:py-8"
	>
		<div class="flex gap-4 items-center justify-between sm:flex-row flex-col">
			<Logo />
			<nav>
				<ul class="flex">
					<li
						v-for="item of settings?.data.navigation"
						:key="item.label ?? ''"
					>
						{{ item.label }}
					</li>
				</ul>
			</nav>
		</div>
	</Bounded>
</template>