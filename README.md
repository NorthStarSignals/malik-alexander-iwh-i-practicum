# Integrating With HubSpot I: Foundations Practicum

A Node/Express app that reads and writes a HubSpot custom object through the CRM API, built for the
[Integrating With HubSpot I: Foundations](https://app.hubspot.com/academy/l/tracks/1092124/1093824/5493?language=en)
practicum.

**Custom object list view:** https://app.hubspot.com/contacts/247535123/objects/2-269141966/views/all/list

## The custom object

The custom object is **Stars** — navigational and notable stars. It has three custom properties, all
created in a HubSpot developer test account and associated with the contacts object type:

| Property | Internal name | Type |
| --- | --- | --- |
| Name | `name` | string (single-line text) |
| Constellation | `constellation` | string (single-line text) |
| Bio | `bio` | string (multi-line text) |

## Routes

| Route | Method | What it does |
| --- | --- | --- |
| `/` | GET | Fetches every Stars record from the CRM API and renders them in a table (`views/homepage.pug`). |
| `/update-cobj` | GET | Renders the form used to add a new Stars record (`views/updates.pug`). |
| `/update-cobj` | POST | Posts the submitted form data to the CRM API as a new Stars record, then redirects back to `/`. |

## Running it locally

1. `npm install`
2. Copy `.env.example` to `.env` and fill in the two values:
   - `PRIVATE_APP_ACCESS` — the access token from your private app
   - `CUSTOM_OBJECT_TYPE` — the custom object's objectTypeId, for example `2-12345678`
3. `npm start`
4. Open http://localhost:3000

`.env` is gitignored. The private app access token is never committed to this repository.

## Pre-requisites

- [Node](https://nodejs.org/en/download) and node packages
- [Express](https://expressjs.com/en/starter/installing.html)
- [Axios](https://axios-http.com/docs/intro)
- [Pug](https://pugjs.org/api/getting-started.html)
- The command line
- [Git and GitHub](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
