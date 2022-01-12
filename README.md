# ion-compose
a series of docker-compose.yml for pion/ion

signal和sfu启动前需先配置nats服务地址`${NATS_ADDR}`和端口号`${NATS_PORT}`。

sfu启动前需先配置`sfu.toml`中`[webrtc.candidates]`下的`nat1to1`。

web启动前需先配置signal服务地址`${SIGNAL_ADDR}`和端口号`${SIGNAL_PORT}`。

带tls的web-scure启动前除了需先配置signal服务地址`${SIGNAL_ADDR}`和端口号`${SIGNAL_PORT}`外，还需配置tls证书用的URL`${WWW_URL}`和Email`${ADMIN_EMAIL}`。