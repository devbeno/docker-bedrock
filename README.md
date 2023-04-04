## Usage

### First time setup
1. `git clone https://github.com/devbens/docker-bedrock.git your-project`
1. `cd your-project`
1. Adjust `PROJECT_NAME=bedrock` in the Makefile to your projects name (use [kebap-case](https://stackoverflow.com/questions/11273282/whats-the-name-for-hyphen-separated-case/12273101#12273101) as this is also used for your local development domain)
1. Run `make up` and follow the instructions
1. Your new project should start and you should be greeted with the local URLs where you can access it

### Starting, stopping etc...
Run `make up` to start everything

Run `make stop` to stop everything

Run `make restart` to - you probably guessed it - restart everything

Run `make rebuild` to rebuild the project from the ground (current database will be lost if not backed up)

### Using composer
Bedrock Docker abstracts composer into a container. You can use `make composer` like you would use `composer` standalone:

    # install a wordpress plugin:
    make composer require wpackagist-plugin/wp-mail-smtp
    
    # update wordpress & plugins:
    make composer update


### Backup a database
Run `make mysql-backup` creates a compressed backup of your database in the backup folder. If you need a more fine grained backup you can use phpMyAdmin

### Restoring a database
Use phpMyAdmin to restore the database or use `make mysql-restore` if you created a backup previously

### Upgrading the project & development containers
Run `make upgrade`

### Logging & information
Run `make logs` or `make logs app` for just the logs of all or specific containers

Run `make state` to see the current state of your containers

Run `make urls` to see the URLs of the project

### Accessing containers
Run `make ssh app` or `make logs web` to access the specific containers

### Deleting the containers
Run `make destroy`
