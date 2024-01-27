<template>
	<div class="team q-my-xl">
		<div class="row justify-center text-center">
			<div class="col-12">
				<p class="text-h2">Our Team</p>
			</div>
		</div>
		<div class="row justify-center">
			<div class="col-12 text-center">
				<p class="text-h4">Chiropractors</p>
			</div>
			<div
				v-for="(person, index) in team.chiropractors"
				:key="index"
				class="col-10 col-md-5 text-center"
			>
				<PersonCard :person="person" />
			</div>
		</div>
		<div class="row justify-center q-mt-xl">
			<div class="col-12 text-center">
				<p class="text-h5">Massage Therapists</p>
			</div>
			<div
				v-for="(person, index) in team.massageTherapists"
				:key="index"
				class="col-10-col-md-5 text-center"
			>
				<PersonCard :person="person" />
			</div>
		</div>
		<!-- <div class="row justify-center q-mt-xl">
			<div class="col-12 text-center">
				<p class="text-h5">Office Staff</p>
			</div>
			<div
				v-for="(person, index) in team.office"
				:key="index"
				class="col-10-col-md-5 text-center"
			>
				<PersonCard :person="person" />
			</div>
		</div> -->
	</div>
</template>

<script>
import PersonCard from 'src/components/home/personCard.vue';

export default {
	name: 'components-home-team',
	components: {
		PersonCard,
	},
	setup() {
		const team = {
			chiropractors: [
				{
					name: "Terry Henderson, DC",
					about: 
						"Since graduating from Palmer College of Chiropractic in 1986, my post-graduate studies have led me to a greater understanding of the wondrous nature of our body's 'operating systems'. From my perspective, our primary job as chiropractors is to remove obstacles that impair the normal functioning of these systems and facilitate the body's innate ability to stay healthy and vital, as it was engineered to do. So often, all kinds of things (symptoms), that have been diagnosed as cardiovascular disease or prostate issues or diabetes or stomach problems or mood issues are all diagnosed as separate entities. If we truly look at how the body functions, we would see that this myriad of symptoms is often nothing more than the consequences of the body's control mechanisms being out of balance. Normally, the body will do everything in its power to keep our blood chemistry, our gut function, and our pH balance where it is supposed to be at all times. Symptoms generally only manifest themselves when the body's control mechanisms have run out of options on how to regulate an organ or system. Our body's operating systems have gone 'off line' and the result is a diagnosis of a disease, or more appropriately being in a state of 'dis-ease'. My own personal chiropractic experience dates back to when I was 10 years old and my parents took me to a chiropractor to find out if there were any “natural” solutions for my asthma and allergies. Out of that experience, my viewpoint about what chiropractic care is, and or should be, is slightly different than the average chiropractor’s perception. Increasingly, I have come to believe that our medical health care system is actually little more than a 'disease management system'.  If we are truly practicing health care, it is my belief that we must embrace the concept that our body is designed to be a self-healing, self-regenerating system that borders on perfection.",
					image: 'doch.jpg'
				},
				{
					name: "Doug Krift, DC",
					about: "Dr. Krift is a native of Northern KY and Campbell County. He has been practicing in Ft. Thomas for the past 20 years. After receiving a Bachelors degree in Biological Sciences from Northern Kentucky University in 1994 he traveled to Marietta, GA to attend Life University, College of Chiropractic",
					link: 'http://www.drkrift.com',
					image: 'dock.jpg'
				}
			],
			massageTherapists: [
				{
					name: "Debbie Benton",
					about: "Debbie has been professionally certified as a massage therapist for 20 years. She received a Bachelor of Science degree in Elementary Education from Eastern Kentucky University, and graduated from S.N.I Massage School in Lake Worth, Florida.After receiving National Certification in Florida and practicing in the massage field for 5 years, she presently resides and is licensed in the state of Kentucky, working in the office of Dr. Terry Henderson, D.C. and Dr. Doug Krift, D.C.Clinical and private practice experience comes from working in the spa industry, resorts, holistic healing centers, a yoga center, and current chiropractic office. Debbie combines traditional and leading edge techniques to provide a wide range of bodywork and pain management solutions. Various and therapeutic modalities range from light touch such as Reiki, Cranial Sacral Therapy, Bamboo and Swedish Massage to Deep Tissue.",
					image: 'debbie.jpg'
				},
			],
			office: [
				{
					name: "Angie",
					about: "About Angie.",
					image: 'angie.jpg'
				}
			]
		};

		return {
			team,
		}
	},

}
</script>

<style>

</style>