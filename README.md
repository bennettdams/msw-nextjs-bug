# Reproduction repo for a probable bug with MSW & Next.js

## Steps

1. Install initial Create Next App with TypeScript
`npx create-next-app@latest --use-npm --ts .`

2. Create `src` folder at root and move `pages` folder to it

3. Install & configure Jest, testing libs, etc. based on [Next's docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):
`npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom identity-obj-proxy react-test-renderer`

3. Create a simple test file based on [Next's docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):

3. Install MSW and follow setup for mocks/handlers/server [via docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):
`npm install msw --save-dev`

3. Integrate MSW with Jest

3. Install and utilize `whatwg-fetch` - needed for Polyfill with Next.js
`npm install -D whatwg-fetch` 

3. Change server config to `onUnhandledRequest: "error"` and add some simple fetch execution in the tested component

==> The test does not fail, even though the tests shows the error