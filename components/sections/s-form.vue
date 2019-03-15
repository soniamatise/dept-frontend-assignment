<template>
	<section class="section section__form-section form-section">
		<div class="form-section__title">
			<h3>QUESTION? WE ARE HERE  TO HELP!</h3>
		</div>
		<div class="form-section__container">
			<form
				id="app"
				action="https://vuejs.org/"
				method="post"
				@submit="checkForm"
			>
				<div v-if="errors.length">
					<ul>
						<li v-for="(error,index) in errors" :key="index">{{ error }}</li>
					</ul>
				</div>
				<ul class="form-section__inner">
					<li class="form-section__field">
						<label class="form-section__label" for="name">Name</label>
						<input
							id="name"
							v-model="name"
							type="text"
							name="name"
						>
					</li>
					<li class="form-section__field">
						<label class="form-section__label" for="email">Email</label>
						<input
							id="email"
							v-model="email"
							type="email"
							name="email"
						>
					</li>
					<li class="form-section__field last-label">
						<label class="form-section__label" for="name">Message</label>
						<textarea
							id="message"
							v-model="message"
							type="text"
							name="message"
						/>
					</li>
					
				</ul>
				<button 
					class="button button--full-blue form-section__button"
					type="submit"
					value="Submit">
					Send
				</button>
			</form>
		</div>
	</section>
</template>

<script>
export default {
	data() {
		return {
			errors: [],
			name: null,
			email: null,
			message: null
		}
	},
	methods:{
		checkForm: function (e) {
			if (this.name && this.email && this.message) {
				return true;
			}

			this.errors = [];

			if (!this.name) {
				this.errors.push('Name required.');
			}
			if (!this.email) {
				this.errors.push('Email required.');
			}
			if (!this.message) {
				this.errors.push('Message required.');
			}

			e.preventDefault();
		}
	}
};
</script>

<style lang="scss">
@import '~tools';

.form-section {
	display: flex;
	flex-wrap: wrap;
	flex-direction: row;
	@media #{$large-down} {
		flex-direction: column;
	}

	&__title {
		width: 20%;
		padding-right: 50px;
		@media #{$large-down} {
			padding: 0;
			width: 100%;
		}
	}
	&__container {
		width: 60%;
		@media #{$large-down} {
			width: 100%;
			padding-top: 30px; 
		}
	}
	&__inner {
		display: flex;
		flex-wrap: wrap;
		list-style-type: none;
		padding: 0 25px;
		@media #{$large-down} {
			padding: 0;
		}
	}
	&__field {
		position: relative;
		margin-bottom: 50px;
		flex-basis: 50%;
		padding-right: 25px;
		padding-left: 25px;
		@media #{$large-down} {
			flex-basis: 100%;
			padding: 0;
		}

		&.last-label {
			margin-bottom: 30px;
		}
	}
	&__label {
		display: block;
	}
	&__button {
		margin: 0 50px;
		@media #{$large-down} {
			margin: 0;
		}
	}
}

</style>