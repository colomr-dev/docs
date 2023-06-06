---
description: How-to deploy Hugo generated static site at Google Firebase service
---

# Deploy Hugo site at Firebase

## Assumptions

On this how-to we assume that:

1. Understanding what Hugo SDK is and how to use it
2. Once generated public files by executing `hugo` command
3. We need to prepare Firebase to hosts our site

## Google Firebase&#x20;

Google Firebase is a comprehensive mobile and web development platform provided by Google. Firebase provides a range of features that cover various aspects of app development, including authentication, real-time database, cloud storage, hosting, cloud functions, and more.

It is cheaper an most suitable option than GCP for personal projects.

{% embed url="https://firebase.google.com/docs?hl=es-419" %}

{% embed url="https://gohugo.io/hosting-and-deployment/hosting-on-firebase/" %}

## Setup Firebase Project & Tools

Once logged into Firebase and launched the (first) project, please follow the next steps:

1. Install the CLI tool to talk with Firebase\
   `npm install -g firebase-tools`
2. Then we need to login\
   `firebase login`
3. And perform the initialization in the Hugo root working directory;\
   `firebase init`
4. Firebase features needed to deploy our site\
   From here:
   * Choose **Hosting** in the feature question
   * Choose the **project** you just set up
   * Accept the default for your database rules file
   * Accept the default for the publish directory, which is **`public`**
   * Choose “No” in the question if you are deploying a single-page app
5. Now we're done to deploy our site in our Firebase project, by issuing:\
   `firebase deploy --only hosting`

If everything is fine the output looks like

```
fcolomer@puzzle:~/repos/preventa.tech$ firebase deploy --only hosting

=== Deploying to 'pvtech-site'...

i  deploying hosting
i  hosting[pvtech-site]: beginning deploy...
i  hosting[pvtech-site]: found 41 files in public
✔  hosting[pvtech-site]: file upload complete
i  hosting[pvtech-site]: finalizing version...
✔  hosting[pvtech-site]: version finalized
i  hosting[pvtech-site]: releasing new version...
✔  hosting[pvtech-site]: release complete

✔  Deploy complete!

Project Console: https://console.firebase.google.com/project/pvtech-site/overview
Hosting URL: https://pvtech-site.web.app
```
