<script lang="ts">
  import { T } from '@threlte/core';
  import { Environment, GLTF, OrbitControls } from '@threlte/extras';
</script>

<!-- files に対象ファイルのパスを指定。今回は Three.js のサンプルから直接ロード -->
<Environment
	files={'https://raw.githubusercontent.com/mrdoob/three.js/dev/examples/textures/equirectangular/venice_sunset_1k.hdr'}
	isBackground={true}
/>

<T.PerspectiveCamera
  makeDefault
  position={[-10, 10, 10]}
  fov={15}
>
  <OrbitControls
    autoRotate
    enableZoom={false}
    enableDamping
    autoRotateSpeed={0.5}
    target.y={1.5}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={0.8}
  position.x={5}
  position.y={10}
/>
<T.AmbientLight intensity={0.2} />

<T.Mesh position={[0, 1.3, 0]}>	
  <GLTF url="https://raw.githubusercontent.com/KhronosGroup/glTF-Sample-Models/main/2.0/DamagedHelmet/glTF/DamagedHelmet.gltf"/>
</T.Mesh>
