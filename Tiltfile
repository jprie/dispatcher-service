# Build
custom_build(
    # name of the container image
    ref = 'dispatcher-service',
    # command to build the container image
    command = './gradlew bootBuildImage --imageName $EXPECTED_REF',
    # Files to watch that trigger a new build
    deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml([kustomize('k8s')])

# Manage
k8s_resource('dispatcher-service', port_forwards=['9003'])
