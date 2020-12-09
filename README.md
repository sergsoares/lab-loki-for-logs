# lab-loki-for-logs

Lab project to test loki functions.

```
# Start docker-compose
$ docker-compose up -d
```

Then access http://localhost:3000/explore using default user and password (admin/admin)

### Tips for queries

|= is a contains
!= is not contains
|~ Match Regex
!~ Doesn't match regex

```
# Simples query with filter
{compose_service="mario-server"} |= "-Djava" != "protocol"

#Getting logs from method
{compose_service="apache-logs"} | json | method="DELETE"
```

## References

- https://blog.ruanbekker.com/blog/2020/08/13/getting-started-on-logging-with-loki-using-docker/
- https://github.com/ruanbekker/loki-docker-nginx-example
- https://grafana.com/docs/loki/latest/logql/
- https://xuwenyihust.github.io/lunaticlog/lunaticlog/html/
- https://pypi.org/project/log-generator/
- https://hub.docker.com/r/mingrammer/flog
- https://github.com/chentex/random-logger