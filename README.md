# Arrow Next GitHub Pages Package

This package contains static files for publishing Arrow Next store compliance files from a public GitHub Pages repository. The current public URLs are intended for store metadata and AdMob verification use.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Root GitHub Pages entry that redirects to `privacy-policy.html`. |
| `app-ads.txt` | Public AdMob authorized seller declaration for app-ads.txt verification. |
| `privacy-policy.html` | Public-facing static HTML privacy policy. |
| `privacy-policy.md` | Markdown source for PM/legal review and future edits. |
| `README.md` | Package notes and publish handoff. |

## Evidence Used

- Support contact is `g1854003@gmail.com`.
- `ProjectSettings/ProjectSettings.asset` sets product name to `Arrow Next` and company name to `KoyoTap`.
- `Assets/ArrowPuzzle/Compliance/MVP/privacy_consent_text.csv` states progress/settings are stored on device.
- `Assets/ArrowPuzzle/Compliance/MVP/sdk_disclosure_matrix.csv` records the published privacy policy URL.
- `Assets/ArrowPuzzle/Operations/MVP/OPERATIONS_INDEX.md` states Firebase Analytics logging is enabled only when the Firebase sink, define, and SDK are present, and AdMob is enabled only when the AdMob client, define, and Google Mobile Ads plugin are present.
- `Assets/ArrowPuzzle/Scripts/Runtime/Feature/Common/Services/SaveDataRepository.cs` and `SaveData.cs` show local progress/settings/onboarding/purchase/ad-count/achievement state stored through local save data.
- `Assets/ArrowPuzzle/Scripts/Runtime/Feature/Common/Services/AdMobAdNetworkClient.cs` and `FirebaseAnonymousAnalyticsSink.cs` show production-facing adapters for ads and analytics when enabled.

## Assumptions

- This policy is production-facing and covers the expected public app scope: local save data, ads, in-app purchases, analytics/diagnostics, store platforms, and support.
- The app does not currently require a KoyoTap account or cloud save.
- Store Data Safety and App Privacy answers must still be matched to the exact SDKs and platform services enabled in the submitted build.
- The final public privacy policy URL is published and verified as `https://koyotap-official.github.io/ArrowNext/privacy-policy.html`.
- The app-ads.txt entry is intended to be publicly served for AdMob verification.

## Publish Target

- Public repository: `https://github.com/koyotap-official/ArrowNext`
- Expected GitHub Pages root: `https://koyotap-official.github.io/ArrowNext/`
- Expected app-ads.txt URL from this project page: `https://koyotap-official.github.io/ArrowNext/app-ads.txt`
- Expected privacy policy URL: `https://koyotap-official.github.io/ArrowNext/privacy-policy.html`
- Initial policy commit: `7b36cbaf079bc53818c747a27c9f52efbd0b973b`
- Latest branch-deploy cleanup commit: `416fae54da7614605bf3a1f6832f1fd688754cda`
- Latest production-policy content commit: `fdc3f6019f6c112fbfefaa0bb22e86a021b92039`
- Verification on 2026-05-31 JST: repository returned `200 OK`; expected privacy policy URL returned `200 OK`. No GitHub Actions workflow is required for this one-time static policy page.

The policy URL is store-ready as a hosted URL. Policy content must still be kept aligned with the exact live ads, real-money IAP, analytics, diagnostics, cloud save, account, or platform achievement integrations enabled in the submitted build.

## Publish Handoff

1. Use `https://koyotap-official.github.io/ArrowNext/privacy-policy.html` in store metadata and release checklists.
2. Use `https://koyotap-official.github.io/ArrowNext/app-ads.txt` only when the verifier accepts the project-page path; AdMob may require `https://koyotap-official.github.io/app-ads.txt` at the host root.
3. Keep `privacy-policy.md` and `privacy-policy.html` aligned when SDK/provider or real IAP scope changes.
4. Re-verify that the final URLs serve publicly without authentication or geo-blocking before store submission.

Do not update store privacy disclosures to claim a specific provider or data type unless that provider or data handling is actually connected and reviewed for the submitted build.
