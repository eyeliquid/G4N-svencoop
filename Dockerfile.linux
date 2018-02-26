# escape=`

FROM lacledeslan/gamesvr-svencoop

HEALTHCHECK NONE

ARG BUILDNODE="unspecified"
ARG SOURCE_COMMIT

LABEL maintainer="Laclede's LAN <contact @lacledeslan.com>" `
      com.lacledeslan.build-node=$BUILDNODE `
      org.label-schema.schema-version="1.0" `
      org.label-schema.url="https://github.com/LacledesLAN/README.1ST" `
      org.label-schema.vcs-ref=$SOURCE_COMMIT `
      org.label-schema.vendor="Laclede's LAN" `
      org.label-schema.description="LL Half-Life 2 Deathmatch Dedicated Freeplay Server" `
      org.label-schema.vcs-url="https://github.com/LacledesLAN/gamesvr-hl2dm"

COPY --chown=SvenCoOp:root ./dist /app/svencoop/

COPY --chown=SvenCoOp:root ./ll-tests/*.sh /app/ll-tests

# UPDATE USERNAME & ensure permissions
RUN usermod -l SvenCoOpFreeplay SvenCoOp &&`
    chmod +x /app/ll-tests/*.sh;

USER SvenCoOpFreeplay

WORKDIR /app

CMD ["/bin/bash"]

ONBUILD USER root
