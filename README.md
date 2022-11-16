# Steps to reproduce

1. Go into `client/`
1. `npm install` to install dependencies
1. Run `npx parcel serve index.html` to start Parcel
1. Open `shared/main.js`
1. Change the exported string to some new value and save

## Expected
Updated string value should get picked up.

## Actual
Updated string value is not picked up. Note that `npm update parcel-cache-repro-shared` in `client/` doesn't help, nor does restarting Parcel. Also note that if the dependency is a child of the test package (in the file system), then I don't see this problem (as opposed to a sibling, as in this repro).

## Work around
Use `parcel serve --no-cache ...` or delete `.parcel-cache`.

## Environment
Tested on:

* Windows 10 21H2
* 64-bit
* Parcel 2.8.0
* NPM 8.8.0
* Node 14.17.0
