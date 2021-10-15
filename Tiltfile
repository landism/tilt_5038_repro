# docker_build('sprkl/common', './common/',
  # build_args={'node_env' : 'development'},
  # live_update=[
    # sync('protos', '/opt/common/protos'),
  # ]
# )
# 
# images = ['nodejs', 'nest']
# 
# for service in images:
  # image='sprkl/{}'.format(service)
  # path='./{}'.format(service)
  # docker_build(image, path,
    # build_args={'node_env' : 'development'},
    # live_update=[
      # sync(service, '/opt/code'),
# 
      # run('cd /opt/code && npm install' ,
        # trigger=['./{}/package.json'.format(service)])
    # ]
    # )

# load('ext://namespace', 'namespace_create', 'namespace_inject')
# namespace_create('observability')

observability_yaml = helm(
  'helm/local/observability',

  # The release name, equivalent to helm --name
  name='stam',

  # The namespace to install in, equivalent to helm --namespace
#  namespace='observability',

  )


app_yaml = helm(
  'helm/local/',

  # The release name, equivalent to helm --name
  name='main',

  # The namespace to install in, equivalent to helm --namespace
  # namespace='my-namespace',

  # The values file to substitute into the chart.
  # values=['helm/local/values.yaml'],

  # Values to set from the command-line
  # set=['service.port=1234', 'ingress.enabled=true']
  )
#k8s_yaml([ app_yaml, observability_yaml ])
k8s_yaml([ observability_yaml, app_yaml ])
#k8s_yaml(observability_yaml)

