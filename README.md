# Google Ads Developer Token Upgrade Guide

## Purpose

This document outlines the detailed process for requesting an upgrade of a Google Ads Developer Token from **test** mode to **Standard** mode. The upgrade supports system integration with the Google Ads API for:

- Campaign management  
- Budget management  
- Account access and permission control  

---

## Prerequisites

- A valid **Google Ads Manager Account (MCC)**
- A Google Cloud Console project configured with **OAuth 2.0 credentials**
- A **Developer Token** already created (in test or pending state)
- **Google Ads API enabled**: [Google Ads API Center](https://ads.google.com/aw/apicenter)

---

## Application Description (For Submission)

| Field                         | Value                                                                 |
|------------------------------|-----------------------------------------------------------------------|
| **Application Name**         | SmartAds Campaign Management Platform                                 |
| **Application Type**         | Internal application for in-house operations                         |
| **Purpose of API Usage**     | Internal campaign management and optimization for company/client use |

### Key Functionalities

- **Campaign Management**  
  Create, update, enable/disable campaigns  
  Retrieve performance metrics (impressions, CTR, CPC, conversions)

- **Budget Management**  
  Set and update campaign budgets  
  Monitor and adjust budget allocations

- **Account Access Control**  
  Send access invitations  
  Manage roles (ADMIN, STANDARD) via the API

---

## Target Users

Only **internal employees and business collaborators**.  
The system is **not distributed** to external users or the public.

---

## OAuth 2.0 & Access Flow

- Uses OAuth 2.0 for user authentication/authorization
- Users log in via Google to grant access to their Ads accounts
- OAuth consent screen displays: `SmartAds Auth Gateway`

---

## System Workflow with Google Ads API

1. User logs in via OAuth 2.0
2. System retrieves accessible Google Ads accounts
3. User selects an account → `customer_id` is stored
4. From there, the system allows:
   - Managing campaigns (CampaignService)
   - Updating budgets (CampaignBudgetService)
   - Sending access invitations (CustomerUserAccessInvitationService)
   - Fetching reports (GoogleAdsService)

---

## Developer Token Upgrade Steps

### Step 1: Go to Developer Token Settings

- Visit: [Google Ads API Center](https://ads.google.com/aw/apicenter)
- Log in using the MCC account that owns the developer token

### Step 2: Request Standard Access

Fill out the form with the following details:

| Field                                            | Sample Input                                                                 |
|--------------------------------------------------|------------------------------------------------------------------------------|
| **Application name**                             | SmartAds Campaign Management Platform                                       |
| **How will your app use the Google Ads API?**    | Internal platform to manage campaigns, budgets, and account access          |
| **Who will use your app?**                       | Internal employees only (not publicly available)                            |
| **Will your app be used on behalf of clients?**  | Yes (or only for our company accounts, as applicable)                       |
| **Use of third-party platforms?**                | No                                                                          |

---

## Notes

- Make sure your application description aligns with actual functionality.
- Ensure all users accessing via OAuth are listed under your MCC or invited through access control.

