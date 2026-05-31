# Arrow Puzzle Privacy Policy GitHub Pages Package

This package contains static files for publishing the Arrow Puzzle privacy policy from a public GitHub Pages repository. It is a draft package until a human or PM publishes it and records the final public URL.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Root GitHub Pages entry that redirects to `privacy-policy.html`. |
| `privacy-policy.html` | Public-facing static HTML privacy policy. |
| `privacy-policy.md` | Markdown source for PM/legal review and future edits. |
| `README.md` | Package notes and publish handoff. |

## Evidence Used

- Support contact is `g1854003@gmail.com`.
- `Assets/ArrowPuzzle/Compliance/MVP/privacy_consent_text.csv` states progress/settings are stored on device and ads, purchases, and achievements are stubbed.
- `Assets/ArrowPuzzle/Compliance/MVP/sdk_disclosure_matrix.csv` marks local save as implemented and ads, purchases, restore, and achievements as stub states.
- `Assets/ArrowPuzzle/Operations/MVP/crash_log_policy.tsv` states no crash SDK is connected in the MVP seed.
- `Assets/ArrowPuzzle/Scripts/Runtime/Feature/Common/Services/SaveDataRepository.cs` and `SaveData.cs` show local progress/settings/onboarding/purchase/ad-count/achievement state stored through local save data.
- Service defaults use local stubs or null sinks when live ad/analytics clients are not registered.

## Assumptions

- This policy describes the current public MVP build only.
- Live third-party ads, real-money IAP, external achievement services, analytics SDKs, crash SDKs, cloud save, and account sign-in are not release-connected for this policy package.
- Local ad-removal, ad-count, and achievement state are treated as on-device game state, not as proof of live third-party services.
- The final public privacy policy URL is still pending and must not be marked resolved until the package is published and verified.

## Publish Target

- Public repository: `https://github.com/koyotap-official/ArrowNext`
- Expected GitHub Pages root: `https://koyotap-official.github.io/ArrowNext/`
- Expected privacy policy URL: `https://koyotap-official.github.io/ArrowNext/privacy-policy.html`
- Verification on 2026-05-31 JST: repository returned `200 OK`; expected privacy policy URL returned `404 Not Found`.

The policy URL is not store-ready until the files in this folder are published to the repository or configured Pages branch and the expected privacy URL returns `200 OK`.

## Publish Handoff

1. Copy all files in this folder into the public GitHub Pages repository or Pages branch.
2. Enable GitHub Pages for that repository/branch.
3. Verify that the final URL serves `privacy-policy.html` publicly without authentication or geo-blocking.
4. Run the follow-up PM task for resolving `human.privacy_policy_url` with the verified URL, owner, and publish timing.

Do not update store privacy disclosures to claim live ads, purchases, analytics, crash reporting, cloud save, or platform achievements unless those services are actually connected and reviewed.
