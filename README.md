# **photon-repository-tasklist**

- [x] intergrate kafka with spring bus

- [x] spring cloud config password encrypt
> keytool -genkeypair -alias config-server-key -keyalg RSA -keysize 4096 -sigalg SHA512withRSA -dname 'CN=Config Server,OU=Spring Cloud,O=Baeldung' -keypass my-k34-s3cr3t -keystore config-server.jks  -storepass my-s70r3-s3cr3t
- [x] jasypt encrypt

- [ ] docker-compose with nginx and springboot

- [ ] intergate mongoDB and redis

- [ ] spring start gateway & cloud stream

- [ ] use RPC backend service communicate

- [ ] start learning netty




>Your link is working, but you're on separate networks inside of Docker. From the docker-compose.yml docs:
>
>Note: If you’re using the version 2 file format, the externally-created containers must be connected to at least one of the same networks as the service which is linking to them.
>
>To solve this, you can create your own network:
>
>docker network create dbnet
>docker network connect dbnet mysql
