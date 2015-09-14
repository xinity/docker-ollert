# docker-ollert
dockerized trello stats app ollert : https://github.com/sep/ollert

## Configuration
to use the docker container, you just a .env which will your Environment variables:
PUBLIC_KEY
required
Retrieve a public key from Trello by visiting https://trello.com/1/appKey/generate.
TRELLO_TEST_DISPLAY_NAME
required
Display name to use while running cukes (this is your @<username> from Trello)
TRELLO_TEST_USERNAME
required
Username to use while running cukes
TRELLO_TEST_PASSWORD
required
Password to use while running cukes
MEMBER_TOKEN
required
this value is used to run the integration tests. To generate this value after you have entered your PUBLIC_KEY run the following command and paste the result into your .env file where it asks you to:
rake test:setup
SESSION_SECRET
optional
Any string

## Usage
### Build
docker build -t docker-ollert .

### Run
 docker run -d -v [path to your .env file]/.env:/srv/ollert/.env -p 8080:4000 docker-ollert

Now go to http://localhost:8080 and your good to go :)