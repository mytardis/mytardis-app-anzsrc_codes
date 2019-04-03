# mytardis-app-anzsrc\_codes
MyTardis app for adding F.O.R. codes to RIF-CS OAI-PMH feeds

Australian and New Zealand Standard Research Classification (ANZSRC), 2008: http://www.abs.gov.au/ausstats/abs@.nsf/0/6BB427AB9696C225CA2574180004463E

OAI-PMH metadata harvesting: https://www.ands.org.au/online-services/research-data-australia/rda-registry/oai-pmh-data-provider/oai-pmh-metadata-harvesting

## Installation

Assumes you have a working MyTardis installation: https://github.com/mytardis/mytardis

Clone this repository into an `anzsrc_codes` directory within `tardis/apps`

Add this app to `tardis/settings.py`:

```
INSTALLED_APPS += ('tardis.apps.anzsrc_codes',)
```

Copy the default settings from `tardis/default_settings/publication.py`
(see https://github.com/mytardis/mytardis) into your `tardis/settings.py`
and customize as needed.

In particular, set `RIFCS_TEMPLATE_DIR` to the path to `default.xml`, i.e.
`tardis/apps/anzsrc_codes/templates/rif-cs/profiles/default.xml`

The default RIF-CS profile in MyTardis in
`tardis/tardis_portal/templates/tardis_portal/rif-cs/profiles/default.xml`
is missing the ANZSRC F.O.R. codes provided by this `anzsrc_codes` app.

This app is largely unmaintained and has been removed from the main MyTardis
repository because of its rdflib dependency, which is currently listed as
insecure by https://pyup.io/, although it would appear that the vulnerability
only affects rdflib's Debian package.
