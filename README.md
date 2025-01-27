<!-- markdownlint-disable MD014 -->
<!-- markdownlint-disable MD033 -->
<!-- markdownlint-disable MD041 -->
<!-- markdownlint-disable MD029 -->

<div align="center">

  <h1 style="font-size: 2.5rem; font-weight: bold;">Profile Module Template</h1>

  <p>
    <strong>A customizable profile module for easy integration with module federation</strong>
  </p>

</div>

<details>
  <summary>Table of Contents</summary>

- [Getting Started](#getting-started)
  - [Installing Dependencies](#installing-dependencies)
  - [Running the Development Server](#running-the-development-server)
  - [Customizing Your Profile](#customizing-your-profile)
- [Module Federation Configuration](#module-federation-configuration)
- [Theming and Styling](#theming-and-styling)
- [Building for Production](#building-for-production)
- [Running Tests](#running-tests)
- [Deploy to Web4](#deploy-to-web4)
- [Contributing](#contributing)

</details>

## Getting Started

### Installing Dependencies

This project uses Bun as the package manager. Install the dependencies with:

```bash
bun install
```

### Running the Development Server

Start the development server on `localhost:5170`:

```bash
bun run dev
```

The development server is configured with hot module replacement for a smooth development experience.

### Customizing Your Profile

1. Open `src/components/Profile.tsx` to modify the main profile component.
2. Update styles in `src/index.css` or use Tailwind classes directly in your components.
3. Adjust the theme in `tailwind.config.js` to match your desired look and feel.

## Module Federation Configuration

This template is set up for module federation. The configuration can be found in `rsbuild.config.ts`. Key points:

- The profile module is exposed as `"./Profile"`.
- The exposed component is now a TypeScript file: `./src/components/Profile.tsx`.
- Shared dependencies are configured to utilize the dependencies of the host "gateway".

## Theming and Styling

- This project uses Tailwind CSS for styling.
- Customize the theme in `tailwind.config.js`.
- Use CSS variables for easy theming across your application.

## Building for Production

To create a production build:

```bash
bun run build
```

This will generate optimized files in the `dist` directory.

## Running Tests

Execute the test suite with:

```bash
bun run test
```

For more details on testing, see the [testing guide](./playwright-tests/README.md).

## Deploy to web4

1. Build the project

```cmd
pnpm run build
```

2. Create a web4 subaccount of your master account (this will be your domain).

```cmd
near account create-account fund-myself web4.MASTER_ACCOUNT.testnet '1 NEAR' autogenerate-new-keypair save-to-keychain sign-as MASTER_ACCOUNT.testnet network-config testnet sign-with-keychain send
```

Be sure to "Store the access key in legacy keychain"!

3. Run web4-deploy to upload production bundle to nearfs and deploy it to a minimum-web4 contract to your account.

```cmd
npx github:vgrichina/web4-deploy dist web4.MASTER_ACCOUNT.testnet --deploy-contract --nearfs
```

Deploy should be accessible and your website accessible at:

`testnet`: MASTER_ACCOUNT.testnet.page

`mainnet`: MASTER_ACCOUNT.near.page

## Contributing

We welcome contributions! Please read our [contribution guide](./CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

<div align="right">
<a href="https://nearbuilders.org" target="_blank">
<img
  src="https://builders.mypinata.cloud/ipfs/QmWt1Nm47rypXFEamgeuadkvZendaUvAkcgJ3vtYf1rBFj"
  alt="Near Builders"
  height="40"
/>
</a>
</div>
