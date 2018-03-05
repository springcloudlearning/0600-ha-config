HA Config

build a high available config server. if we have lots of service exists, and each of them load properties from config server 
it will cause high overhead and what if the config server down?? so we need to build HA config server

Config server need to register to Eureka server

register config server to eureka server
@SpringBootApplication
@EnableDiscoveryClient   <-- register to eureka server
@EnableConfigServer           

ensure the application name are same between lots of config server


from client side perspective. we need to name the server name instead of hard code url
spring.application.name=service-user
spring.cloud.config.label=master
spring.cloud.config.profile=dev
spring.cloud.config.discovery.enabled=true
spring.cloud.config.discovery.serviceId=config-server
server.port=8762
eureka.client.service-url.defaultZone: http://localhost:8761/eurek








