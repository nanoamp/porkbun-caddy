Porkbun module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with porkbun.

## Caddy module name

```
dns.providers.porkbun
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "porkbun",
				"api_key": "YOUR_PROVIDER_API_TOKEN",
				"secret_api_key": "SECRET_API_TOKEN"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns porkbun {
		api_key pk..
		secret_api_key sk..
	}
}
```

```
# one site
tls {
	dns porkbun {
		api_key pk..
		secret_api_key sk..
	}
}
```
