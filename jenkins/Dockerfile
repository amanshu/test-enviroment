FROM jenkins/jenkins:lts

ARG Plugins=plugins.txt

LABEL name="Mirada Medical Jenkins Master build"
LABEL version=${Version}
LABEL description="The default setup of the Jenkins master for Mirada Medical"

# Define the required ports, these will need to be exposed with the -P flag at run time
EXPOSE 8080/tcp
EXPOSE 50000/tcp

# Copy files into the container
# groovy/ contains initialisation scripts for Jenkins
COPY --chown=jenkins:jenkins groovy/* /usr/share/jenkins/ref/init.groovy.d/

# Turn off the setup wizard on the grounds we'll be configuring separately
ARG JAVA_OPTS
ENV JAVA_OPTS "-Djenkins.install.runSetupWizard=false ${JAVA_OPTS:-}"

# Install the plugins listed in Plugins
COPY ${Plugins} /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
