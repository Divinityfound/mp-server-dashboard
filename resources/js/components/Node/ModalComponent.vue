<template>
	<div>
		<div class="modal fade show" id="itemModal" tabindex="-1" role="dialog" aria-labelledby="itemModalLabel" aria-hidden="true"  style="display: block;">
			<div class="modal-dialog" role="document">
				<div class="modal-content">
					<div class="modal-header">
						<h4 class="modal-title" id="itemModalLabel">{{ params.title }}</h4>
						<button type="button" class="close" aria-label="Close" @click="$emit('close')">
							<span aria-hidden="true">&times;</span>
						</button>
					</div>
					<div class="modal-body">
						<NodeSetComponent v-if='params.modal == "CreateNodeServer"' @handleModal='handleModal' @close='$emit("close")' :params='params.args' />
					</div>
					<div class="modal-footer">
						<button type="button" class="btn btn-secondary" @click="$emit('close')">Close</button>
					</div>
				</div>
			</div>
		</div>
		<div class="modal-backdrop fade show"></div>
		<div class="modal-backdrop fade show"></div>
	</div>
</template>


<script>
	import NodeSetComponent from './NodeSetComponent';
	export default {
		name      : "modal-component",
		props     : [
			'params'
		],
		components: { 
			NodeSetComponent
		},
		created()   {},
		data()      { return {} },
		computed  : {},
		methods   : {
			handleModal(args) {
				this.$emit('handleModal', args);
			}
		},
		watch     : {}
	};
</script>

<style scoped></style>


