FROM codercom/code-server:latest

#RUN chmod 755 /usr/bin/sudo
#RUN chmod 644 /usr/lib/sudo/sudoers.so
#RUN chown root:dyno /usr/bin/sudo

#RUN chown root:root /usr/bin/sudo
#RUN chmod 4755 /usr/bin/sudo

RUN chown root:dyno /etc/sudoers
RUN chmod 440 /etc/sudoers

USER coder

# Apply VS Code settings
COPY settings.json .local/share/code-server/User/settings.json

# Use bash shell
ENV SHELL=/bin/bash

# Use our custom entrypoint script first
COPY heroku-entrypoint.sh /usr/bin/heroku-entrypoint.sh
ENTRYPOINT ["/usr/bin/heroku-entrypoint.sh"]
