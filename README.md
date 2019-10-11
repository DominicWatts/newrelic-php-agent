# newrelic-php-agent

New Relic php agent for building docker images.  Fixed version so image builds will not fail. Not relying on third party archive site.

Inside `Dockerfile`

```
# Install New Relic
RUN \
  curl -L https://github.com/DominicWatts/newrelic-php-agent/raw/5-9.2.0.247/newrelic-php5-9.2.0.247-linux.tar.gz  | tar -C /tmp -zx && \
   export NR_INSTALL_USE_CP_NOT_LN=1 && \
    export NR_INSTALL_SILENT=1 && \
     /tmp/newrelic-php5-*/newrelic-install install && \
      rm -rf /tmp/newrelic-php5-* /tmp/nrinstall* 
```
