# Data.gov (data-gov)

Data.gov is the United States federal government's open data catalog, operated by the General Services Administration (GSA) Technology Transformation Services. It indexes over 300,000 datasets, tools, and resources from federal, state, local, and tribal governments, universities, and non-profits. The catalog runs on CKAN 2.11 and exposes the standard CKAN Action API at `catalog.data.gov/api/3/action` for programmatic discovery and retrieval of datasets, organizations, groups, tags, and resources. Data.gov also defines and harvests the federal Project Open Data / DCAT-US 1.1 schema (the `/data.json` endpoint that every federal executive agency must publish under the OPEN Government Data Act of 2018).

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/data-gov/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=government-api-evangelist&utm_content=repo)

## Tags

 - Government, Open Data, Catalog, CKAN, Datasets, Federal, GSA, Open Government

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Tier

**Tier 1** — Canonical U.S. federal open data catalog, mandated by the OPEN Government Data Act of 2018. Exposes the full CKAN 2.11 Action API, indexes 300,000+ datasets, defines the DCAT-US metadata standard used by every federal agency `/data.json`, and operates openly with all infrastructure code on `github.com/GSA`.

## APIs

### Data.gov CKAN Action API
The CKAN Action API exposes the full Data.gov catalog programmatically. Single endpoint family at `/api/3/action/{action_name}` accepting GET (simple reads) or POST (JSON body). Key actions: `package_search`, `package_show`, `package_list`, `organization_list`, `organization_show`, `group_list`, `group_show`, `tag_list`, `resource_show`, `current_package_list_with_resources`. Responses are wrapped in `{success, result, help}`. Read access is anonymous; write actions require an API key.

**Base URL:** `https://catalog.data.gov/api/3/action`

- [Documentation — CKAN 2.11 API](https://docs.ckan.org/en/2.11/api/)
- [API Reference — help_show](https://catalog.data.gov/api/3/action/help_show)
- [Standards — DCAT-US](https://resources.data.gov/resources/dcat-us/)

### Project Open Data (data.json) Catalog API
Every U.S. federal executive branch agency is required by the Open Government Data Act of 2018 (and OMB M-13-13) to publish a public enterprise data inventory as a JSON document at `/data.json` on its primary domain, following the DCAT-US 1.1 schema. Data.gov harvests these endpoints on a regular cadence into the central CKAN catalog. The schema defines a Catalog containing Dataset records with required fields (`title`, `description`, `keyword`, `modified`, `publisher`, `contactPoint`, `identifier`, `accessLevel`, `bureauCode`, `programCode`) and optional distribution records.

- [Documentation — Resources.data.gov DCAT-US](https://resources.data.gov/resources/dcat-us/)
- [JSON Schema — Project Open Data v1.1](https://project-open-data.cio.gov/v1.1/schema/)
- [Source — Project Open Data Dashboard](https://github.com/GSA/project-open-data-dashboard)

### Data.gov Harvester (datagov-harvester)
The harvester service ingests dataset metadata from federal, state, local, and tribal `data.json` endpoints, CKAN sources, and CSW/WAF sources on a scheduled cadence and writes records into the central catalog. Publisher-facing service; source code is open at `GSA/datagov-harvester`.

- [Source — datagov-harvester](https://github.com/GSA/datagov-harvester)
- [Portal — harvest.data.gov](https://harvest.data.gov/)

### Inventory.data.gov CKAN API
A second CKAN 2.11 instance used by federal agencies as a publishing inventory before public release on catalog.data.gov. Same CKAN Action API surface; most actions require authorization for authenticated publishers.

**Base URL:** `https://inventory.data.gov/api/3/action`

- [Documentation — CKAN 2.11 API](https://docs.ckan.org/en/2.11/api/)
- [Source — inventory-app](https://github.com/GSA/inventory-app)

## Common Properties

- [GitHub](https://github.com/GSA/data.gov)
- [GitHub Organization — GSA](https://github.com/GSA)
- [Source — catalog.data.gov](https://github.com/GSA/catalog.data.gov)
- [Portal](https://data.gov/)
- [Catalog](https://catalog.data.gov/)
- [Documentation](https://resources.data.gov/)
- [Strategy](https://strategy.data.gov/)
- [Blog](https://data.gov/news/)
- [Twitter — @usdatagov](https://twitter.com/usdatagov)
- [Standards — DCAT-US](https://resources.data.gov/resources/dcat-us/)
- [Legislation — OPEN Government Data Act of 2018](https://www.congress.gov/115/plaws/publ435/PLAW-115publ435.pdf)
- [Contact](https://data.gov/contact/)
- [Privacy](https://data.gov/privacy-policy/)
- [Terms of Service](https://data.gov/privacy-policy/#data-policy)

## Maintainers

- **Kin Lane** — info@apievangelist.com
