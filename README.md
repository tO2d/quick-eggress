# quick-eggress*

*http:/www.bar.com/foo


<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<style>
			body {
				background-color: #ffffff;
				margin: 0;
				overflow: hidden;
			}
		</style>
	</head>
	<body>
		<script src="http://cdnjs.cloudflare.com/ajax/libs/three.js/r57/three.min.js"></script>
		<script>

			var camera, scene, renderer;
			var geometry, material, mesh;

			function init() {

				renderer = new THREE.CanvasRenderer();
				renderer.setSize( window.innerWidth, window.innerHeight );
				document.body.appendChild( renderer.domElement );

				camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 10 );
				camera.position.z = 3;

				scene = new THREE.Scene();

				geometry = new THREE.CubeGeometry( 1, 1, 1 );
				material = new THREE.MeshBasicMaterial( { color: 0x000000, wireframe: true, wireframeLinewidth: 2 } );

				mesh = new THREE.Mesh( geometry, material );
				scene.add( mesh );

			}

			function animate() {

				requestAnimationFrame( animate );

				mesh.rotation.x = Date.now() * 0.0005;
				mesh.rotation.y = Date.now() * 0.001;

				renderer.render( scene, camera );

			}

			init();
			animate();

		</script>
	</body>
</html>
