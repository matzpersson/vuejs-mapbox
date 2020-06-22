# VueJs/Mapbox Singe Page App
Vue front-end using Vuex as the common store and Mapbox as the mapping engine. The app includes minimalistic, placeholder Jest tests, dockerfile (without volume mounts) with run.sh for convenience, Gitlab CI/CD deployment yaml and Kubernetes example deployment script.

The static site is temporarily hosted on http://archistar-spa.s3-website-ap-southeast-2.amazonaws.com/

Repo moved to: https://gitlab.com/archistar/archistar-spa

### Environment File
Configure your environment tokens and default settings in your development environment through .env. Copy .env-example to .env and replace atleast maptoken.

## Local installation
Clone this repo and install.
```
git clone https://gitlab.com/archistar/archistar-spa.git
npm install
```

Run the application with:
```
npm run serve
```

## Docker installation
Assuming Docker software is installed on the workstation, change to the archistar-spa repo directory and execute following to build docker image and run:
```
./run.sh
```

## Testing
Browser interface tested on a Chrome browser only. Minimal mock and unit test created as placeholder demonstrating how they would be run in a typical pipeline. See gitlab-ci.yml for tests in pipeline. To run test locally:
```
npm test
```

## Static S3 deployment
As a static deployment option, i pushed this to a AWS S3 bucket through package.json scripts options. Static site is on: http://archistar-spa.s3-website-ap-southeast-2.amazonaws.com/ . To run locally (with your own AWS credentials):
```
npm build
npm deploy
```

## CI/CD and Deployment
Added gitlab-ci.yml and deployment.yaml to demonstrate the integration and deployment pipeline using gitlab's built in CI/CD Tools. All variables and environment settings in GitLab portal and used during the various stages of build and deployment.

This is configured to deploy using Docker images to Kubernetes. This is a example only and not a currently active pipeline.

## Test Data
Testdata is included in repo to ensure availability of the data for test assessment. This would otherwise be a Constant url string to api endpoint.
