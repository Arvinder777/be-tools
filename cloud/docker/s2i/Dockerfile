#
# Dockerfile for s2i builder image
#

ARG BE_TAG
ARG ARG_VERSION

FROM "$BE_TAG":"$ARG_VERSION"-"$ARG_VERSION"

# Defines the location of the S2I
LABEL io.openshift.s2i.scripts-url=image:///usr/local/s2i

# Copy the S2I scripts from ./.s2i/bin/ to /usr/local/s2i when making the builder image
COPY assemble /usr/local/s2i/assemble
COPY usage /usr/local/s2i/usage

RUN cp /home/tibco/be/run /usr/local/s2i/run
RUN chmod 777 /usr/local/s2i/assemble
RUN chmod 777 /usr/local/s2i/usage

CMD ["/usr/local/s2i/usage"]
