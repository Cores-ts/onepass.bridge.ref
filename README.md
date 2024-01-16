# OnePass Bridge resources

This repository collects reference information and materials about the use case definition, user journeys, flows and credentials for the OnePass Bridge project.

- Credentials
- Actors
- Flows


# Credentials

## General Verifiable Credentials

| Verifiable Credential Name	| Link to the JSON Schema (if it already exists) |	Link to Examples |
| Natural person VerifiableId | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/natural-person/2022-11/schema.json | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/natural-person/2022-11/examples |
| Legal VerifiableId | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/legal-entity/2023-08/schema.json | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-vid/legal-entity/2023-08/examples |
| VerifiableAttestation | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-attestation/2023-10/schema.json | https://code.europa.eu/ebsi/json-schema/-/tree/main/schemas/ebsi-attestation/2023-10/examples |
| VerifiableAccreditationToAccredit | https://code.europa.eu/ebsi/json-schema/-/blob/main/schemas/ebsi-trust-model/2023-10/schema.json | https://code.europa.eu/ebsi/json-schema/-/blob/main/schemas/ebsi-trust-model/2023-10/examples/TI-accredited-to-attest.json |

## Domain-specific Verifiable Credentials

| Verifiable Credential Name	| Link to the JSON Schema (if it already exists) |	Link to Examples |
| KycChecksCredential |  | https://credentials.walt.id/credentials/kycdatacredential |
| KycDataCredential |  |  https://credentials.walt.id/credentials/kycdatacredential |
| KybChecksCredential |  |
| KybDataCredential |  |
| StartupMomentumCredential |  |

# Actors

## Trust Chain actors

| Actor               | Role           | Accredited to                                                                                                                                                                                                                                | Accredited by       | Additional Information |
|---------------------|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|------------------------|
| EBSI Support Office | Root TAO       | - (Accredit) Sub-TAO to accredit Trusted Issuers to Issue: [KYC,KYB,Onepass] VCs - (Issue): VerifiableAccreditationToAccredit                                                                                                                | Self                |                        |
| OnePass Consortium  | Sub-TAO        | - (Accredit) Sub-TAO to accredit Trusted Issuers to Issue: KycChecksCredential, KycDataCredential, KybChecksCredential, KybDataCredential, StartupMomentumCredential, Natural person VerifiableId, Legal VerifiableId, VerifiableAttestation | EBSI Support Office |                        |
| FundingBox          | Trusted Issuer | - (Issue): KycChecksCredential, KycDataCredential, KybChecksCredential, KybDataCredential, StartupMomentumCredential, Natural person VerifiableId, Legal VerifiableId                                                                        | OnePass Consortium  |                        |
| BIA                 | Trusted Issuer | - (Issue): KybChecksCredential, KybDataCredential, Legal VerifiableId                                                                                                                                                                        | OnePass Consortium  |                        |
| Accelerace          | Trusted Issuer | - (Issue): StartupMomentumCredential                                                                                                                                                                                                         | OnePass Consortium  |                        |
| WaltId              | Trusted Issuer | - (Issue): KycChecksCredential, KycDataCredential, Natural person VerifiableId, Legal VerifiableId                                                                                                                                           | OnePass Consortium  |                        |


## Trusted issuers

| Trusted Issuer |	Verifiable Credential to be issued |	Does it require accreditation? |
| FundingBox | KycChecksCredential, KycDataCredential, KybChecksCredential, KybDataCredential, StartupMomentumCredential, Natural person VerifiableId, Legal VerifiableId | OnePass Consortium | yes |
| BIA | KybChecksCredential, KybDataCredential, Legal VerifiableId | OnePass Consortium |  yes |
| Accelerace | StartupMomentumCredential | OnePass Consortium |  yes |
| WaltId | KycChecksCredential, KycDataCredential, Natural person VerifiableId, Legal VerifiableId | OnePass Consortium | yes |


# Flows

## Startup enrollment flow

The startup enrollment journey consists of seven independent flows, which are grouped into three main categories: Onboarding, Verification, and Workspace Setup. 

NOTE: As the OnePass Bridge pilot is accessible only through invitation, an optional flow is provided for users to request an invitation by completing a form. This particular flow is not yet covered here.

### Onboarding

- Sign in/Sign up
- Create a company profile

### Verification

- Eligibility check (This is a background job; shows a warning message if the organization is not eligible)
- Connect wallet (optional)
- User identity verification
- Business verification

### Workspace setup

- Create a workspace
- Create a data room

## List of figures





## Investor enrollment flow

TBD