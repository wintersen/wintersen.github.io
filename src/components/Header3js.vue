<template>
<div id="canvas"></div>
</template>

<script>
import * as Three from 'three'

export default {
  name: "Header3js",
  data(){
    return{
      camera: null,
      scene: null,
      renderer: null,
      mesh: null
    }
  },
  methods: {
    init: function(){
let canvas = document.getElementById('canvas');

        this.camera = new Three.PerspectiveCamera(70, 1920/1080, 0.01, 10);
        this.camera.position.z = 1;

        this.scene = new Three.Scene();

        let geometry = new Three.BoxGeometry(0.2, 0.2, 0.2);
        let material = new Three.MeshNormalMaterial();

        this.mesh = new Three.Mesh(geometry, material);
        this.scene.add(this.mesh);

        this.renderer = new Three.WebGLRenderer({antialias: true});
        this.renderer.setSize(1920, 1080);
        canvas.appendChild(this.renderer.domElement);

      // let canvas = document.getElementById('canvas');
      // const left= 0;
      // const right= 1920;
      // const top = 0;
      // const bottom = 1080;
      // const near = -1;
      // const far = 1;
      // this.camera = new THREE.OrthographicCamera(left, right, top, bottom, near, far);
      // this.camera.zoom = 1;

      // this.scene = new THREE.Scene();
      // this.scene.background= new THREE.Color('black');

      // const loader = new THREE.TextureLoader();
      // const textures =[
      //   loader.load('./assets/threejs/test1.png'),
      //   loader.load('./assets/threejs/test2.png')
      // ];

      // const planeSize = 256;
      // const planeGeo = new THREE.PlaneBufferGeometry(planeSize, planeSize);
      // const planes = textures.map((texture)=>{
      //   const planePivot = new THREE.Object3D();
      //   scene.add(planePivot);
      //   texture.magFilter = THREE.NearestFilter;
      //   const planeMat = new THREE.MeshBasicMaterial({
      //     map: texture,
      //     side: THREE.DoubleSide
      //   });
      // })
    },
    animate: function() {
        requestAnimationFrame(this.animate);
        this.mesh.rotation.x += 0.01;
        this.mesh.rotation.y += 0.02;
        this.renderer.render(this.scene, this.camera);
    }
  },
  mounted(){
    this.init();
    this.animate();
  }
}
</script>