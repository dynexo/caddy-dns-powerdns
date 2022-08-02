powerdns module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with powerdns.

## Caddy module name

```
dns.providers.powerdns
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "powerdns",
				"api_token": "YOUR_PROVIDER_API_TOKEN",
				"server": "YOUR_PROVIDER_SERVER_ADDRESS"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns powerdns ...
}
```

```
# one site
tls {
	dns powerdns ...
}
```
