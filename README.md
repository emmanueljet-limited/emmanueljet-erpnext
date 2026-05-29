<div align="center">
  <img src="docs/public/frappe-docker.png" alt="Frappe Docker" width="80" />
  <h1>emmanueljet erpnext</h1>
  <p>An optimized ERPNext Docker image engineered to include more applications with native support for Paystack payment gateway.</p>
  <p>
    <a href="https://github.com/frappe/frappe_docker/actions/workflows/core-build-stable.yml">
      <img src="https://img.shields.io/github/actions/workflow/status/frappe/frappe_docker/core-build-stable.yml?branch=main&label=Build%20Stable" alt="Build Stable" />
    </a>
    <a href="https://frappe.github.io/frappe_docker/">
      <img src="https://img.shields.io/badge/Docs-Open%20Site-0A7EA4" alt="Docs" />
    </a>
  </p>
</div>

## Bundled Applications

- erpnext (Core Finance, Inventory, B2B Sales)
- payments (Core Payment Gateway Architecture)
- hrms (Decoupled HR and Payroll)
- lending (Inter-company loan management)
- insights (God-view Business Intelligence and Data Visualization)
- frappe_paystack (Multi-currency Africa-specific payment routing)

## Documentation

The full `frappe_docker` documentation is available in [`docs/`](docs/) and published at [frappe.github.io/frappe_docker](https://frappe.github.io/frappe_docker/).

### Recommended entry points

- **New here:** [Getting Started Guide](docs/getting-started.md)
- **Choosing a setup:** [Deployment methods](docs/01-getting-started/01-choosing-a-deployment-method.md)
- **ARM64 notes:** [ARM64](docs/01-getting-started/03-arm64.md)
- **Container setup overview:** [Container Setup Overview](docs/02-setup/01-overview.md)
- **Running in production:** [Production docs](docs/03-production/)
- **Operating a deployment:** [Operations docs](docs/04-operations/)
- **Development workflows:** [Development](docs/05-development/01-development.md)
- **FAQ:** [Frequently Asked Questions](https://github.com/frappe/frappe_docker/wiki/Frequently-Asked-Questions)

### Resources

- [Frappe framework](https://github.com/frappe/frappe)
- [ERPNext](https://github.com/frappe/erpnext)
- [Frappe Bench](https://github.com/frappe/bench)

## Quick Start

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose v2](https://docs.docker.com/compose/)
- [git](https://docs.github.com/en/get-started/getting-started-with-git/set-up-git)

> For Docker basics and best practices refer to Docker's [documentation](http://docs.docker.com)

### Build custom image

- First clone the repo:

  ```sh
  git clone https://github.com/emmanuel-limited/emmanueljet-erpnext --branch emmanueljet
  cd emmanueljet-erpnext
  ```

- Edit [apps.json](apps.json) to include your custom apps (if any)
- Then run:

  ```sh
  docker build \
    --secret id=apps_json,src=apps.json \
    --tag=emmanueljet-erpnext:version-16 \
    --file=images/custom/Containerfile
  ```

Wait for the image to be built (this may take a while)

## Usage (Docker Compose)

You can easily drop this image into your existing Docker Compose. See [docker-compose.yml](docker-compose.yml) for more details.

## License

This repository is licensed under the MIT License. See [LICENSE](LICENSE) for details.
