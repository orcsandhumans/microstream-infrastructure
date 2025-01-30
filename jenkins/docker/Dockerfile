FROM jenkins/jenkins:2.479.3-lts-jdk17

RUN jenkins-plugin-cli --plugins \
    kubernetes:4306.vc91e951ea_eb_d \
    workflow-aggregator:600.vb_57cdd26fdd7 \
    git:5.7.0 \
    github:1.40.0 \
    configuration-as-code:1915.vcdd0a_d0d2625 \
    ws-cleanup:0.48 \
    hashicorp-vault-plugin:371.v884a_4dd60fb_6 \
    aws-credentials:242.v8d05df911e3d \
    pipeline-stage-view:2.34 \
    simple-theme-plugin:202.v6367d3dea_73b_

COPY ./casc_configs/ /var/jenkins_home/casc_configs

# Set the JCasC path so Jenkins knows where to load configurations from
ENV CASC_JENKINS_CONFIG=/var/jenkins_home/casc_configs