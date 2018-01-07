<template>
<div v-if="(!lockedOut || manuallyUnlocked)">
	<div class="row">
		<div class="col-md-4">
			<cue-button :cue="1" name="House Full" type="House Lights" color="bg-yellow"></cue-button>
			<cue-button :cue="2" name="House Off" type="House Lights" color="bg-red" icon="fa-power-off"></cue-button>
		</div>
	</div>
</div>
<div v-else>
	<div class="lockscreen-wrapper">
		<div class="lockscreen-logo">Auditorium Lighting</div>

		<div class="text-center" style="margin-bottom: 24px;">
			Loading scenes...
		</div>
		<p class="text-center" style="font-size: 36px; margin-bottom: 24px;">
			<i class="fa fa-refresh fa-spin"></i>
		</p>
	</div>

</div>
</div>
</template>

<script>
module.exports = {
	computed: {
		cuelistsLoaded: function() {
			return this.$parent.$data.cuelistsLoaded;
		},
		lockedOut: function() {
			return this.$parent.$data.lockedOut;
		},
		manuallyUnlocked: function() {
			return this.$parent.$data.manuallyUnlocked;
		}
	}
}
</script>