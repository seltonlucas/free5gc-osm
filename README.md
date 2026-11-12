# Free5GC descriptors and OSM deployment

This repository contains the Free5GC/UERANSIM descriptors and Pipeline 2 of the ODIM IaC-to-MANO workflow.

- Read [the readiness and dispatch guide](docs/readiness-setup.md) before operational use.
- P2 verifies Kubernetes before OSM resource creation and separately monitors the NS lifecycle. Neither check proves UE registration, a PDU session or UE-to-DN traffic.
- VM images are prepared separately in seltonlucas/packer_free5gc and must be explicitly selected by the Terraform configuration. A prepared hypervisor is not an already ready Kubernetes cluster.
- Automatic P1 handoff must remain disabled until the receiving workflow, secrets, image contract and target environment have been reviewed.

## Offline verification

```bash
python3 -m unittest discover -s tests -v
```

These tests use synthetic fixtures and do not deploy anything or contact the laboratory. Functional 5G validation remains a separate, explicitly authorized experiment.
