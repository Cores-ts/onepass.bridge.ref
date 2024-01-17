# OnePass Bridge resources

This repository collects reference information and materials about the use case definition, user journeys, flows and credentials for the OnePass Bridge project.

- Credentials
- Actors
- Flows


# Credentials

## Generic Verifiable Credentials

| Verifiable Credential Name	| Link to the JSON Schema (if it already exists) |	Link to Examples |
|---|---|---|
| Natural person VerifiableId | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/natural-person/2022-11/schema.json | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/natural-person/2022-11/examples |
| Legal VerifiableId | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/legal-entity/2023-08/schema.json | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/legal-entity/2023-08/examples |
| VerifiableAttestation | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-attestation/2023-10/schema.json | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-attestation/2023-10/examples |
| VerifiableAccreditationToAccredit | https://code.europa.eu/ebsi/json-schema/-/blob/main/schemas/ebsi-trust-model/2023-10/schema.json | https://code.europa.eu/ebsi/json-schema/-/blob/main/schemas/ebsi-trust-model/2023-10/examples/TI-accredited-to-attest.json |

## Domain-specific Verifiable Credentials

| Verifiable Credential Name	| Link to the JSON Schema (if it already exists) |	Link to Examples |
|---|---|---|
| KycChecksCredential |  | [Example](credentials/KycChecksCredential/examples/example.json) |
| KycDataCredential * |  |  [Example](credentials/KycDataCredential/examples/example.json) |
| KybChecksCredential |  |
| KybDataCredential * |  |
| StartupMomentumCredential |  |

NOTE: KycDataCredential and KybDataCredential may be replaced by Natural person VerifiableId and Legal VerifiableId (TBC)

# Actors

## Trust Chain actors

| Actor | Role | Accredited to| Accredited by |
|---|---|---|---|
| EBSI Support Office | Root TAO | - (Accredit) Sub-TAO to accredit Trusted Issuers to Issue: [KYC,KYB,Onepass] VCs - (Issue): VerifiableAccreditationToAccredit | Self | |
| OnePass Consortium | Sub-TAO | - (Accredit) Trusted Issuers to Issue: KycChecksCredential, KycDataCredential, KybChecksCredential, KybDataCredential, StartupMomentumCredential, Natural person VerifiableId, Legal VerifiableId, VerifiableAttestation | EBSI Support Office |
| FundingBox | Trusted Issuer | - (Issue): KycChecksCredential, KycDataCredential, KybChecksCredential, KybDataCredential, StartupMomentumCredential, Natural person VerifiableId, Legal VerifiableId | OnePass Consortium  |
| BIA | Trusted Issuer | - (Issue): KybChecksCredential, KybDataCredential, Legal VerifiableId | OnePass Consortium |
| Accelerace | Trusted Issuer | - (Issue): StartupMomentumCredential | OnePass Consortium  |
| WaltId | Trusted Issuer | - (Issue): KycChecksCredential, KycDataCredential, Natural person VerifiableId, Legal VerifiableId | OnePass Consortium  |  


## Trusted issuers

| Trusted Issuer |	Verifiable Credential to be issued |	Does it require accreditation? |
|---|---|---|
| FundingBox | KycChecksCredential, KycDataCredential, KybChecksCredential, KybDataCredential, StartupMomentumCredential, Natural person VerifiableId, Legal VerifiableId | yes |
| BIA | KybChecksCredential, KybDataCredential, Legal VerifiableId | yes |
| Accelerace | StartupMomentumCredential |  yes |
| WaltId | KycChecksCredential, KycDataCredential, Natural person VerifiableId, Legal VerifiableId | yes |


# Flows

## [Startup enrollment flow](screen-flows/startup-enrollment-flow)

The startup enrollment journey consists of seven independent flows, which are grouped into three main categories: Onboarding, Verification, and Workspace Setup. 

NOTE: As the OnePass Bridge pilot is accessible only through invitation, an optional flow is provided for users to request an invitation by completing a form. This particular flow is not yet covered here.

### [Onboarding](screen-flows/startup-enrollment-flow/1-onboarding)

- Sign in/Sign up - [screen flow](screen-flows/startup-enrollment-flow/1-onboarding/1.1-sign-up)
- Create a company profile - [screen flow](screen-flows/startup-enrollment-flow/1-onboarding/1.2-create-organization-profile)

### [Verification](screen-flows/startup-enrollment-flow/2-verification)

- Eligibility check (This is a background job; shows a warning message if the organization is not eligible) - [eligibility warning](screen-flows/startup-enrollment-flow/2-verification/2.0-eligibility-check/2.0.1-eligibility-warning.png)
- Connect wallet (optional) - [screen flow](screen-flows/startup-enrollment-flow/2-verification/2.1-connect-wallet)
- User identity verification - [screen flow](screen-flows/startup-enrollment-flow/2-verification/2.2-KYC)
  - KYCDataCredential issuance - [screen flow](screen-flows/startup-enrollment-flow/2-verification/2.4-KYB)
- Business verification - [screen flow](screen-flows/startup-enrollment-flow/2-verification/2.4-KYB)
  - KYBDataCredential issuance  - [screen flow](screen-flows/startup-enrollment-flow/2-verification/2.5-KYB-credential-issuance) 

### [Workspace setup](screen-flows/startup-enrollment-flow/3-workspace-setup)

- Create a workspace
- Create a data room  - [screen flow](screen-flows/startup-enrollment-flow/3-workspace-setup/3.2-create-data-room)

## Investor enrollment flow

TBD


---


# Links

- [WaltId - Kyc compliance dapp example](https://dapp.walt.xyz/)