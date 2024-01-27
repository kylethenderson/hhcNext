<template>
	<div class="services q-py-xl">
		<div class="row justify-center q-my-lg">
			<div class="col-12 col-md-10 text-center">
				<p class="text-h2 q-mb-xl q-mt-sm text-white">Our Approach</p>
			</div>
			<div class="col-10 col-sm-4 col-md-3 q-mx-md" v-for="(service, index) in services" :key="index">
				<q-card class="q-my-md serviceCard" :style="serviceCardStyle">
					<div class="row justify-center">
						<div class="col-12 self-center text-center">
							<q-icon size="64px" class="q-my-md" color="accent" :name="icons[service.icon]"></q-icon>
						</div>
						<div class="col-11 self-center text-center">
							<p class="text-h6 q-mb-sm">
								{{ service.title }}
							</p>
						</div>
						<div class="col-11 text-center">
							<p class="q-mb-none">{{ service.text }}</p>
						</div>
					</div>
				</q-card>
			</div>
		</div>
	</div>
</template>

<script>
import { 
	mdiMedicalBag,
	mdiHandHeart,
	mdiAccountHeart,
	mdiBrain,
	mdiFoodAppleOutline,
} from '@quasar/extras/mdi-v7';
export default {
	name: 'components-home-services',
	setup () {
		const icons = {
			mdiMedicalBag,
			mdiHandHeart,
			mdiAccountHeart,
			mdiBrain,
			mdiFoodAppleOutline,
		};
		const services = [
			{
				title: "Chiropractic Adjustment",
				text:
					"At the heart of what we do, the chiropractic adjustment is a technique or method of reestablishing body function through proper alignment of the involved areas of the spine and extremities.",
				icon: "mdiMedicalBag",
				link: "",
				href: ""
			},
			{
				title: "Massage Therapy",
				text:
					"The manual manipulation of soft body tissues to normalize those tissues and enhance a person’s health and well-being.",
				icon: "mdiHandHeart",
				link: "",
				href: ""
			},
			{
				title: "Nutritional Counseling",
				text: "Counseling of nutritional intake and supplementation.",
				icon: "mdiFoodAppleOutline",
				link: "",
				href: ""
			},
			{
				title: "Contact Reflex Analysis (CRA)",
				text:
					"A technique of assessing proper body functions through reflex testing.",
				icon: "mdiAccountHeart",
				link: "",
				href: ""
			},
			{
				title: "Nuero Emotional Technique (NET)",
				text:
					"A mind/body technique whereby stress induced emotional blockages are removed that stifle physical health and well being of the individual.",
				icon: "mdiBrain",
				link: "",
				href: ""
			},
		];

		const serviceCardStyle = {
			minHeight: '300px',
		};
		return {
			services,
			icons,
			serviceCardStyle,
		}
	}
}
</script>


<style lang="scss" scoped>
.services {
	background: linear-gradient(rgba(34, 34, 34, 0.75), rgba(34, 34, 34, 0.75)),
		url("src/assets/forest1.jpg");
	background-attachment: fixed;
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center;
}
.serviceCard {
	background-color: rgba(59, 85, 63, .7);
	color: white;	
}
</style>