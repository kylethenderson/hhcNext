<template>
	<div class="row justify-center bg-primary text-white q-py-xl" >
		<div class="col-11 col-md-6">
			<p class="text-h2">What to expect</p>
			<p class="text-h5">
				From the moment you enter our office, we strive to provide the highest level of attention to your care.
			</p>
		</div>
		<div class="row justify-center">
			<div class="col-12 col-md-6">
				<p>
					Once the necessary paperwork is completed, you can expect a one on one evaluation to trace the source of your concerns or complaints.
					Standardized medical approaches such as X-Rays aren't necessarily required, but are considered based upon the evaluation.
					The doctor will outline a series of treatment suggestions or options for your consideration and care will usually begin on your first visit.
					We are cost-conscience and will work with you and your insurance company to provide the greatest level of care at the lowest cost to you.
				</p>
			</div>
			<div class="row justify-center">
				<div class="col-11 col-md-6">
					<p class="text-h5">To make your first appointment, call us at</p>
					<a href="8597818799" type="tel">859-781-8700</a>
				</div>
			</div>
			<div class="row justify-center">
				<div class="col-11-col-md-6">
					<p class="text-h5">Please print and complete the appropriate forms before your first visit.</p>
					<q-btn>New Patient Registration</q-btn>
					<q-btn>Massage Therapy Intake</q-btn>
				</div>
			</div>
		</div>
	</div>
		<!-- <PdfViewer :isOpen="dialogs.intake" :form="selectedForm" @onClose="closeFormDialog" /> -->
		<!-- <v-dialog v-model="dialogs.form" persistent fullscreen>
			<IntakeForm v-if="selectedForm === 'intakeAll'" @close="closeFormDialog" />
			<MassageIntakeForm v-if="selectedForm === 'massageIntake'" @close="closeFormDialog" />
		</v-dialog> -->
</template>


<script>
import { ref } from 'vue';
export default {
	name: 'components-home-steps',
	setup() {

		const intakeDialog = ref(false);
		const selectedIntake = ref('intakeAll');
		const toggleIntakeDialog = (string) => {
			selectedIntake.value = string || '';
			intakeDialog.value = !intakeDialog.value;
		}
		return {
			intakeDialog,
			selectedIntake,
			toggleIntakeDialog,
		}
	}
}
</script>

<style>

</style>