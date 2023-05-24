<script>
	let gpa = null;
	let modalText = 'Enter your GPA first, genius 🤦‍♀️';

	function checkGPA() {
        gpa = parseFloat(gpa);

        if (isNaN(gpa)) {
            modalText = 'Last I checked, that was not a number 🤔';
        } else if (gpa === null || gpa === '') {
			modalText = 'Enter your GPA first, genius 🤦‍♀️';
		} else if (gpa > 4) {
			modalText = 'Allah se daro';
		} else if (gpa < 0) {
			modalText = 'Bhai please';
		} else if (gpa >= 3.595) {
			// Open modal
			modalText = "Yes, you'll get DHL, nerd 👩‍🔬";
		} else {
			modalText = "Won't get DHL, git gud 🤡";
		}
	}
</script>

<!-- Put this part before </body> tag -->
<input type="checkbox" id="my-modal-6" class="modal-toggle" />
<div class="modal modal-bottom sm:modal-middle">
	<div class="modal-box">
		<p class="py-4">
			{modalText}
		</p>
		<div class="modal-action">
			<label for="my-modal-6" class="btn">Yay!</label>
		</div>
	</div>
</div>
<div
	class="min-h-screen bg-neutral-900 text-white flex flex-col gap-y-10 items-center justify-center p-5 text-center"
>
	<h1 class="text-4xl font-bold w-full">What is your current GPA?</h1>

	<input
		type="text"
		class="bg-neutral-800 p-5 border-red-700 border-2 rounded-lg focus:outline-none"
		bind:value={gpa}
	/>
	<!-- The button to open modal -->
	<label for="my-modal-6" class="btn" on:click={checkGPA}>Check</label>
</div>
