# The Almanac
### Data Preservation & Monitoring

Public-interest data goes dark quietly — an agency is decommissioned, a URL rots, a
dataset moves and nobody updates the link. **The Almanac is open infrastructure that
maps where authoritative public datasets live, and watches whether they're still
reachable.**

We **catalog, we don't host.** Each entry points to a dataset's canonical source, its
archives, its license, and a continuously-checked reachability status. When something
goes dark, we know — automatically.

## Catalogs

- **[climate-almanac](https://github.com/almanac-data/climate-almanac)** — public
  climate datasets, after the climate.gov decommissioning.
  *(First catalog; more domains to follow.)*

## How it works

- **Preservation** — canonical-source and archive mapping (Wayback, S3), versioned and
  openly licensed (CC0 data / MIT tooling).
- **Monitoring** — a daily reachability probe that auto-files an issue when a source
  dies and closes it when the source recovers.

## Contribute

Built in the open. Whether it's a dataset to add, a dead link to report, or a whole new
domain to start — contributions are welcome. Start with
[climate-almanac](https://github.com/almanac-data/climate-almanac) or open an issue.
