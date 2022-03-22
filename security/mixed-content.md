## [🪴 View in the Comfort of My Digital Garden: Security - Mixed Content](https://www.aniqa.io/wiki/security/mixed-content)

Understanding what type of websites are classified as Mixed Content and how to diagnose and remedy the issue.

---

## Definitions

➤ **Mixed Content** is when initial documents *(e.g. HTML source document)* are **loaded over a secure HTTPS connection**, displaying it to be *secure*, but other resources (images, stylesheets, scripts) **load in over an insecure HTTP connection**.

- Mixed Content: a website with resources loading from `HTTPS` and `HTTP`

- **Weakens security of the entire webpage** due to the request being vulnerable to on-path attacks (hackers can view + modify communications and documents between the website and browser)

➤ **Passive Mixed Content: images, video, audio, media** 
- content that does not interact with the rest of the page making any hacker *restricted* in what they are capable of doing, meaning, **they can only change the media but nothing beyond that**

➤ **Active Mixed Content: scripts, stylesheets, iFrames, any executable codes** 
- content that interacts with the entire page allows any attackers with potential to anything they want with the page, meaning, **they can literally replace whatever they want with malicious links, content, and scripts**

---

## Diagnose & Remedy

##### More Details Soon to Be Added

**Diagnosis?** Use **Chrome Developer Tools** and navigate to the **Security Panel** to find out all the origins of the webpage resources and whether or not the resources were loaded in over HTTPS, even the third-party ones. 

Each [**origin** location](/wiki/security/origin-values) will be displayed individually and will indicate if a resource is an original source or third-party and if the individual resource was loaded over `https://` or `http://` or both.

To better understand how the different resource links may compare and what the similarities and differences mean, read my breakdown on **[Domain Origin Values](/wiki/security/origin-values)**.

Or, the **Chrome Developer Tools** has another tool, the **Console Panel** could register a warning:

![](https://www.aniqa.io/static/619e198bf9d2e63c7a96a6370b931593/88b03/mixed-content.png)

**Solution? Ensure that all resources *(even if loaded from different sources)* are loaded over** `HTTPS`.
