<template>
  	<q-page padding>
  		<div style="max-width: 350px">
	  		<q-list 
	  			v-for="folder in folders"
	        	:key="folder.id"
	  			bordered
	  			class="bg-teal-1">
		    	<q-expansion-item 
		    		dense 
		    		expand-separator>
			        <template v-slot:header>
			          	<q-item-section avatar>
			          		<div class="row">
								<q-checkbox 
								  	dense 
								 	v-model="check1" 
								   	class="q-mr-sm" />
				            	<q-icon 
									name="folder" 
									color="primary" 
									size="20px" />
							</div>
			          	</q-item-section>

			          	<q-item-section>
			            	{{ folder.name }}
			          	</q-item-section>

			          	<q-item-section side>
							<div class="row items-center">
							  	<q-btn 
							      	@click.stop=""
							     	size="10px" 
							       	dense 
							      	flat 
							      	round
							       	icon="more_horiz"
							      	color="primary">
									<q-menu
										self="top middle"
										:offset="[-10, 5]"
										transition-show="scale"
										transition-hide="scale">
										<q-list class="bg-teal-1" style="min-width: 100px">
											<q-item dense clickable>
											 	<div class="row items-center">
													<q-icon 
												     	name="add" 
												      	color="primary" 
												      	size="20px"
												    	class="q-mr-sm" />
													<q-item-section>Add Item</q-item-section>
												</div>
											</q-item>

											<q-separator />

											<q-item dense clickable>
											  	<div class="row items-center">
												 	<q-icon 
												     	name="edit" 
												    	color="primary" 
												     	size="20px"
												     	class="q-mr-sm" />
												   	<q-item-section>Edit Folder</q-item-section>
												</div>
											</q-item>
											
											<q-separator />
											
											<q-item dense clickable>
											  	<div class="row items-center">
												  	<q-icon 
												  		name="delete" 
												       	color="primary" 
												      	size="20px"
												     	class="q-mr-sm" />
												   	<q-item-section>Delete Folder</q-item-section>
												</div>
											</q-item>
										</q-list>
									</q-menu>
								</q-btn>
							</div>
						</q-item-section>
		        	</template>
		        	<q-card>
					 	<q-item 
					 		dense
							v-ripple
							clickable
							:inset-level="0.5">
					 		<q-checkbox 
					 			dense
							   	v-model="check1"
							   	class="q-mr-sm" />
					 		<q-item-section>{{ folder.children.name }}</q-item-section>
					 		<div class="row items-center">
								<q-btn 
									@click.stop=""
								 	size="10px" 
								  	dense 
								  	flat 
								 	round
								  	icon="more_horiz"
								  	color="primary">
									<q-menu
										self="top middle"
										:offset="[25, 5]"
										transition-show="scale"
										transition-hide="scale">
										<q-list class="bg-teal-1" style="min-width: 100px">
											<q-separator />
														
											<q-item dense clickable>
												<div class="row items-center">
													<q-icon 
														name="edit" 
														color="primary" 
														size="20px"
														class="q-mr-sm" />
														<q-item-section>Edit Item</q-item-section>
												</div>
											</q-item>
													
											<q-separator />
													         	
											<q-item dense clickable>
												<div class="row items-center">
													<q-icon 
														name="delete" 
														color="primary" 
														size="20px"
														class="q-mr-sm" />
													<q-item-section>Delete Item</q-item-section>
												</div>
											</q-item>
										</q-list>
									</q-menu>
								</q-btn>
							</div>
					 	</q-item>
				  	</q-card>
	    		</q-expansion-item>
	    	</q-list>
	    </div>
  	</q-page>
</template>

<script>
	export default {
		data () {
			return {
				check1: false,
				folders: [
					{
						id: 1,
						name: 'coatings',
						children: [
							{
								id: 1.1,
								name: 'interior coatings'
							},
							{
								id: 1.2,
								name: 'exterior coatings'
							},
							{
								id: 1.3,
								name: 'auto finish'
							}
						]
					},
					{
						id: 2,
						name: 'ceramics',
						children: [
							{
								id: 2.1,
								name: 'floor tiles'
							},
							{
								id: 2.2,
								name: 'wall tiles'
							},
							{
								id: 2.3,
								name: 'anti-slippery tiles'
							}
						]
					}
				]
			}
		}
	}
</script>

<style>
	
</style>
