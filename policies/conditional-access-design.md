
# Conditional Access Policy Design — Contoso Financial Services

## Objective
Design Conditional Access controls for Finance users and simulated privileged administrators in Microsoft Entra ID.

## Policy 1: Finance MFA
- Name: CA-Require-MFA-Finance
- Include: CA-Finance-Users
- Exclude: Designated emergency-access accounts
- Target resources: All resources
- Grant: Require multifactor authentication
- Initial mode: Report-only

## Policy 2: Privileged phishing-resistant authentication
- Name: CA-Privileged-Phishing-Resistant
- Include: CA-Privileged-Admins
- Exclude: Designated emergency-access accounts
- Target resources: All resources
- Grant: Require phishing-resistant authentication strength
- Initial mode: Report-only
- Prerequisite: Users must register a supported phishing-resistant authentication method

## Validation Plan (not executed)
1. Review emergency-access exclusions and confirm account recovery procedures.
2. Use the Conditional Access What If tool to evaluate selected users and sign-in conditions.
3. Review report-only results in sign-in logs.
4. Pilot changes with designated test users before considering enforcement.

## Licensing Limitation
The lab tenant uses Microsoft Entra Free. Conditional Access policy creation is unavailable without the required licensing. These policies are documented designs only; they were not deployed or validated in the tenant.
  
