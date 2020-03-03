# Servicebot Drupal 7 testing module

This module is only for testing purposes.

## How to test servicebot module

### Requirements

* Setup a servicebot account
* Connect a stripe account to servicebot
* (optional) stripe cli


### How to test webhooks

1) Enable servicebot module
2) Navigate to `/admin/config/services/servicebot` and add service configuration info. 
    * servicebot secret key 
    * servicebot id
    * Servicebot service product
3) Authenicate the stripe cli with your stripe account
4) Set stripe cli to forward webhooks to your local site `stripe listen --forward-to https://123.ngrok.io/servicebot/webhooks`
5) Send test webhooks from stripe cli.  `stripe trigger customer.subscription.created`
    * check the Drupal servicebot module documentation for a list of all supported webhooks.