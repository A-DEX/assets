# A-DEX Assets

This repository contains blockchain, token, and wallet metadata with PNG and SVG logos.

## Repository structure

```text
blockchains/
  <network>/
    <chain>/
      info/
        info.json
        logo.png
        logo.svg
      assets/
        <precision>,<SYMBOL>@<contract>/
          info.json
          logo.png
          logo.svg
wallets/
  <wallet>/
    info/
      info.json
      logo.png
      logo.svg
```

- `<network>` is `mainnet` or `testnet`.
- Chain and wallet directory names use lowercase slugs.
- Token directories use `<precision>,<SYMBOL>@<contract>`, for example `4,EOS@eosio.token`.
- Token symbols use uppercase letters. Contract names must match the on-chain contract exactly.

## Raw asset links

GitHub raw URLs use this base:

```text
https://raw.githubusercontent.com/A-DEX/assets/main/
```

### Blockchain

Vaulta mainnet examples:

```text
https://raw.githubusercontent.com/A-DEX/assets/main/blockchains/mainnet/vaulta/info/info.json
https://raw.githubusercontent.com/A-DEX/assets/main/blockchains/mainnet/vaulta/info/logo.png
https://raw.githubusercontent.com/A-DEX/assets/main/blockchains/mainnet/vaulta/info/logo.svg
```

Pattern:

```text
blockchains/<network>/<chain>/info/<file>
```

### Token

EOS on Vaulta mainnet examples:

```text
https://raw.githubusercontent.com/A-DEX/assets/main/blockchains/mainnet/vaulta/assets/4%2CEOS%40eosio.token/info.json
https://raw.githubusercontent.com/A-DEX/assets/main/blockchains/mainnet/vaulta/assets/4%2CEOS%40eosio.token/logo.png
https://raw.githubusercontent.com/A-DEX/assets/main/blockchains/mainnet/vaulta/assets/4%2CEOS%40eosio.token/logo.svg
```

Pattern:

```text
blockchains/<network>/<chain>/assets/<precision>%2C<SYMBOL>%40<contract>/<file>
```

The comma and `@` in raw URLs are shown URL-encoded as `%2C` and `%40`.

### Wallet

Anchor wallet examples:

```text
https://raw.githubusercontent.com/A-DEX/assets/main/wallets/anchor/info/info.json
https://raw.githubusercontent.com/A-DEX/assets/main/wallets/anchor/info/logo.png
https://raw.githubusercontent.com/A-DEX/assets/main/wallets/anchor/info/logo.svg
```

Pattern:

```text
wallets/<wallet>/info/<file>
```

## Pull request data examples

Every new entry must include `info.json`, `logo.png`, and `logo.svg` in the appropriate directory.

### Add a blockchain

Example PR path:

```text
blockchains/mainnet/vaulta/info/
```

Example `info.json`:

```json
{
    "name": "Vaulta Mainnet",
    "website": "https://www.vaulta.com",
    "description": "Vaulta is a Web3 Banking network empowering the next frontier of finance.",
    "explorer": "http://unicove.com/en/vaulta",
    "research": "https://research.binance.com/en/projects/vaulta",
    "precision": 4,
    "symbol_code": "A",
    "contract": "core.vaulta",
    "type": "coin",
    "status": "active",
    "links": [
        {
            "name": "github",
            "url": "https://github.com/VaultaFoundation"
        },
        {
            "name": "X",
            "url": "https://x.com/Vaulta_"
        }
    ]
}
```

### Add a token

Example PR path:

```text
blockchains/mainnet/vaulta/assets/4,EOS@eosio.token/
```

The directory precision, symbol, and contract must match the corresponding values in `info.json`.

Example `info.json`:

```json
{
    "name": "EOS",
    "website": "https://eosnetwork.com",
    "description": "",
    "explorer": "https://eos.bloks.io/tokens/EOS-eos-eosio.token",
    "type": "",
    "precision": 4,
    "symbol_code": "EOS",
    "contract": "eosio.token",
    "status": "active",
    "tags": [],
    "links": [
        {
            "name": "coingecko",
            "url": "https://www.coingecko.com/en/coins/eos"
        }
    ]
}
```

### Add a wallet

Example PR path:

```text
wallets/anchor/info/
```

Example `info.json`:

```json
{
    "name": "Anchor",
    "website": "https://greymass.com/en/anchor",
    "description": "Anchor is a security and privacy focused open-source digital wallet for Antelope-based networks.",
    "status": "active",
    "links": [
        {
            "name": "github",
            "url": "https://github.com/greymass"
        },
        {
            "name": "X",
            "url": "https://x.com/greymass"
        }
    ]
}
```

## Logo requirements

- `logo.png`: PNG, exactly 256×256 pixels.
- `logo.svg`: valid SVG with a 32×32 canvas.
- Keep the logo centered and preserve its aspect ratio.
- Do not add unrelated image variants or source files to an asset directory.

## Pull request checklist

- Use the correct `mainnet` or `testnet` directory.
- Follow the chain, token, or wallet naming convention.
- Include valid `info.json`, `logo.png`, and `logo.svg` files.
- Ensure JSON has no comments or trailing commas.
- Verify that token precision, symbol, and contract match on-chain data.
- Verify that all website, explorer, and social links use HTTPS and are publicly accessible.
- Keep the pull request limited to the assets being added or updated.
