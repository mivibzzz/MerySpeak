# MerySpeak.com
Online Monitoring and Alerts
## Project Overview

[MerySpeak.com](https://MerySpeak.com) is a website monitoring SaaS application that tracks uptime, response times, SSL certificates, security headers, page changes, and domain expiration for user websites.

### Technology Stack

| Category | Technology |
|----------|------------|
| **Framework** | Flask 3.0.0 |
| **Database** | SQLite with SQLAlchemy 2.0.23 ORM |
| **Background Jobs** | APScheduler 3.10.4 with ThreadPoolExecutor |
| **Payments** | Stripe 7.8.0 |
| **HTTP Client** | Requests 2.31.0, HTTPX 0.26.0 |
| **SSL/Crypto** | Cryptography 41.0.7, PyOpenSSL 23.3.0 |
| **DNS/Domain** | DNSPython 2.4.2, python-whois 0.8.0 |
| **Email** | Gmail SMTP |
| **Frontend** | Vanilla JavaScript, Chart.js |

## Uptime Monitoring

MerySpeak provides continuous uptime monitoring to ensure your website or API remains online and responsive. We perform automated checks at regular intervals and notify you immediately when issues occur—so you can respond before users are affected.

### How It Works

MerySpeak follows a simple and reliable monitoring process:

1. **HTTP Requests**  
   Our servers send scheduled HTTP GET requests to your website.

2. **Response Analysis**  
   We verify response status codes and confirm successful responses (2xx).

3. **Status Updates**  
   Your site status is updated in the dashboard as **UP** (green) or **DOWN** (red).

4. **Instant Alerts**  
   Email notifications are sent immediately when status changes occur.

5. **Incident Logging**  
   All downtime events are logged with timestamps for historical analysis.

### Understanding Uptime Percentages

Uptime is measured as the percentage of time your site is available during a given period:

| Uptime   | Downtime / Month | Downtime / Year | Rating    |
|----------|------------------|-----------------|-----------|
| 99.999%  | 26 seconds       | 5 minutes       | Excellent |
| 99.99%   | 4 minutes        | 52 minutes      | Excellent |
| 99.9%    | 43 minutes       | 8.7 hours       | Good      |
| 99%      | 7.2 hours        | 3.6 days        | Fair      |
| 95%      | 36 hours         | 18.2 days       | Poor      |

For most production websites and APIs, an uptime of **99.9% or higher** is recommended. MerySpeak automatically tracks this metric and provides clear visibility into availability and outages.
____________________________________________________________


## Response Time Analytics

MerySpeak’s response time analytics help you monitor website performance and ensure fast, reliable user experiences. By tracking how quickly your server responds to requests, you can detect slowdowns early, analyze trends, and maintain optimal performance.

### What Is Response Time Monitoring?

Response time monitoring measures how fast your server responds to incoming requests. While uptime monitoring confirms availability, response time monitoring reveals performance quality. A website can be online but still deliver a poor experience if it loads slowly.

MerySpeak measures **Time To First Byte (TTFB)** on every check, capturing the time from request initiation to the first byte received. This metric reflects backend performance and processing speed.

Pro users gain access to advanced analytics, including historical trends, averages, percentiles, and alerts when response times exceed defined thresholds.

### Key Features

- **Real-Time Tracking**  
  Response time measured with every check, up to 1,440 data points per day with 1-minute monitoring.

- **Trend Analysis**  
  Visualize performance trends across 24 hours, 7 days, and 30 days.

- **Percentile Metrics**  
  95th percentile calculations highlight worst-case performance.

- **Performance Alerts**  
  Get notified when response times spike or consistently exceed acceptable limits.

### Response Time Benchmarks

Understanding response time targets helps you maintain strong performance:

| Response Time | Rating      | User Experience                         |
|---------------|-------------|-----------------------------------------|
| Under 100ms   | Excellent   | Feels instant to users                  |
| 100–200ms     | Good        | Quick and responsive                    |
| 200–500ms     | Acceptable  | Noticeable but tolerable                |
| 500ms–1s      | Slow        | Users notice the delay                  |
| Over 1 second | Poor        | Frustrating, high bounce risk           |

### Analytics Dashboard

The MerySpeak analytics dashboard provides key performance metrics:

- **Current Response Time** – Most recent measurement  
- **Average Response Time** – Mean values over selected time periods  
- **Minimum / Maximum** – Best and worst recorded response times  
- **95th Percentile** – Performance better than 95% of measurements  
- **Trend Charts** – Visual performance graphs over time  
- **Anomaly Detection** – Automatic identification of unusual spikes  

### Use Cases

- **Performance Optimization**  
  Measure the impact of code changes, server upgrades, or infrastructure improvements.

- **SLA Compliance**  
  Track performance against contractual response time guarantees.

- **Capacity Planning**  
  Detect degradation under increased load and scale resources proactively.

- **Third-Party Impact Assessment**  
  Identify slowdowns caused by external services such as APIs, CDNs, or databases.

### Why Response Time Matters

- **User Experience**  
  Faster sites reduce frustration and bounce rates, improving visitor satisfaction.

- **SEO and Rankings**  
  Page speed is a ranking factor in search engines, including Google’s Core Web Vitals.

- **Conversion Rates**  
  Faster load times lead to higher conversions and improved revenue performance.
____________________________________________________________



## SSL Certificate Monitoring

MerySpeak helps you avoid unexpected SSL certificate expirations by continuously monitoring your certificates and alerting you well before they expire. This ensures your website remains secure, trusted, and accessible without browser security warnings.

### What Is SSL Certificate Monitoring?

SSL certificate monitoring checks the validity and expiration dates of the SSL/TLS certificates installed on your websites. These certificates enable HTTPS by encrypting data between visitors and your server.

When a certificate expires, modern browsers display prominent security warnings that discourage users from proceeding. MerySpeak regularly checks your certificates, tracks issuers and expiration dates, and sends email alerts **14+ days before expiration**, giving you ample time to renew without disrupting visitors.

### Key Features

- **Expiry Tracking**  
  View exactly how many days remain before certificate expiration.

- **Early Warnings**  
  Receive email alerts 14 days in advance to renew on time.

- **Issuer Information**  
  Track the Certificate Authority that issued each certificate.

- **Validity Status**  
  Instantly see whether a certificate is valid, expiring soon, expired, or misconfigured.

### Why SSL Certificates Expire

SSL certificates have limited lifespans for security reasons. Browser vendors now enforce a maximum validity of **398 days**, ensuring:

- Cryptographic freshness  
- Domain ownership revalidation  
- Reduced risk from compromised certificates  
- Adoption of stronger encryption algorithms  

Free certificates (such as Let’s Encrypt) typically expire every **90 days**. While auto-renewal is common, failures can occur, making monitoring essential.

### Certificate Status Levels

| Status          | Days Remaining      | Action Required                     |
|-----------------|---------------------|--------------------------------------|
| Valid            | More than 14 days   | No action needed                     |
| Expiring Soon    | 14 days or less     | Renew certificate                    |
| Expired          | 0 or negative       | Urgent: Site shows warnings          |
| Error            | N/A                 | Check certificate installation       |

### Use Cases

- **E-commerce Security**  
  Prevent checkout disruptions and maintain customer trust.

- **Multi-Site Management**  
  Monitor certificates across multiple websites from one dashboard.

- **Let’s Encrypt Renewal Failures**  
  Detect auto-renewal issues before certificates expire.

- **Compliance Requirements**  
  Meet security standards such as PCI-DSS with continuous certificate validation.

### Impact of Expired SSL Certificates

Expired certificates can cause immediate and serious issues:

- Browser security warnings  
- Lost sales and transactions  
- SEO ranking penalties  
- API and webhook failures  
- Email delivery disruptions  
- Mobile app connection failures  
- Loss of user trust  

____________________________________________________________



## Page Change Detection

MerySpeak monitors your web pages for unexpected or unauthorized content changes. It instantly detects modifications such as defacements, injected code, or unplanned updates, allowing you to investigate and respond quickly.

### What Is Page Change Detection?

Page change detection tracks modifications to your website’s HTML content. During each check, MerySpeak generates a **SHA256 cryptographic hash** of the page. This hash acts as a unique fingerprint—any change to the content, even a single character, produces a different hash.

When a change is detected, the event is logged with a timestamp and an email alert can be sent. This helps you determine whether the change was expected or potentially malicious.

### Key Features

- **Content Hashing**  
  SHA256 hashing ensures accurate detection of any content changes.

- **Instant Alerts**  
  Receive email notifications as soon as page changes are detected.

- **Change History**  
  Review detected changes over the last 24 hours, 7 days, and 30 days.

- **Security Monitoring**  
  Quickly identify defacements, malware injections, or unauthorized edits.

### How It Works

1. **Content Download**  
   MerySpeak fetches the page HTML during each monitoring check.

2. **Hash Generation**  
   A SHA256 hash is created from the downloaded content.

3. **Comparison**  
   The new hash is compared to the previously stored hash.

4. **Change Detection**  
   If the hashes differ, a `PAGE_CHANGE` event is recorded.

5. **Alert Dispatch**  
   An email notification is sent so you can investigate immediately.

### Use Cases

- **Security Breach Detection**  
  Detect website defacements or malicious content injections quickly.

- **Compliance & Auditing**  
  Maintain an audit trail of when content changes occurred.

- **Competitor Monitoring**  
  Track changes to competitor pages such as pricing or promotions.

- **Deployment Verification**  
  Confirm that new content was successfully deployed.

- **Content Integrity**  
  Protect critical pages from accidental or unauthorized changes.

### What Changes Are Detected?

MerySpeak detects any modification to page HTML, including:

- Text additions, removals, or edits  
- HTML structure and layout changes  
- Link additions, removals, or URL changes  
- Image URL changes  
- Script additions or modifications  
- Form field or action changes  
- Meta tag and SEO-related updates  

**Note:** Pages with frequently changing dynamic content (such as timestamps or personalized data) may trigger frequent alerts. For best results, monitor pages with stable content.
____________________________________________________________



## Domain Expiry Monitoring

MerySpeak helps protect your online presence by monitoring domain registration status, tracking expiration dates, and detecting DNS changes. You’ll receive early alerts so your domains never expire unexpectedly or fall into the wrong hands.

### What Is Domain Expiry Monitoring?

Domain expiry monitoring ensures your domain names remain registered and under your control. If a domain expires, your website, email, and brand identity can disappear instantly.

MerySpeak queries **WHOIS databases** to retrieve expiration dates, registrar details, and registration metadata. Email alerts are sent **30 days before expiration**, giving you time to renew without disruption.

In addition to expiration tracking, MerySpeak monitors DNS records to detect unexpected configuration changes that may indicate misconfiguration or hijacking attempts.

### Key Features

- **Expiry Tracking**  
  Monitor domain expiration dates with 30-day advance warnings.

- **WHOIS Data**  
  View registrar details, creation dates, and registration information.

- **DNS Monitoring**  
  Track changes to A, AAAA, CNAME, MX, TXT, and NS records.

- **Renewal Alerts**  
  Receive email notifications before domains expire.

### Why Domain Monitoring Matters

When a domain expires, it follows a lifecycle that can quickly make recovery difficult or impossible:

- **Grace Period (0–45 days)** – Domain can still be renewed (often with late fees)  
- **Redemption Period (45–75 days)** – Domain is suspended and costly recovery fees apply  
- **Pending Delete (5 days)** – Domain cannot be recovered  
- **Available for Registration** – Anyone can register the domain  

Consequences of domain expiration include:

- Complete website downtime  
- Email delivery failures  
- SEO ranking loss  
- Brand or domain hijacking  
- Lost customers and revenue  
- Expensive redemption fees  

### DNS Records Monitored

MerySpeak tracks critical DNS record types:

| Record Type | Purpose                         | Why Monitor                          |
|-------------|---------------------------------|--------------------------------------|
| A           | Maps domain to IPv4 address     | Detect server IP changes or hijacking |
| AAAA        | Maps domain to IPv6 address     | Track IPv6 configuration changes     |
| CNAME       | Domain aliases                  | Ensure CDN and subdomain integrity   |
| MX          | Mail server routing             | Detect email delivery issues         |
| TXT         | SPF, DKIM, verification records | Monitor email authentication changes |
| NS          | Nameserver delegation           | Detect unauthorized DNS control      |

### Use Cases

- **Multi-Domain Portfolios**  
  Manage and track multiple domains across different registrars.

- **Client Website Management**  
  Stay ahead of client domain expirations with proactive alerts.

- **DNS Security**  
  Detect unauthorized DNS changes and potential hijacking attempts.

- **Brand Protection**  
  Ensure critical and defensive domains remain under your control.
____________________________________________________________

## Security Headers Analysis

MerySpeak analyzes your website’s HTTP security headers and provides clear, actionable recommendations to strengthen your security posture. It checks for essential headers, calculates a security grade, and helps protect your site against common web attacks.

### What Are Security Headers?

HTTP security headers are response headers sent by your web server that tell browsers how to handle your site’s content. They enable browser-side protections against many common vulnerabilities.

Without proper security headers, websites may be exposed to:

- Clickjacking attacks  
- Cross-site scripting (XSS)  
- Man-in-the-middle attacks  
- MIME-type confusion  
- Information leakage to third parties  

MerySpeak scans your headers, assigns a security score, and highlights what needs improvement.

### Headers We Check

MerySpeak analyzes seven essential security headers:

1. **Strict-Transport-Security (HSTS)**  
   Forces HTTPS connections and prevents SSL stripping attacks.  
   Example: `max-age=31536000; includeSubDomains`

2. **Content-Security-Policy (CSP)**  
   Restricts which resources can load, helping prevent XSS attacks.  
   Example: `default-src 'self'; script-src 'self'`

3. **X-Frame-Options**  
   Prevents clickjacking by controlling iframe embedding.  
   Values: `DENY`, `SAMEORIGIN`

4. **X-Content-Type-Options**  
   Prevents MIME-type sniffing attacks.  
   Recommended value: `nosniff`

5. **X-XSS-Protection**  
   Enables legacy browser XSS filtering.  
   Recommended value: `1; mode=block`

6. **Referrer-Policy**  
   Controls how much referrer data is shared.  
   Recommended: `strict-origin-when-cross-origin`

7. **Permissions-Policy**  
   Restricts access to browser features like camera or geolocation.  
   Example: `geolocation=(), camera=(), microphone=()`

### Security Grades

MerySpeak assigns a grade based on header coverage:

| Grade | Score      | Meaning                                      |
|------|------------|----------------------------------------------|
| A    | 90–100%    | Excellent – Strong security header coverage  |
| B    | 80–89%     | Good – Minor improvements possible           |
| C    | 70–79%     | Acceptable – Several headers missing         |
| D    | 60–69%     | Poor – Significant security gaps             |
| F    | Below 60%  | Critical – Urgent action required            |

### Use Cases

- **Security Audit Preparation**  
  Identify and fix basic security gaps before audits or penetration tests.

- **Compliance Requirements**  
  Meet baseline expectations for frameworks like PCI-DSS, SOC 2, and HIPAA.

- **Development Best Practices**  
  Ensure deployments don’t accidentally remove critical headers.

- **Client Website Assessments**  
  Provide clear security grades and recommendations to stakeholders.

### Implementing Security Headers

Security headers are usually configured at the web server level.

**Apache (.htaccess)**

Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains"
Header always set X-Frame-Options "SAMEORIGIN"
Header always set X-Content-Type-Options "nosniff"
Header always set Referrer-Policy "strict-origin-when-cross-origin"
____________________________________________________________




## Status Page Widget

Build trust with your visitors by displaying real-time service status on your website. MerySpeak’s embeddable status widget shows current uptime, availability, and recent incidents at a glance.

### What Is a Status Widget?

A status page widget is a lightweight, embeddable component that displays your service’s operational status in real time. Instead of users guessing whether your site is down, they can instantly see availability, uptime percentage, and recent incidents.

MerySpeak’s widget requires only **one line of code**, updates automatically every **60 seconds**, and works on any website. It supports both light and dark themes to match your design.

The widget displays:
- **Current Status** – Green *Operational* or red *Down* indicator  
- **Uptime Percentage** – Recent availability metrics  
- **Last Incident** – Timestamp of the most recent outage  

### Key Features

- **Real-Time Updates**  
  Automatically refreshes every 60 seconds without page reloads.

- **Light & Dark Themes**  
  Match your website’s visual style.

- **Easy Embedding**  
  Single JavaScript snippet — copy and paste.

- **No Dependencies**  
  Fully self-contained, no external libraries required.

### How to Embed the Widget

1. **Get Your Widget Code**  
   Log in to your MerySpeak dashboard, select a website, and click **Get Embed Code**.

2. **Add to Your HTML**  
   Paste the script tag into your page HTML (footer or status section recommended).

3. **Customize (Optional)**  
   Set `data-theme="dark"` for dark mode or keep `light` as default.

### Embed Code Example

```html
<script src="https://meryspeak.com/static/js/embed.js"
        data-website-id="YOUR_WEBSITE_ID"
        data-theme="light"></script>
````

Replace `YOUR_WEBSITE_ID` with the ID from your dashboard. The widget renders automatically where the script is placed.

### Widget Themes

* **Light Theme**
  White background with dark text
  `data-theme="light"`

* **Dark Theme**
  Dark background with light text
  `data-theme="dark"`

### Use Cases

* **SaaS Dashboard Footer**
  Reduce “is it down?” support tickets with visible status.

* **Dedicated Status Page**
  Create a public `status.yoursite.com` page for transparency.

* **Marketing Website**
  Showcase uptime metrics to build customer trust.

* **Documentation Sites**
  Help developers quickly verify service availability.

### Why Display Public Status?

Public status information offers clear benefits:

* Builds customer trust through transparency
* Reduces support requests
* Demonstrates confidence in reliability
* Differentiates you from competitors
* Sets clear expectations during incidents
* Encourages higher operational standards

### Widget API

The widget uses a public API endpoint that you can also access directly for custom integrations.

**Endpoint**

```
GET /api/widget/{website_id}
```

**Response**

```json
{
  "success": true,
  "data": {
    "status": "up",
    "uptime_24h": 100.0,
    "uptime_7d": 99.95,
    "uptime_30d": 99.87,
    "last_checked": "2025-01-15T10:30:00Z",
    "last_incident": "2025-01-10T08:15:00Z"
  }
}
```

CORS is enabled, allowing this endpoint to be accessed from any domain.


____________________________________________________________



## Email Alerts & Notifications

Stay informed about your website’s status with MerySpeak’s instant email alerts. Receive notifications when your site goes down, recovers, or when SSL certificates are nearing expiration, along with weekly performance summaries.

### How Alerts Work

MerySpeak’s alert system notifies you of important events without overwhelming you. You receive one email per incident: when your site goes down and when it comes back up. This keeps you informed while avoiding redundant messages.

### Alert Types

- **🚨 Downtime Alerts** – Instant notification when your site is unreachable or returns an error.  
- **✅ Recovery Alerts** – Notification when your site is back online, including outage duration.  
- **🔒 SSL Expiry Warnings** – Alerts 14 days before SSL certificates expire (Pro feature).  
- **📋 Weekly Digest** – Summary of uptime, incidents, and performance trends sent every Monday.  

### Downtime Alert Details

Emails include:

- Website name and URL  
- Detection time  
- Error details (HTTP status or connection issues)  
- Direct link to the website details in your dashboard  

**Example:**

```

Alert: Website Down
Website: My Company Website
URL: [https://example.com](https://example.com)
Status: DOWN
Detected: January 15, 2025 at 10:30 AM UTC
Error: Connection timeout after 30 seconds

```

### Recovery Alert Details

Emails include:

- Confirmation site is back online  
- Recovery time  
- Outage duration  
- Current response time  

**Example:**

```

Resolved: Website Back Up
Website: My Company Website
URL: [https://example.com](https://example.com)
Status: UP
Recovered: January 15, 2025 at 10:45 AM UTC
Outage Duration: 15 minutes
Response Time: 245ms

```

### Weekly Digest Report

Sent every Monday, the digest summarizes:

- Overall uptime percentage  
- Incident count per site  
- Total downtime  
- Performance trends (response times)  
- SSL certificate status (Pro)  

This keeps your team informed without daily logins.

### Configuring Notifications

Adjust preferences in your account settings:

- **Email Notifications Toggle** – Enable/disable all email alerts.  
- **Weekly Digest Toggle** – Choose whether to receive the Monday summary.  

*Tip:* Keep downtime alerts enabled for immediate incident awareness.

### Alert Delivery

MerySpeak ensures reliable delivery:

- Immediate dispatch within seconds of detection  
- High deliverability via proven email infrastructure  
- Clear subject lines for easy identification  
- One alert per incident start and one per recovery  

**Delivery Tips:**

- Add `noreply@meryspeak.com` to contacts or safe sender list  
- Check spam/junk folders if alerts are missing  
- Ensure your account email is correct  
- Consider filters to highlight MerySpeak alerts  

### Use Cases

- **On-Call Response** – Forward alerts to on-call emails or integrate with PagerDuty/Opsgenie.  
- **Team Visibility** – Share alerts via a group email alias for full team awareness.  
- **Executive Reporting** – Send weekly digests to stakeholders who need high-level uptime visibility.  
- **Compliance Documentation** – Archive alert emails for auditing and compliance records.

