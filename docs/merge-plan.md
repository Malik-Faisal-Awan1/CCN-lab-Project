# Project plan: merge 3 big Packet Tracer builds

## Goal
Build one final Packet Tracer file that looks like a telecom operator network with:
1) **Telecom inner networking** (operator core/backbone)
2) **Telecom + B2B networking** (two enterprise customers)
3) **Telecom wireless networking** (abstracted 4G access domain + average customers)

Packet Tracer limitation note: LTE/EPC elements are abstracted using cloud/WAN/edge routers.

## Repository structure
- `references/` : imported starter .pkt files (unchanged)
- `working/`    : intermediate merged versions (checkpoints)
- `final/`      : final deliverable .pkt
- `docs/`       : addressing plan, VLAN plan, routing plan, test plan

## What to collect (minimum)
### Reference .pkt set A — Operator internal networking
Must show:
- OSPF single-area then multi-area
- route summarization at ABRs
- DC/server LAN (DNS/HTTP/FTP/SMTP)

### Reference .pkt set B — Operator + B2B
Must show:
- Customer A VLANs + trunk + MLS SVIs + DHCP on router + EIGRP
- Customer B VLANs + trunk + MLS SVIs + DHCP on router + RIP v2

### Reference .pkt set C — Wireless/Access abstraction
Must show:
- “wireless customers” behind an access cloud/edge router
- DHCP for subscribers
- reachability to operator services

## Merge checkpoints
- `working/01_operator_core.pkt`
- `working/02_operator_core_dc_services.pkt`
- `working/03_add_customerA_eigrp_vlan_dhcp.pkt`
- `working/04_add_customerB_ripv2_vlan_dhcp.pkt`
- `working/05_add_wireless_access_domain.pkt`
- `final/telecom_operator_complete.pkt`

## Next action for user
Upload 3 starter `.pkt` files into:
- `references/A_operator_internal/`
- `references/B_b2b/`
- `references/C_wireless_access/`

Name them like:
- `A_operator_internal.pkt`
- `B_b2b_customers.pkt`
- `C_wireless_access.pkt`

Then tell Copilot the exact filenames so we can map/merge features.
