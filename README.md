# Fake ElastiCache

A local (fake) instance of ElastiCache, backed by memcached, for local
development.

Inspired heavily by https://github.com/stevenjack/fake_elasticache ...

https://hub.docker.com/r/dazoakley/fake-elasticache/

## Usage

```
docker build -t fake-elasticache .
docker run -d -p 11211:11211 --name=memcached memcached
docker run --rm -it -p 11212:11212 --link memcached fake-elasticache
```

You will now be able to point your ElastiCache endpoint to http://localhost:11212
