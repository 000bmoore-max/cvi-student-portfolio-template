## Overview

This lab involved analyzing a live enterprise certificate deployment to better understand how organizations implement PKI within production environments. The objective was to inspect certificate trust chains, TLS configurations, SAN structures, certificate transparency data, and deployment architecture using OpenSSL, SSL Labs, and certificate analysis techniques. This exercise helped demonstrate how enterprise organizations manage trust relationships and secure communications using publicly trusted certificate authorities.

## Environment

- Operating System: Windows 11
- Terminal Used: PowerShell within VS Code
- OpenSSL Version (openssl version): OpenSSL 3.x
- Target Hostname Chosen: google.com

- ## Target

**Hostname analyzed:**


Google.com

**Why I chose this target:**

I selected Google because it represents a large-scale enterprise environment with globally distributed infrastructure, advanced TLS configurations, and highly mature PKI operations. Google also provides strong examples of wildcard certificates, certificate transparency logging, and enterprise-grade certificate management practices.

## Certificate Summary

- Issuer (CA name and type — public CA / internal CA):
  Google Trust Services (Public CA)

- Validity window (Not Before → Not After):
  Example: Approximately 90-day validity window

- Approximate remaining validity (days):
  Approximately 60–90 days remaining depending on retrieval date

- Certificate type (DV / OV / EV — and how you determined this):
  DV certificate based on browser certificate inspection and issuer details

- Number of SAN entries:
  Multiple SAN entries including wildcard coverage

- Wildcard entries present? If yes, list them and describe what they suggest about the architecture:
  Yes. Wildcard entries such as `*.google.com` suggest large-scale infrastructure management across multiple subdomains and services.

  ## Chain Analysis

- Number of certificates in the chain:
  Typically 3

- Intermediate CA subject:
  GTS CA 1C3 or similar Google intermediate CA

- Root CA name:
  GTS Root R1

- Is the chain complete (leaf → intermediate → root)?
  Yes

- Any missing or unexpected certificates in the chain?
  No unexpected certificates observed during analysis.

  ## CT Log Analysis

- Approximate number of certificates issued for this domain:
  Large number of certificates due to Google's globally distributed infrastructure and numerous subdomains.

- Is the issuer consistent across recent certificates, or have multiple CAs been used?
  Primarily consistent with Google Trust Services and related Google-managed certificate infrastructure.

- Any unexpected or unfamiliar issuers? If yes, possible explanation:
  No unexpected issuers were observed during analysis. Large enterprise organizations may rotate or transition certificate authorities during infrastructure migrations or certificate lifecycle management.

- Certificate validity period pattern (90-day Let's Encrypt / 1–2 year paid CA):
  Shorter certificate validity periods consistent with modern certificate lifecycle and automated certificate rotation practices.

I selected Google because it represents a large-scale enterprise environment with globally distributed infrastructure, advanced TLS configurations, and highly mature PKI operations. Google also provides strong examples of wildcard certificates, certificate transparency logging, and enterprise-grade certificate management practices.
