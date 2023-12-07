<script>
  import { T, useFrame } from '@threlte/core'
  // import { Fog } from 'threlte'

  let rotation = 0
  useFrame(() => {
    rotation += 0.01
  })

  import {
    BoxGeometry,
    Color,
    IcosahedronGeometry,
    MeshStandardMaterial,
    TorusKnotGeometry
  } from 'three'

</script>

<!-- <Fog color={'#dddddd'} /> -->




<T.Group rotation.y={rotation}>
  <T.PerspectiveCamera
    makeDefault
    position={[0, 0, 10]}
    fov={10}
    on:create={({ ref }) => {
      ref.lookAt(0, 1, 0)
    }}
  />
</T.Group>


<T.DirectionalLight
  intensity={0.8}
  position.x={5}
  position.y={12}
/>
<T.AmbientLight intensity={0.2} />

<!-- <T.Mesh
  position.y={1}
  position.z={0}
>
  <T.CubeGeometry />
  <T.MeshStandardMaterial color="blue" />
</T.Mesh> -->

<T.Mesh
position.y={1}
position.z={0}
scale={1}
>
  <T.BoxGeometry />
  <T.MeshBasicMaterial color="blue" />
</T.Mesh>

<T.Mesh
  position.y={1}
  position.x={1}
  position.z={4}
>
  <T.SphereGeometry />
  <T.MeshStandardMaterial color="blue" />
  <T.MeshStandardMaterial color="purple" />

</T.Mesh>




