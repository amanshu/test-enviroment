FROM jenkins/jenkins:lts

ARG Plugins=plugins.txt
ARG Configuration=casc

LABEL name="Amanshu Jenkins Master build"
LABEL version=${VERSION}
LABEL description="The default setup of the Jenkins master for Amanshu ${version}"

# Define the required ports, these will need to be exposed with the -P flag at run time
EXPOSE 8080/tcp
EXPOSE 50000/tcp

# Copy files into the container
# CONFIGURATION contains the setup for Jenkins Configuration as Code
# groovy/ contains initialisation scripts for Jenkins
COPY --chown=jenkins:jenkins ${Configuration}/ /jenkins_setup/${Configuration}/
COPY --chown=jenkins:jenkins groovy/* /usr/share/jenkins/ref/init.groovy.d/

# Turn off the setup wizard on the grounds we'll be configuring separately
ARG JAVA_OPTS
ENV JAVA_OPTS "-Djenkins.install.runSetupWizard=false ${JAVA_OPTS:-}"
ENV CASC_JENKINS_CONFIG /jenkins_setup/${Configuration}

# Install the plugins listed in Plugins
COPY --chown=jenkins:jenkins ${Plugins} /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --plugin-file /usr/share/jenkins/ref/plugins.txt
