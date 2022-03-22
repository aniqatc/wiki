## [🪴 View in the Comfort of My Digital Garden: Site Origin Values](https://www.aniqa.io/wiki/security/origin-values)

Breaking down the formatting of domains, subdomains and ports to understand if there are any security vulnerabilities.

---

### Origin Format

- **Scheme, or Protocol** = `https://` or `mailto:`
- **Hostname, or Domain** = `www.example.com`
- **Port** = `:443`

Origin could be [`cross-origin`](/wiki/security/cors) or [`same-origin`](/wiki/security/same-origin)

![](https://www.aniqa.io/static/6a279e3f3d733f57e0454b471ca4746c/bf608/origin.png)

### Site Format

- `TLD` = **Top-Level Domain** = `.com`
- `eTLD` = **Second-Level Domain** = `example.com`
- `eTLD+1` = **Subdomain** = `www.example.com`

Site could be `same-site` or `cross-site`

---

`Sec-Fetch-Site` is a **fetch metadata request header**: an HTTP request header that provides additional information about request origins

`Sec-Fetch-Site` *specifically* tells server whether a request for a resource is coming from the [1] **[same origin](/wiki/security/same-origin)**, [2] **same-site**, [3] **different site** or is a [4] **user-initiated** request and will allow server to allow or deny the request from being fulfilled

| Origin Source | Meaning |
| ----- | ----- | 
| `cross-site` | different domains |
| `same-site` | same domain (eTLD) but could have different ports, schemes, sub-domains | 
| `same-origin` | [must be exact match across scheme, hostname, and port](/wiki/security/same-origin) |
| `none` | user-originated operation (opening bookmark, entering URL to search bar) |

**Examples**:

- `cross-site`: **different domains**
    - https://www.example.com:443
    - https://www.different.com:443



- `same-site`:
    - **same site, different ports**
      - https://www.example.com:443
      - https://www.example.com:80
    - **same site, different schemes**
      - https://www.example.com:443
      - http://www.example.com:443
    - **same site, different subdomains**
      - https://www.example.com:443
      - https://login.example.com:443

---

Cross-Origin requires a separate entry: **[Cross-Origin-Resource-Sharing (CORS)](/wiki/security/cors)**

- `cross-origin` = different subdomain, ports, domains
