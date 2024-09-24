# How to replicate problem

1. Run `npm i` to install dependencies
2. Run `npm run build` to build the project

# Context of the error

@veriff/incontext-sdk/index.esm.js module includes code at the top of the file that modifies the process.env variable on the library side.

The Webpack DefinePlugin does the same on the client side, but since it is transpiling the library into the client code, it substitutes the process.env variable for the content of it, which results in essentially CLIENT_PROCESS_ENV = CLIENT_PROCESS_ENV + LIBRARY_PROCESS_ENV


