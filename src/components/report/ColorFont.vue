<template>
	<section class="color" id="color">
		<h2 class="section-title">Color</h2>
		<div class="content">
			<p>
				This font has
				<strong>{{ $filters.listify(this.font.colorFormats) }}</strong>
				color glyphs.

				<template v-if="palettes.length">
					It has {{ palettes.length }}
					{{ $filters.pluralize(palettes.length, "palette") }}.
				</template>
				<template v-else>
					The colors are hardcoded in the font.
				</template>
			</p>
			<template v-if="palettes.length">
				<h3>Palettes</h3>
				<ul
					class="palette"
					v-for="(palette, palIndex) in palettes"
					:key="`pal_${palIndex}`"
				>
					<li
						v-for="(color, colorIndex) in palette"
						:key="`clr_${palIndex}_${colorIndex}`"
						:style="{ background: color }"
					>
						<span class="label">{{ color }}</span>
					</li>
				</ul>
			</template>
		</div>
	</section>
</template>

<script src="./ColorFont.js"></script>
<style src="./ColorFont.css" scoped></style>
