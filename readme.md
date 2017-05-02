# heroku google cloud buildpack

This buildpack installs a pinned version of the Google Cloud SDK. During install, it generates a ```google-credentials.json``` file in the build directory, and generates a ```heroku-google-cloud.sh``` script in ```.profile.d``` which activates the Google service account with this credentials file upon server startup.

## Credentials

This script generates a credentials file using the following environment variables. If they're not present, the Google Cloud SDK will be installed, but this buildpack won't generate the credentials file or set the SDK to auth on server startup:

* ```GOOGLE_TYPE```
* ```GOOGLE_PROJECT_ID```
* ```GOOGLE_PRIVATE_KEY_ID```
* ```GOOGLE_PRIVATE_KEY```
* ```GOOGLE_CLIENT_EMAIL```
* ```GOOGLE_CLIENT_ID```
* ```GOOGLE_AUTH_URI```
* ```GOOGLE_TOKEN_URI```
* ```GOOGLE_AUTH_PROVIDER_CERT```
* ```GOOGLE_CLIENT_CERT```