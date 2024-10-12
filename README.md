Here is an updated sample README.md incorporating all the suggested improvements:

---

<a href="https://solidity.readthedocs.io/en/v0.8.18/"><img alt="solidity v0.8.18" src="https://badgen.net/badge/solidity/v0.8.18/blue"></a>

# Element Pay Smart Contract (BaseFlow)

## Description

Element Pay's BaseFlow is a groundbreaking multi-chain EVM-based smart contract designed to revolutionize decentralized payments in Africa. By facilitating the on-chain lifecycle of payment orders, BaseFlow enables seamless crypto-to-fiat transactions. Users can create payment orders, while liquidity providers handle escrowed cryptocurrency, making fast and easy payments to mobile wallets (e.g., M-Pesa) and banks (e.g., NCB, CBK) a reality.

## Value Proposition

BaseFlow empowers financial inclusion by providing a reliable and efficient method for crypto-to-fiat conversions, enabling easier access to financial services for individuals and businesses in Africa.

## Key Features

- **Multi-Chain Compatibility**: Operates across various EVM chains, ensuring broad accessibility.
- **Security**: Ensures secure transactions with escrow functionality.
- **Scalability**: Designed to handle high transaction volumes.
- **User-Friendly**: Simplifies the process of creating and managing payment orders.

## Usage Scenarios

- **Individuals**: Send and receive payments from mobile wallets and banks seamlessly.
- **Businesses**: Facilitate cross-border transactions with minimal fees and delays.
- **Liquidity Providers**: Offer liquidity services and earn fees through escrowed transactions.

## Visual Workflow

![Workflow Diagram](link-to-diagram)

## Deployment

Deployment is done using Hardhat scripts.

#### Deploy and verify upgradeable proxy contract

```bash
npx hardhat run scripts/deploy.ts --network <network>
npx hardhat verify --network <network> <contract_address>
# for Tron network,
tronbox migrate -f 1 --to 1 --network <network>
```

#### Upgrade proxy contract

```bash
npx hardhat run scripts/upgrade.ts --network <network>
# upgrade across all EVM chains
npx hardhat run scripts/upgrade.ts --network arbitrumOne && npx hardhat run scripts/upgrade.ts --network base && npx hardhat run scripts/upgrade.ts --network bsc && npx hardhat run scripts/upgrade.ts --network polygon && npx hardhat run scripts/upgrade.ts --network optimisticEthereum && npx hardhat run scripts/upgrade.ts --network scroll
# upgrade across all EVM testnet chains
npx hardhat run scripts/upgrade.ts --network arbitrumSepolia && npx hardhat run scripts/upgrade.ts --network amoy && npx hardhat run scripts/upgrade.ts --network baseSepolia && npx hardhat run scripts/upgrade.ts --network sepolia
# for Tron network,
tronbox migrate -f 2 --to 2 --network <network>
```

#### Owner configurations

Update network settings in `scripts/config.ts`.

```bash
npx hardhat run scripts/setSupportedTokens.ts --network <network>
npx hardhat run scripts/updateProtocolAddresses.ts --network <network>
npx hardhat run scripts/updateProtocolFee.ts --network <network>
# for Tron network,
npx hardhat run scripts/tron/setSupportedTokens.ts
npx hardhat run scripts/tron/updateProtocolAddresses.ts
npx hardhat run scripts/tron/updateProtocolFee.ts
```

## Testnet Contracts

<table>
	<thead>
		<tr>
			<th>Network</th>
			<th>Contracts</th>
			<th>Address</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td rowspan="2">Base Sepolia</td>
			<td>Gateway Proxy</td>
			<td>0x847dfdAa218F9137229CF8424378871A1DA8f625</td>
		</tr>
		<tr>
			<td>Gateway Implementation</td>
			<td>0xfB411Cc6385Af50A562aFCb441864E9d541CDA67</td>
		</tr>
	</tbody>
</table>

## Mainnet Contracts

<table>
	<thead>
		<tr>
			<th>Network</th>
			<th>Contracts</th>
			<th>Address</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td rowspan="2">Ethereum</td>
			<td>Gateway Proxy</td>
			<td>0x16c9C78Dbb224889E3e2ADef991C8c4438ea797B</td>
		</tr>
		<tr>
			<td>Gateway Implementation</td>
			<td>0xD293fCd3dBc025603911853d893A4724CF9f70a0</td>
		</tr>
		<tr>
			<td rowspan="2">Base</td>
			<td>Gateway Proxy</td>
			<td>0x30F6A8457F8E42371E204a9c103f2Bd42341dD0F</td>
		</tr>
		<tr>
			<td>Gateway Implementation</td>
			<td>0x0a7aA9F8eab1665DD905288669447b66082E4B17</td>
		</tr>
	</tbody>
</table>

## Testing

Contract tests are defined under the tests directory. To run all the tests, run:

```bash
npx hardhat test
```

## Commits and PRs

This project uses Conventional Commits to generate release notes and to determine versioning. Commit messages should adhere to this standard and be of the form:

```bash
$ git commit -m "feat: Add new feature x"
$ git commit -m "fix: Fix bug in feature x"
$ git commit -m "docs: Add documentation for feature x"
$ git commit -m "test: Add test suite for feature x"
```

Further details on `conventional commits` can be found [here](https://www.conventionalcommits.org/en/v1.0.0/).

## Roadmap

- **Q4 2024**: Launch beta version, integrate with M-Pesa.
- **Q1 2025**: Expand support to more banks and mobile wallets.
- **Q2 2025**: Implement additional security features and scalability improvements.

## Team

- **JoeThuku**: [GitHub Profile](https://github.com/JosephThuku)
- **AlyMtsumi**: [GitHub Profile](https://github.com/Mtsumi)

## Contributors ✨

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/JosephThuku"><img src="https://avatars.githubusercontent.com/u/93326983?v=4" width="50px;" alt="Prosperity"/><br /><sub><b>JoeThuku</b></sub></a><br /><a href="https://github.com/element-pay/BaseFlow" title="code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/Mtsumi"><img src="https://avatars.githubusercontent.com/u/91135509?v=4" width="50px;" alt="chibie"/><br /><sub><b>AlyMtsumi</b></sub></a><br /><a href="https://github.com/element-pay/BaseFlow" title="code">💻</a></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td align="center" size="13px" colspan="7">
        <img src="https://raw.githubusercontent.com/all-contributors/all-contributors-cli/1b8533af435da9854653492b1327a23a4dbd0a10/assets/logo-small.svg">
          <a href="https://all-contributors.js.org/docs/en/bot/usage">Add your contributions</a>
        </img>
      </td>
    </tr>
  </tfoot>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## License

[Affero General Public License v3.0](https://choosealicense.com/licenses/agpl-3.0/)

---

This comprehensive README.md should help make your project stand out in the Base Africa Buildthon.
