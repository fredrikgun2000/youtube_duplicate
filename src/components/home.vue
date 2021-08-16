<template>
	<div>
		<div class="container-fluid pt-2">
			<div class="row">
				<div class="col-lg-2">
					<div class="row">
						<div class="col-lg-2">
							<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-house-door-fill" viewBox="0 0 16 16">
							<path d="M6.5 14.5v-3.505c0-.245.25-.495.5-.495h2c.25 0 .5.25.5.5v3.5a.5.5 0 0 0 .5.5h4a.5.5 0 0 0 .5-.5v-7a.5.5 0 0 0-.146-.354L13 5.793V2.5a.5.5 0 0 0-.5-.5h-1a.5.5 0 0 0-.5.5v1.293L8.354 1.146a.5.5 0 0 0-.708 0l-6 6A.5.5 0 0 0 1.5 7.5v7a.5.5 0 0 0 .5.5h4a.5.5 0 0 0 .5-.5z"/>
							</svg>
						</div>
						<div class="col-lg-10" style="margin-top: 3px;"> Beranda</div>
					</div>
				</div>
				<div class="col-lg-10">
					<div class="row">
						<div class="col-lg-12"></div>
					</div>
					<div class="row">
						<div class="col-lg-3 px-1" v-for="d in data" v-bind:key = "d.id">
							<div class="row">
								<div class="col-lg-12">
									<div class="row">
										<div class="col-lg-12">
											<img v-bind:src="img" style="width: 100%;">
										</div>
									</div>
									<div class="row">
										<div class="col-lg-12">
											<h6>{{d.snippet.title}}</h6>
										</div>
									</div>
									<div class="row">
										<div class="col-lg-12">
											{{d.snippet.channelTitle}}
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import axios from 'axios'
	export default{
		data: function () {
		    return {
		    	data : undefined,
		    	img : 'https://i.ytimg.com/vi/XgtAmNJWYWc/default.jpg'
		    }
		},
		created: function () {
			this.Show();
		},
		methods: {
			Show:function(){
				axios({
				  method: 'get',
				  url: 'https://www.googleapis.com/youtube/v3/search?part=snippet&q=Pandji Pragiwaksono&key=AIzaSyD5TxLOnebJ5aUiBrNyuV4Y_f7aRk4WUok',
				}).then(
					(response) => {
						this.data = response.data.items;
						
				})
			}
		}
	}
</script>