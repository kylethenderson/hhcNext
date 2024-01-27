<template>
	<div class="row justify-center">
		<div class="col-shrink">
			<q-card class="imageCard q-mx-md cursor-pointer" @click="toggleDetails">
				<img :src="imageUrl" :alt="`${person.name} image`">
				<div class="absolute-bottom text-white q-py-md" style="backgroundColor: rgba(0,0,0,.5)">
					<div class="text-h6" style="position: relative;">
						{{ person.name }}
						<q-icon size="14px" class="q-pl-lg q-pb-xs" :name="mdiOpenInNew" style="position: absolute; right: 10px; top: 8px;"></q-icon>
					</div>
				</div>
			</q-card>
		</div>
	</div>
	<q-dialog v-model="detailsDialog">
		<q-card class="detailCard q-mx-md">
			<q-card-section class="bg-grey-8 text-white">
				<div class="row justify-between">
					<div class="col-shrink self-center">
						<div class="text-h6">{{ person.name }}</div>
					</div>
					<div class="col-shrink self-center">
						<q-icon size="20px" :name="mdiClose" @click="toggleDetails"></q-icon>
					</div>
				</div>
			</q-card-section>
			<q-card-section style="max-height: 50vh; overflow-y: auto;">
				<p class="text-justify">{{ person.about }}</p>
			</q-card-section>
		</q-card>
	</q-dialog>
	<!-- <q-tab-panels
		v-model="panel"
		@click="togglePanel"
		animated
		transition-prev="fade"
		transition-next="fade"
	>
        <q-tab-panel name="image" class="q-mx-auto">
			<div class="row justify-center">
				<div class="col-shrink">
					<q-card class="profileCard image q-mx-md cursor-pointer">
						<img :src="imageUrl" :alt="`${person.name} image`">
						<div class="absolute-bottom text-h6 text-white q-py-md" style="backgroundColor: rgba(0,0,0,.5)">
							{{ person.name }}
						</div>
					</q-card>
				</div>
			</div>
        </q-tab-panel>

        <q-tab-panel name="details">
			<div class="row justify-center">
				<div class="col-shrink">
					<q-card class="profileCard q-mx-md">
						<q-card-section class="bg-grey-8 text-white">
							<div class="text-h6">{{ person.name }}</div>
						</q-card-section>
						<q-card-section style="max-height: calc(325px - 64px); overflow: auto">
							<p class="text-justify">{{ person.about }}</p>
						</q-card-section>
					</q-card>
				</div>
			</div>
        </q-tab-panel>
      </q-tab-panels> -->
</template>

<script>
import { computed, ref } from 'vue';
import { 
	mdiClose,
	mdiOpenInNew,
} from '@quasar/extras/mdi-v7';

export default {
	name: 'components-home-team-personCard',
	props: {
		person: {
			type: Object,
			default: () => ({}),
		},
	},
	setup(props, {emit}) {
		const imageUrl = computed(() => new URL(`/src/assets/${props.person.image}`, import.meta.url).href);
		const detailsDialog = ref(false);

		const toggleDetails = () => {
			detailsDialog.value = !detailsDialog.value;
		}

		const panelOptions = ['image', 'details']
		const panel = ref('image');

		const togglePanel = () => {
			const remainingOption = panelOptions.filter((option) => option !== panel.value)[0];
			panel.value = remainingOption;
		};

		return {
			detailsDialog,
			toggleDetails,
			mdiClose,
			mdiOpenInNew,
			panel,
			togglePanel,
			imageUrl,
		}
	}
}
</script>

<style scoped>
.imageCard {
	height: 325px;
	width: 275px;
	max-height: 325px;
	overflow: hidden;
}
.imageCard img {
	height: 100%;
	width: 100%;
	object-fit: cover;
	object-position: center;
}
</style>