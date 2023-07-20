# LogCollectors

## Log[Frameworks.md](Frameworks.md)stash vs Fluentd

**Docker support:** Docker provides an in-built fluentd logging driver. The logging driver sends container logs 
to the fluentd collector as structured log data. In the case of Logstash, an extra agent (**filebeat**) is required 
on the container to push logs to Logstash. So if you're running your applications with Docker, FluentD is a more natural choice. Logs can be directly shipped to FluentD service from STDOUT. FluentD makes the overall Docker logging architecture less complex, and less risky.

On the other hand, Logstash works well with Elasticsearch and Kibana -> part of ELK stack