<script lang="ts">
  import { T, TransformableObject, useFrame } from '@threlte/core'
  import { GLTF } from '@threlte/extras'
  import { DEG2RAD } from 'three/src/math/MathUtils'

  let rotation = 0
  useFrame(() => rotation += 0.015);
</script>

<T.Group rotation.y={rotation}>
  <T.OrthographicCamera zoom={10} near={-100} let:ref={cam} position={[0, 5, 10]} makeDefault>
    <TransformableObject object={cam} lookAt={{ y: 2 }} />
  </T.OrthographicCamera>
</T.Group>

<GLTF castShadow receiveShadow url={'/models/dingus_the_cat.glb'} interactive />

<T.Mesh receiveShadow rotation.x={DEG2RAD * -90}>
  <T.CircleGeometry args={[32, 60]} />
  <T.MeshStandardMaterial>
    <T.Color args={['#070708']} attach="color" />
  </T.MeshStandardMaterial>
</T.Mesh>

<T.DirectionalLight position={[3, 10, 10]} castShadow />
<T.DirectionalLight position={[-3, 10, -10]} intensity={0.2} />
<T.AmbientLight intensity={0.5} />
