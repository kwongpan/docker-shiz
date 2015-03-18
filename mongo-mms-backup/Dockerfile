# bigtoast/mongo-mms-backup

from ubuntu

MAINTAINER Andrew Headrick "github.com/bigtoast"

RUN apt-get update && \
	apt-get install -y curl logrotate && \
	apt-get clean && \
	apt-get autoremove --purge && \
	rm -rf /tmp/* /var/tmp/* /var/lib/apt/lists/*

# -OL

RUN curl -sSL https://mms.mongodb.com/download/agent/backup/mongodb-mms-backup-agent_3.1.0.250-1_amd64.deb -o mms.deb && \
	dpkg -i mms.deb && \
	rm mms.deb

VOLUME ["/etc/mongodb-mms"]

USER mongodb-mms-agent

CMD ["mongodb-mms-backup-agent", "-c", "/etc/mongodb-mms/backup-agent.config"]
