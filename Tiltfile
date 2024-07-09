# Build
custom_build(
    # Name of the container image
    ref = 'catalog-service',
    # Command to build the container image
    command = 'gradle bootBuildImage --imageName $EXPECTED_REF -g /mnt/d/data/gradle/ubuntu',
    # Files to watch that trigger a new build
    deps = ['build.gradle','src']
)

# Deploy
k8s_yaml(['k8s/deployment.yml','k8s/service.yml'])

# Manage
k8s_resource('catalog-service',port_forwards=['9001'])