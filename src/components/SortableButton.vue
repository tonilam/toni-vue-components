<template>
	<span @click="toggleSort" style="cursor: pointer;">
		<font-awesome-icon :icon="sortClass" :class="{'text-black-50': value.field != field}" ></font-awesome-icon>
	</span>
</template>

<script>
	import { faSort, faSortUp, faSortDown } from '@fortawesome/free-solid-svg-icons'
	export default {
		name: "SortableButton",
		props: {
			field: {required: true},
			value: {required: true}
		},
		data() {
			return {
				myIcon: faSort
			}
		},
		computed: {
			sortClass: function() {
				switch (this.value.order) {
					case 'asc': return faSortUp;
					case 'desc': return faSortDown;
					default: return faSort;
				}
			}
		},
		methods: {
			toggleSort() {
				let state = 'asc';
				if (this.value.field == this.field) {
					switch (this.value.order) {
						case 'asc':
							state = 'desc';
							break;
						case 'desc':
							state = null;
							break;
						default:
							state = 'asc';
					}
				}
				this.$emit('input', {
					field: state? this.field: null,
					order: state
				});
			}
		}
	}
</script>