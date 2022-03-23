## [🪴 View In My Digital Garden: Same-Origin Policy](https://www.aniqa.io/wiki/security/same-origin)

Basic definition of the same-origin policy to better understand other online security vulnerabilities.

---


**[Origin](/wiki/security/origin-values)** - defined by hostname, port, scheme.
- **All three must be the same to be considered** `same-origin`

**Same-Origin Policy: browser security feature** - ensures documents that interact on the *origin* server must all be **sourced from the same server** 
- Restricts [cross-origin sharing](/wiki/security/cors) between different [eTLDs (domains)](/wiki/security/origin-values)

---

`same-origin` is a value [(among others)](/wiki/security/origin-values) for the `Sec-Fetch-Site` [HTTP metadata request header](/wiki/security/origin-values) that is tasked with identifying where a resource is originating and if the request should be completed
