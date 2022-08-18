# Projeto Interdisciplinar realizado para o 5º e 6º semestre da FATEC-Guaratinguetá
# Colaboração de: 
## Ariel Paixão, Brenda Aparecida, Carlos Marques e João Machado

# Commerce Layer Starter

A multi-country ecommerce starter that features the sanity studio built with Commerce Layer, Next.js, and deployed to Vercel.

![A preview image showing the frontend demo with some products.]()

![A screenshot of Commerce Layer Sanity studio]()

## Starter features

- An ecommerce storefront built with Nextjs, [Commerce Layer react components library](https://github.com/commercelayer/commercelayer-react-components), and Tailwind CSS.
- International shopping capabilities powered by [Commerce Layer](https://commercelayer.io) APIs.
- PSD2-compliant and production-ready checkout functionality powered by [Commerce Layer React Checkout Application](https://github.com/commercelayer/commercelayer-react-checkout).
- [Micro CLI seeder](https://github.com/commercelayer/commercelayer-cli-plugin-seeder/blob/main/README.md) to import Commerce Layer data.
- Structured content on Sanity CMS.
- Localization support.
- Deployment configuration to Vercel.

### ⚙️ Installation guide

1. Clone this repository ([learn how to do this](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)).

2. Rename the `/env.example` file to `.env` and add the following:

- Your project ID, dataset, and token from [manage.sanity.io](https://manage.sanity.io).
- Your sales_channels application client ID and base endpoint from [Commerce Layer](https://commercelayer.io). You can create this automatically by following our [onboarding guide](https://docs.commercelayer.io/developers/) or manually on the [Commerce Layer dashboard](https://dashboard.commercelayer.io/sign_up).

3. Run the command below to install the necessary dependencies of your project:

```bash
npm install && cd /studio && sanity install
```

4. Add your `projectTitle`, `projectId,` and `dataset` in `/studio/sanity.json`.

5. Run the command below to start the development server:

```bash
npm run dev
```

This will run the frontend at `localhost:3000` and studio at `localhost:3333`.

### ⬇️ Import test studio content

> If you set up your project from the starters page on Sanity, you should skip this step as Sanity will automatically add the dataset's content.

1. Extract the `production.tar.gz` file in `/.sanity-template/data` directory using the command below:

```bash
tar -xf production.tar.gz
```

The extracted folder name should look like `production-export-2021-02-26t14-15-56-557z`.

2. Run the command below in the `/studio` directory to import the `data.ndjson` file in the extracted folder.

```bash
sanity dataset import ../.sanity-template/data/<name of extracted folder>/data.ndjson <your_dataset>
```

3. Check the frontend and studio now to preview the imported content.

### ⬇️ Seed Commerce Layer data

1. Create a free [Commerce Layer account](https://dashboard.commercelayer.io/sign_up). If you already have an account, kindly skip to Step 3.

2. Create a new [organization](https://commercelayer.io/docs/data-model/users-and-organizations) or follow the [onboarding tutorial guide](https://docs.commercelayer.io/developers/).

3. Create a new application in the **Integrations** tab with **Name** set to `<Project Name>`, and **Role** set to `admin`.

4. In your newly created application, copy your `Client ID`, `Client Secret`, and base endpoint.

5. Install the [Commerce Layer CLI](https://github.com/commercelayer/commercelayer-cli) which is available as an [npm package](https://www.npmjs.com/package/@commercelayer/commercelayer-cli) or [yarn package](https://yarnpkg.com/package/@commercelayer/cli) using the command below:

```bash
// npm
npm install -g @commercelayer/cli

//yarn
yarn global add @commercelayer/cli
```

6. Log into your application via the CLI using the previously created CLI credentials like so:

```bash
commercelayer applications:login -o <organizationSlug> -i <clientId> -s <clientSecret> -a <applicationAlias>
```

7. Install the [seeder plugin](https://github.com/commercelayer/commercelayer-cli-plugin-seeder/blob/main/README.md) using the command below:

```bash
commercelayer plugins:install seeder
```

8. Run the command below to import three demo [markets](https://data.commercelayer.app/seed/markets.json) (UK, USA, and Europe), a set of [product SKUs](https://data.commercelayer.app/seed/skus.json), related [price lists](https://data.commercelayer.app/seed/price_lists.json), related [prices](https://data.commercelayer.app/seed/prices.json), [stock locations](https://data.commercelayer.app/seed/stock_locations.json), and [inventory](https://data.commercelayer.app/seed/stock_items.json) into your organization using the multi_market [business model](https://commercelayer.io/docs/data-model/markets-and-business-models).

```bash
commercelayer seed -b multi_market
```

9. To see the commands for other seeder options, type the command below:

```bash
commercelayer --help
```

## Contributors guide

1. Fork [this repository](https://github.com/commercelayer/sanity-template-commercelayer) (learn how to do this [here](https://help.github.com/articles/fork-a-repo)).

2. Clone the forked repository like so:

```bash
git clone https://github.com/<your username>/sanity-template-commercelayer.git && cd sanity-template-commercelayer
```

3. Make your changes and create a pull request ([learn how to do this](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)).

4. Someone will attend to your pull request and provide some feedback.

## License

This repository is published under the [MIT](LICENSE) license.

---
