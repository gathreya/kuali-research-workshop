
## Kuali Research API Workshop

# Setup

- Install Node/NPM. 4.x or newer, 6.9.1 recommended.
  - [Download Node](https://nodejs.org/en/download/)
  - Alternatively on Mac/Linux use nvm `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash`
- Get a copy of the workshop files
  - `git clone https://github.com/kuali/kuali-research-workshop.git`
  - or download (https://github.com/kuali/kuali-research-workshop/archive/master.zip)
- In the folder with the workshop files
  - `npm install`
  - `npm start`

https://docs.google.com/document/d/1XOTEUX1IOjLxUBA9jKYwnSvjSh1J4SvwgtrPoePevXc/edit

# Exercise 1 -- Institutional Proposals - Proposals.js

- Fetch the list of proposals when the component mounts
  - using `fetch` load a list of proposals from `/instprop/api/v1/institutional-proposals/` and set it into the local state as `proposals`
  - alternatively use the pre-built method `this.fetchProposals`
- Fetch related data to replace the codes with the actual descriptions
  - using `fetch` grab the list of proposal types from `/research-common/api/v1/proposal-types/` and using lodashes `keyBy` create a hash of the types by code and set the result into the local state as `proposalTypes`
- Fetch other related data similar to above for other data being displayed
  - activity types from `/research-common/api/v1/activity-types/`  into state as `activityTypes`
  - proposal statuses from `/instprop/api/v1/proposal-statuses/` into state as `proposalStatues`
  - units from `/research-common/api/v1/units/` into state as `units`
- Tie filtering into the proposal search so that when you click the filter button it only shows relevant results
  - do this by appending to the url ?key=value. The key is stored in `this.state.filterBy` and the value is in `this.state.filter`
- You can find the final version in `Proposals.final.js`
