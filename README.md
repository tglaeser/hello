## _Hello World_ written in Motoko and compiled into WebAssembly
[dfx-download]:https://sdk.dfinity.org/docs/download.html
[dfx-docs]:https://sdk.dfinity.org/docs/index.html
[nodejs]:https://nodejs.org/
[wasm]:https://webassembly.org/
Code generated by executing `dfx new hello`; it demonstrates how to compile Motoko sources into WebAssembly to be served via [Node.js][nodejs].

#### Prerequisites
This project requires version `0.8.4` of the [DFINITY Canister SDK][dfx-download] being installed. To verify, run `dfx --version`.
#### Get the Sources
```
$ git clone https://github.com/tglaeser/hello.git
$ cd ./hello
```
#### Displays the Project Structure
```
$ tree -L 4 .
.
├── LICENSE
├── README.md
├── dfx.json
├── package-lock.json
├── package.json
├── src
│   ├── hello
│   │   └── main.mo
│   └── hello_assets
│       ├── assets
│       │   ├── favicon.ico
│       │   ├── logo.png
│       │   ├── main.css
│       │   └── sample-asset.txt
│       └── src
│           ├── index.html
│           └── index.js
└── webpack.config.js
```
#### Install Web Application Dependencies
```
$ npm install
```
#### Start a Local Internet Computer
```
$ dfx start
```
#### Create, Build, and Install Canister
```
$ dfx canister create --all
$ dfx build
$ dfx canister install --all
```
#### Call the `greet` Function from the Terminal
```
$ dfx canister call hello greet "World"
```
#### Call the `greet` Function from a Browser
Open a browser and navigate to the address and port your local IC is listening to: `http://<host>:<port>/?canisterId=<hello_assets_cid>`. See value `networks.local.bind` in file [dfx.json](./dfx.json#L30) for the `<host>:<port>` binding, you can also execute `dfx config` to see the configuration. The `<hello_assets_cid>` value was printed to the console when previously installing the canister.
#### Further Reading
- [SDK documentation][dfx-docs] - For the SDK, the Candid Specification, and the Motoko language.
- [WebAssembly home page][wasm] - For the WASM binary instruction format.
