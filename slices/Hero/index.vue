<script setup lang="ts">
import { type Content } from "@prismicio/client";
import Bounded from "~/components/Bounded.vue";

// The array passed to `getSliceComponentProps` is purely optional.
// Consider it as a visual hint for you when templating your slice.
defineProps(
  getSliceComponentProps<Content.HeroSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ]),
);
</script>

<template>
	<Bounded
		:data-slice-type="slice.slice_type"
		:data-slice-variation="slice.variation"
	>
		<div class="grid grid-cols-1 place-items-center">
			<div class="flex flex-col items-center text-center">
				<PrismicRichText
					:field="slice.primary.heading"
					class="heading heading--xl mb-4 md:mb-8"
				/>
				<PrismicRichText
					:field="slice.primary.body"
					class="mb-4 md:mb-8 text-2xl font-normal leading-10 font-body max-w-lg text-slate-600"
				/>
				<PrismicLink
					:field="slice.primary.button_link"
					class="button mb-8 md:mb-10"
				>
					{{ slice.primary.button_text }}
				</PrismicLink>
				<PrismicImage
					:field="slice.primary.image"
					class="max-w-4xl w-full drop-shadow-xl"
				/>
			</div>
		</div>
	</Bounded>
</template>
