<script lang="ts">
  let className:string = '';
  export { className as class };
	import { onMount } from 'svelte';
	import * as THREE from 'three';
	let canvas: HTMLCanvasElement;
	const scene = new THREE.Scene();
	onMount(() => {
		let width = canvas.clientWidth;
		let height = canvas.clientHeight;
		// const camera = new THREE.OrthographicCamera(0, 1, 1, -1, -0.001, 0);
		// camera.position.z = 0.5;
		// camera.rotateY(Math.PI/2);
		const camera = new THREE.OrthographicCamera(0, 1, 1, -1, -10, 10);
		const renderer = new THREE.WebGLRenderer({ antialias: true, canvas: canvas, alpha: true });


		let xScale = { value: 1.0 };
		let time_u = { value: 0.0 };

    function resize() {
      width = canvas.clientWidth;
      height = canvas.clientHeight;
      xScale.value = Math.min(width/1000,1);
      renderer.setSize(width, height, false);
    }

		window.addEventListener('resize', () => {
      resize();
			console.log('resize');
		});
    resize();



		function generatePoints() {
			const points = [];
			for (let x = 0; x <= 1; x += 1 / width) {
				points.push(x, 0, 0);
			}
			return new Float32Array(points);
		}

		// vertex shader code
		const vertexShader = `
      const float PI = radians(180.0);
      uniform float time;

      uniform float morph;
      uniform float xScale;
      varying float vPosition;

      void main() {
        vec3 pos = position;
        vPosition = position.x;
        float base_x = position.x*PI*2.0*xScale;
        float r = (sin(base_x+time/PI)*morph + 
                cos(base_x*3.0+time/0.8/PI)*(1.0-morph)/1.5
                )/2.0-0.1*pos.x; 
        float angle = position.x*PI*2.0+morph*PI;
        pos.z = cos(angle)*r;
        pos.y = sin(angle)*r-0.2*pos.x+0.1;
        gl_Position = projectionMatrix * modelViewMatrix * vec4(pos, 1.0);
      }
    `;

		// fragment shader code
		const fragmentShader = `
      varying float vPosition;
      vec3 rgb(int r, int g, int b){
        return vec3(float(r)/255.0, float(g)/255.0, float(b)/255.0);
      }

      void main() {
        vec3 color1 = rgb(245, 194, 231);
        vec3 color2 = rgb(137, 180, 250);
        gl_FragColor = vec4(color1 * vPosition + color2 * (1.0 - vPosition), 1.0);
      }
    `;

		const geometry = new THREE.BufferGeometry();
		geometry.setAttribute('position', new THREE.BufferAttribute(generatePoints(), 3));

		const nLines = 40;
		// create a material for the mesh using the shader
		for (let i = 0; i < nLines; i++) {
			const material = new THREE.ShaderMaterial({
				uniforms: {
					morph: { value: i / nLines },
					time: time_u,
          xScale: xScale
				},
				vertexShader: vertexShader,
				fragmentShader: fragmentShader
			});
			const mesh = new THREE.Line(geometry, material);
			scene.add(mesh);
		}

		// create a mesh with the geometry and material, and add it to the scene
		let clock = new THREE.Clock();
		clock.start();
		renderer.setAnimationLoop(() => {
			time_u.value = clock.getElapsedTime();
			renderer.render(scene, camera);
		});
	});
</script>

<canvas class={"w-full h-full "+className} bind:this={canvas} />
