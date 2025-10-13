# Contribution rules

> [!WARNING]
If you violate these rules, you will be banned from interacting with the repository for a year. So pay attention.

---

## 1. No anti consumer services

This repository is maintained for consumers and that these custom destinations are trustworthy, safe, and reasonable.

> All future submissions are required to have a clear **Terms of Service** that includes:
>
> - A description of the service’s purpose and intended use.
> - Rules of acceptable and prohibited use.
> - Details on account termination or content removal policies.
> - Any limitations of liability and disclaimers.
> - Information on user rights and obligations.
> - Under no circumstances are uploaders allowed  
> - Contact information for support or legal inquiries.

> Additionally, all submissions must include a **Privacy Policy** that clearly explains:
>
> - What data is collected (e.g., IP address, uploaded content, analytics).
> - How that data is used and for what purpose.
> - Whether any data is shared with third parties and under what circumstances.
> - How long data is retained and how users can request deletion.
> - What security measures are in place to protect user data.
> - How users will be notified of policy changes.

> **Important:** Any hosts or services whose Terms of Service or upload policies **transfer ownership of user content** or apply a **broad, unrestricted (“asterisk”) license** that effectively allows them to use, modify, redistribute, or sell uploaded images without clear user consent are **strictly disallowed**.  
> Only services that preserve full user ownership and provide limited, purpose-bound usage rights (e.g., for hosting or display) will be accepted.

> **Notice Requirement:** If possible, hosts should **notify users at least 14 days in advance** when hosting of images will no longer be possible, such as when the service is shutting down or going defunct. This ensures users have time to retrieve or migrate their content.

### 2. Service Quality and Reliability

To maintain a list of dependable upload destinations, all submitted image hosts must demonstrate a reasonable level of quality, stability, and performance.

#### Minimum Requirements

- **Uptime:** Services should be up for at least 90% of the time over a long period of time. If you have a lot of downtime or service interruptions, you will be removed.
- **Performance:** Uploads and image retrieval should complete within a reasonable time frame for typical broadband connections (~[240 Mbps](https://tachus.com/internet-speeds-usa-vs-the-rest-of-the-world/)). Extremely slow services will not be accepted.
- The service must use a **registered custom domain name** that the operator owns and controls.  
   Dynamic DNS providers that offer free subdomains (like `example.ddns.net` or `something.weebly.com`) are not acceptable.
- The domain must have at least one year left on its registration or show that it plans to renew.  
   Submissions that use domains that are about to expire, don't have valid WHOIS information, or have a history of lapses will be turned down.
- Mentioned domains must use **valid HTTPS** with a properly configured SSL/TLS certificate. Expired or self-signed certificates are not allowed.
- Image links must be publicly accessible without captchas for viewing. Files that are *intended* to be secret are excluded from this rule.

#### Disallowed Practices

- **Placeholder or Non-Functional APIs:** Services that are just demos, placeholders, or proof-of-concepts and don't actually host anything are not allowed.
- **Projects that aren't being maintained or are no longer useful:** Hosts that don't show any signs of maintenance, version updates, or stability in their domain ownership won't be accepted.
- **Aggressive Advertising or Tracking:** Services that put annoying ads, pop-ups, or heavy analytics scripts on image URLs are not allowed.
- **Upload Size Requirements:** For a host to be useful for normal use, it must be able to handle uploads of at least **6 MB per file**.  
   If a service has stricter limits or only accepts smaller files, it will be **rejected** unless there is a clear and good reason for it (for example, a service that is only for thumbnails or compressed previews).

#### Recommendation

Before submitting, contributors should verify that the service:

1. Can handle uploads and retrievals reliably under normal load.
2. Does not break existing `.sxcu` configurations unexpectedly.
3. Is likely to remain operational for the foreseeable future.

The goal is to ensure transparency, user control, and responsible data handling for all accepted upload destinations.

### 3. Naming Format Guidelines

The file name and custom uploader name should be just domain with lowercase:

**File name:** `example.com.sxcu`  
**Custom uploader name field:** `example.com`

Because ShareX automatically uses `Request URL` domain when the name field is empty, generally name field should be just kept empty.

Both file name and custom uploader name field output should be identical.

---

### 4. Multiple Service Handling

If you are going to pull request one host with multiple services then append that info within brackets as below to avoid conflict:

`example.com (Image uploader).sxcu`  
`example.com (URL shortener).sxcu`

If you are going to pull request only one service then there won't be conflict, and there must not be any brackets.

Going forward, submissions that include **separate `.sxcu` files for the same service** (for example, one for authenticated uploads requiring an API key and another for anonymous uploads using a different endpoint) are **disallowed**.  

Hosts should recognize that this practice is confusing and unnecessary. Instead:

- Use the **same endpoint** for both authenticated and anonymous uploads.
- If no API key is provided, or the provided key is invalid, the upload should be treated as **anonymous**.
- The API response should clearly indicate this by including a message such as `"API key invalid, upload treated as anonymous"` in the response body.
- Exceptions can be made, but only with good reason.

### 6. File Export Requirements

Please note that `.sxcu` file must be exported from latest version of SnapX OR ShareX and not made manually using text editor.
