ARG DOCKER_PREBUILD_IMAGE 
FROM ${DOCKER_PREBUILD_IMAGE} 
USER root

RUN if [ "$MANUAL_BUILD_POLYMAN" = true ] ; then \
        cd /code/packages/godwoken-polyman ;\
        yarn init_placeholder_config ;\
    else \
        cd /godwoken-polyman ;\
        yarn init_placeholder_config ;\
fi

EXPOSE 8024

WORKDIR /code
COPY ./entrypoint.sh /bin/

RUN chmod +x /bin/entrypoint.sh

ENTRYPOINT ["/bin/entrypoint.sh"]
