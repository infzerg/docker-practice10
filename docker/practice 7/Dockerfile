FROM mostafamoradian/xk6-kafka:latest


USER root


RUN apk add --no-cache nano && addgroup -g 1001 -S appgroup && adduser -u 1001 -S -G appgroup appuser


USER appuser


ENTRYPOINT ["/bin/sh"]


CMD []
