# envoy-practise

For helping me get my head around envoy proxy configuration with static resources.


#Requirements

- helm
- Connected kubernetes cluster (I used GKE)

## Install envoy

`helm upgrade --install envoy stable/envoy -f values.yaml`

## Install our sample microservice

`helm upgrade --install my-release hello-go`


## Testing


`curl localhost:10000/service/1 -v`

Will yield...

```
curl localhost:10000/service/1 -v
*   Trying ::1...
* TCP_NODELAY set
* Connected to localhost (::1) port 10000 (#0)
> GET /service/1 HTTP/1.1
> Host: localhost:10000
> User-Agent: curl/7.54.0
> Accept: */*
>
< HTTP/1.1 200 OK
< date: Fri, 06 Sep 2019 16:21:41 GMT
< content-length: 21
< content-type: text/plain; charset=utf-8
< x-envoy-upstream-service-time: 1
< server: envoy
<
* Connection #0 to host localhost left intact
Hello from 10.44.1.15%
```
