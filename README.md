# IDP Builder Stack for Cosmonic Control

This repository provides a complete Kubernetes cluster setup using IDP Builder, pre-configured with Cosmonic Control for WebAssembly workload management.

## Prerequisites

- Docker or compatible container runtime
- Kubernetes cluster access
- `kubectl` CLI tool installed
- Git

## Installation

### 1. Install IDP Builder

First, install the IDP Builder tool by following the instructions at [idpbuilder repository](https://github.com/cnoe-io/idpbuilder?tab=readme-ov-file#installation).

### 2. Deploy the Stack

To deploy using the public repository:

```bash
idpbuilder create --host localhost.cosmonic.sh --extra-ports "80:80" -p https://github.com/cosmonic-labs/idp-stack//cosmonic-control
```

## Available Services

After successful deployment, the following services will be available:

- **Cosmonic Control Console**: [https://console.localhost.cosmonic.sh:8443/](https://console.localhost.cosmonic.sh:8443/)
  - Manage and monitor your WebAssembly workloads
  - View system metrics and logs

- **Argo CD Console**: [https://argocd.localhost.cosmonic.sh:8443/](https://argocd.localhost.cosmonic.sh:8443/)
  - GitOps workflow management
  - Application deployment tracking

- **Welcome Tour App**: [https://welcome-tour.localhost.cosmonic.sh:8443/](https://welcome-tour.localhost.cosmonic.sh:8443/)
  - Example WebAssembly application
  - Demonstrates successful deployment

## Development Guide for stack improvement

### Local Stack Package Development

1. Clone this repository:
```bash
git clone [repository-url]
cd idp-stack
```

2. Deploy using local package:
```bash
idpbuilder create --host localhost.cosmonic.sh --extra-ports "80:80" -p idp-package
```

### Package Structure

The stack includes the following key components:
- `idp-package/cosmonic-control.yaml`: Cosmonic Control configuration
- `idp-package/hostgroup.yaml`: Host group definitions
- `idp-package/welcome-tour.yaml`: Example application configuration
- `manifests/ingress.yaml`: Configures nginx ingress for Cosmonic Control and Hostgroups

## Troubleshooting

### Common Issues

1. **Connection Issues**
   - Verify that your Kubernetes cluster is running
   - Check if the DNS resolution for localhost.cosmonic.sh is working
   - Ensure ports 8443 is not being used by other services

2. **Deployment Failures**
   - Check the Argo CD console for deployment status
   - View pod logs using `kubectl logs`
   - Verify cluster resources availability

### Getting Help

- Open an issue in the GitHub repository
- Check the [Cosmonic documentation](https://docs.cosmonic.com)
- Join the community discussion

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch
3. Submit a Pull Request

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file included in the repository.


