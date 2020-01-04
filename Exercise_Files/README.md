# Node.js: Testing and Code Quality Exercise Files

## Layout

- `nadia` - Nadia’s Restaurant Application
- `progress` - snapshots of application throughout course
  - subfolders by chapter, video
  - Ex: Chapter 2, Video 1 - `02_01`
- `solutions` - only changed files
  - subfolders by chapter, video

## Versions

- Atom - 1.18.0
- Node.JS - 6.11.1
- NPM - 3.10.10

Notes:

- cd into the nadia folder (that's the app)
- npm config set -g production false || to set environment to not production
- npm install || install all dependencies
- npm run debug || runs the server in debug mode
- navigate to http://localhost:3000
- add a reserveration, use incorrect format email address
- navigate to http://localhost:3000/admin || name/pw: admin

BDD Style:
Given a expect y

Installing and running assertion libraries:

test it out:

- cd solutions/03_02
- npm install
- npm test || executes test scripts

installing mocha:

- make sure you're inside project folder: cd/nadia
- npm install mocha chai -D
- add a file in the project folder, name it test/.eslintrc.js [adds new folder + file] to add Eslint preferences.
- add this to the eslintrc.js file, save and close:
  module.exports = {
  env: {
  mocha: true
  },
  rules: {
  "no-unused-vars": ["error", { varsIgnorePattern: "should|expect" }]
  }
  };

unit-testing - actually doing it:

- mirror structure of application for tests eg lib/schema/reservation.js >> test/unit/lib/schema/reservation.js
- initialize:
  - const chai=rquire('chai')
  - const should =chai.should()
  - const Reservation = require(.... reservation)
  - write the tests (lines: 5-25)
  - npm test -- --recursive || this runs the test. need to specify --recursive so it searches directories recusrively until file is found. it's not recursive by default
  - create a test/mocha.opts file if you want to configure and not type --recursive every time. needs to be in test folder
    - --recursive || add that line
