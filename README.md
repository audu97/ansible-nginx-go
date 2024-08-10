
## [go-install.yaml](https://github.com/audu97/ansible-nginx-go/blob/master/go-install.yaml)
  * update apt repository
  * download the lates version og the go binary
  * extract go and remove the tarball to free up space
  * add go to environment variable
  * The Go environment is set up for future bash sessions. then makes sure environment is immediately available in the current Ansible run. Go installation is verified by checking its version.
## [playbook.yaml](https://github.com/audu97/ansible-nginx-go/blob/master/playbook.yaml)
  * update apt packages
  * installs nginx and starts nginx service
## [inventory.ini](https://github.com/audu97/ansible-nginx-go/blob/master/inventory.ini)
  * contains target vm public ip and ssh keys
## [webserver/templates/myapp.service.j2](https://github.com/audu97/ansible-nginx-go/blob/master/webserver/templates/myapp.service.j2)
  *contains nginx service, for automatically starting the go binary on boot also, when application crashes it automatically reboots
## [webserver/teamplates/nginx.conf.j2](https://github.com/audu97/ansible-nginx-go/blob/master/webserver/templates/nginx.conf.j2)
  * This configuration contains different Nginx settings, transforming it into a reverse proxy to route requests to the Go application. SSL/TLS can be configured here as well
## [deploy.yaml](https://github.com/audu97/ansible-nginx-go/blob/master/deploy.yaml)
  * copy go binary from local machine to vm
  * set up a systemd service for the go app to start automatically on boot and and also automaticaly restart when app rashes
  * configure nginx using nginx configuration files. i.e specifying nginx setting and configurations for the application
  * enablig nginx by creating a symlink between sites available and sites enabled
