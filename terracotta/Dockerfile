# Pull base image.
FROM dockerfile/java:oracle-java7

ENV BM_VERSION 4.2.0

# Install BigMemory.
RUN \
  mkdir -p /opt/terracotta/data \
  mkdir -p /opt/terracotta/config \
  cd /opt/terracotta && \
  wget http://d2zwv9pap9ylyd.cloudfront.net/bigmemory-max-$BM_VERSION.tar.gz && \
  tar xvzf bigmemory-max-$BM_VERSION.tar.gz && \
  rm -f bigmemory-max-$BM_VERSION.tar.gz

# Define mountable directories.
VOLUME ["/opt/terracotta/config","/opt/terracotta/data"]

# Define working directory.
WORKDIR /opt/terracotta/bigmemory-max-$BM_VERSION

# Define default command.
CMD ["bash"]

# Expose ports.
#   - 9501: client
#   - 9520: server
#   - 9530: management
EXPOSE 9510
EXPOSE 9520
EXPOSE 9530