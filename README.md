# Walnut

A password manager whose server never sees your secrets.

**Important note: this project was written as a proof of concept. Do not use this in production.**

## How it works

Encryption and decryption are done using a locally generated key, which is encrypted using your master password and
stored locally.

Encryption and decryption are both done locally using that key. The server only serves as a storage for encrypted items;
it does not see your keys or items in plain text. You verify your identity with the server using the master password as
well.

This means that if you lose your secret key, you lose the ability to decrypt your items.

## Build from Source

1. Clone this repo and `cd` into project root.
2. `cd` into `webui` and build the webui.

```shell
cd webui
npm ci
npm run build
```

3. Build the core binary.

```shell
cd ..
cargo build --release --bin walnut
```

The webui will be embedded in the binary.

The binary will be `target/release/walnut`.

## License

Copyright 2026 Jhe-An Lee

This project is licensed under the [Apache License 2.0](LICENSE).