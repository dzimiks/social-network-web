<template>
	<div class="container">
		<div class="row my-4">
			<div class="col-12">
				<h3 class="text-center">Social Network</h3>
			</div>
		</div>

		<div class="row">
			<div class="col-6 mx-auto">
				<form>
					<div class="p-1 bg-light rounded rounded-pill shadow-sm mb-4">
						<div class="input-group">
							<div class="input-group-prepend">
								<button id="button-addon2" type="submit" class="btn btn-link text-warning">
									<i class="fa fa-search"></i>
								</button>
							</div>
							<input
									v-model="search"
									type="text"
									placeholder="Search..."
									aria-describedby="button-addon2"
									class="form-control border-0 bg-light">
						</div>
					</div>
				</form>
			</div>
		</div>

		<div class="row">
			<div class="col-sm-4 col-12" v-for="user in filteredUsers" v-bind:key="user.id">
				<div class="card">
					<div class="card-header-text">
						<h3 class="m-0">{{ user.id }}</h3>
					</div>
					<div class="card-body">
						<h5 class="card-title">{{ user.firstName }} {{ user.surname }}</h5>
						<h6 class="card-subtitle mb-2 text-muted">{{ user.age }} | {{ user.gender }}</h6>
						<div class="card-text">
							<p class="d-inline">Friends:</p>
							<p class="d-inline" v-for="friend in user.friends" v-bind:key="friend-user.id">
								{{ friend }}
							</p>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import data from '../../public/db/data';

	export default {
		name: 'MainView',

		data() {
			return {
				data,
				search: '',
			};
		},

		computed: {
			filteredUsers() {
				return this.data.filter(user => {
					return user.firstName.toLowerCase().includes(this.search.toLowerCase())
				})
			}
		}
	}
</script>

<style scoped>
	.form-control:focus {
		box-shadow: none;
	}

	.form-control-underlined {
		border-width: 0;
		border-bottom-width: 1px;
		border-radius: 0;
		padding-left: 0;
	}

	.form-control::placeholder {
		font-size: 0.95rem;
		color: #aaa;
		font-style: italic;
	}
</style>
