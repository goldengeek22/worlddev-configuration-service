#BUILD
custom_build(
    ref = worlddev-configuration-service,
    command='./gradlew bootBuildImage --imageName $EXPECTED_REF',
    deps=['build.gradle', 'src']
)

#DEPLOY
k8s_yaml(['k8s/service.yml','k8s/deployment.yml'])

#MANAGE
k8s_resource('worlddev-configuration-service', port_forwards=['7000'])
