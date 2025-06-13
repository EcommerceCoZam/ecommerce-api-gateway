@Library('microservice-pipeline') _

def config = [
    serviceName: 'api-gateway',
    hasUnitTests: !['cloud-config', 'api-gateway', 'service-discovery'].contains('api-gateway'),
    buildTool: 'maven', 
    dockerContext: '.',
    healthCheckPort: getHealthCheckPort('api-gateway')
]

microservicePipeline(config)

def getHealthCheckPort(serviceName) {
    def ports = [
        'api-gateway': 8080,
        'service-discovery': 8761,
        'cloud-config': 9296,
        'user-service': 8700,
        'product-service': 8500,
        'order-service': 8300,
        'payment-service': 8400,
        'shipping-service': 8600,
        'favourite-service': 8800,
        'proxy-client': 8900
    ]
    return ports[serviceName] ?: 8080
}