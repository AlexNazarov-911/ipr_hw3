## На 4 балла
2026-11-22 19:44:43,490 listening port=8000 storage=sqlite
2026-11-22 19:45:24,548 http 192.168.65.1 "GET / HTTP/1.1" 200 -
2026-11-22 19:46:05,962 http 192.168.65.1 "GET / HTTP/1.1" 200 -
2026-11-22 19:46:12,835 http 192.168.65.1 "POST /increment HTTP/1.1" 200 -

# На 6
Раз:

{"greeting": "compose alhamdulilla", "count": 1, "hostname": "ca64e0a8a26d", "storage": "sqlite"}%  

Два:

{"greeting": "compose alhamdulilla", "count": 1, "hostname": "f4fe534b84ae", "storage": "sqlite"}%   


# На 8

До down "count": 2
После "count": 2



curl -i http://localhost:8080/healthz
HTTP/1.0 200 OK

curl -i http://localhost:8080/readyz
HTTP/1.0 503

curl -i -X POST http://localhost:8080/increment
HTTP/1.0 503



curl http://localhost:8080/
{"greeting": "compose alhamdulilla", "count": 2, "hostname": "3fa77e30a4a1", "storage": "redis"}%                                  

curl -X POST http://localhost:8080/increment
{"greeting": "compose alhamdulilla", "count": 3, "hostname": "3fa77e30a4a1", "storage": "redis"}%                                     
