# PROOF (PRoduction On-ramp for Optimization and Feasibility)
PROOF (PRoduction On-ramp for Optimization and Feasibility) is a user-friendly tool designed for managing and executing WDL (Workflow Description Language) workflows using the Cromwell workflow manager. PROOF allows users to:

- Automate all the backend configurations necessary to run your workflows instantly.
- Validate, troubleshoot, assess performance, and run their workflows all under one roof.
- Refine their workflows before potential transitions to cloud-based infrastructures, providing a ‘proofing’ resource of sorts.

While it is currently configured to run on the Fred Hutch cluster, it is readily adaptable for local instances and/or instances hosted at other institutions. If interested, please email wilds@fredhutch.org with any questions.

## Repos

- [proof-api](https://github.com/FredHutch/proof-api): REST API for PROOF used to automate many/most of the startup/configuration steps of WDL workflow submission via Cromwell.
    - Latest release: [v1.0.0](https://github.com/FredHutch/proof-api/releases/tag/v1.0.0)
- [shiny-cromwell](https://github.com/FredHutch/shiny-cromwell): Shiny-based front end for PROOF that provides a point-and-click interface for new users.
    - Latest release: [v1.0.0](https://github.com/FredHutch/shiny-cromwell/releases/tag/v1.0.0)
- [rcromwell](https://github.com/getwilds/rcromwell): R package for interacting with Cromwell servers and the WDL workflows they manage.
    - Latest release: [v3.2.1](https://github.com/getwilds/rcromwell/releases/tag/v3.2.1)
- [proofr](https://github.com/getwilds/proofr): R package for interacting with the PROOF API mentioned above.
    - Latest release: [v0.2](https://github.com/getwilds/proofr/releases/tag/v0.2)

## Docs

- Product Description: https://sciwiki.fredhutch.org/datascience/proof/
- How to Use PROOF: https://sciwiki.fredhutch.org/dasldemos/proof-how-to/
- PROOF Troubleshooting: https://sciwiki.fredhutch.org/dasldemos/proof-troubleshooting/

## Support

For general questions, reach out to the Fred Hutch Data Science Lab (DaSL) at wilds@fredhutch.org. For bugs and/or feature requests, if you know which repository is the most relevant for your bug/feature, please open an issue directly in the corresponding repository. If you are unclear which repository it belongs in, or if the bug/feature spans across multiple repositories, [open an issue](https://github.com/getwilds/proof/issues) in this overarching PROOF repository and the PROOF development team will file issues in the corresponding locations.

## Contributing

If you would like to contribute to this project, see the [contribution guidelines](CONTRIBUTING.md) as well out our [WILDS Contributor Guide](https://getwilds.org/guide/) for more details.

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.


