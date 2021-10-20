# Reproduction repo for a probable bug with MSW & Next.js

## To try it out

`npm i`

`npm run test`

## Steps to reproduce from zero

1. Install initial Create Next App with TypeScript
`npx create-next-app@latest --use-npm --ts .`

https://github.com/bennettdams/msw-nextjs-bug/commit/2cf426a22bcdab3836365509cdc40a82bfae54f1

2. Create `src` folder at root and move `pages` folder to it

https://github.com/bennettdams/msw-nextjs-bug/commit/78b657e495d08da7fb12343b07b2e66327d742c8

3. Install & configure Jest, testing libs, etc. based on [Next's docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):
`npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom identity-obj-proxy react-test-renderer`

https://github.com/bennettdams/msw-nextjs-bug/commit/aaf1fb3257c311bf25ea7f6e25487a8159feceb2

3. Create a simple test file based on [Next's docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):

https://github.com/bennettdams/msw-nextjs-bug/commit/bd9ba7776ca00e8d8deec740c79a5ac12749752e

3. Install MSW and follow setup for mocks/handlers/server [via docs](https://mswjs.io/docs/getting-started/mocks):
`npm install msw --save-dev`

https://github.com/bennettdams/msw-nextjs-bug/commit/cdd07c1218bfb411bf958c10685aa426be591316

3. Integrate MSW with Jest

https://github.com/bennettdams/msw-nextjs-bug/commit/39738368a00308c1f478ae7f86537d26abd092a4

3. Install and utilize `whatwg-fetch` - needed for Polyfill with Next.js
`npm install -D whatwg-fetch` 

https://github.com/bennettdams/msw-nextjs-bug/commit/5cbe84a9ab2830dce8f5f18b862e576bf889773f

3. Change server config to `onUnhandledRequest: "error"` and add some simple fetch execution in the tested component

https://github.com/bennettdams/msw-nextjs-bug/commit/f77bb0f6bdcf9d37796c678eedda420cc656f3a1

==> The test does not fail, even though the tests shows the error
