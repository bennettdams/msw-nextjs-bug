# Reproduction repo for a probable bug with MSW & Next.js

## Steps

1. Install initial Create Next App with TypeScript
`npx create-next-app@latest --use-npm --ts .`

2. Create `src` folder at root and move `pages` folder to it

3. Install & configure Jest, testing libs, etc. based on [Next's docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):
`npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom identity-obj-proxy react-test-renderer`

3. Create a simple test file based on [Next's docs](https://nextjs.org/docs/testing#jest-and-react-testing-library):
