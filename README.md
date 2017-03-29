
# Getting started

## Required

1. Install [Docker](https://www.docker.com/) 17.03.0-ce+. This should also install Docker Compose 1.11.2+.
2. Verify versions: `docker -v; docker-compose -v;`

## Recommended
1. Install [VNC Viewer](https://www.realvnc.com/download/viewer/) to view & interact with selenium sessions that would otherwise be headless.

# Rails app

This base Rails app is very simple since the focus here is on docker. 
- Was setup with `rails new app --skip-active-record`. The database was skipped to stay lightweight.
- It has one root path route to the WelcomeController which renders "Hello World!" from `views/welcome/index.html.erb`

# Basic Docker Commands

### First run

`docker-commpose build`

### Run

`docker-compose up` Will install all the gems, and launch the web server.

`open http://localhost:3000` Once the server is up, the root page can be seen on your local machine.

### Test

`docker compose test` Ensure the services are already 'up' in another terminal, or in detached mode, before running tests.

`vnc://localhost:5900 password:secret` To watch the selenium tests run, use VNC to connect to the Selenium service. [VNC Viewer](https://www.realvnc.com/download/viewer/) works well, and on OS X Screen Sharing app is built-in. To interact and debug a browser session, add `byebug` into the test to stop the driver.
