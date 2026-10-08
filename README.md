# Kelvia — AI skincare label scanner

> Point the camera at a product's ingredient list and see, ingredient by ingredient, whether it suits **your** skin.

**iOS** · [App Store](https://apps.apple.com/us/app/kelvia-skincare-scanner/id6807114731) · Designed and built end to end by [İbrahim Melikşah Köse](https://github.com/meliksahkose) at [MelberLabs](https://melberlabs.com)

<p>
  <img src="https://is1-ssl.mzstatic.com/image/thumb/PurpleSource211/v4/5f/1c/31/5f1c312e-d3fd-0f5c-2c4f-36c56a0289c1/01-02-scan-hub.png/320x480bb.jpg" width="24%" alt="Scan hub" />
  <img src="https://is1-ssl.mzstatic.com/image/thumb/PurpleSource221/v4/bb/23/b0/bb23b06f-3304-cd86-be1b-79d1a39e175e/02-01-onboarding.png/320x480bb.jpg" width="24%" alt="Onboarding" />
  <img src="https://is1-ssl.mzstatic.com/image/thumb/PurpleSource211/v4/08/1f/e2/081fe222-f45c-2cca-9a97-1c7678087635/03-03-name-entry.png/320x480bb.jpg" width="24%" alt="Search by name" />
  <img src="https://is1-ssl.mzstatic.com/image/thumb/PurpleSource211/v4/a7/4d/13/a74d13c9-4634-a985-1ebf-fa3dc46f8e96/04-04-confirm.png/320x480bb.jpg" width="24%" alt="Confirm ingredients" />
</p>

## What it does
- **Skin profile** from four questions and an optional face scan.
- **Label scan or name search**: the app reads the INCI ingredient list and shows a compatibility score with the reason behind every point.
- **Routine guardrails**: morning/evening routine with warnings for known active-ingredient clashes (e.g. retinoids with exfoliating acids or benzoyl peroxide).
- **Shelf**: every scanned product stays searchable for the next store visit.
- **Safety first**: not a medical app. Photos that look like they need a professional get no analysis and a "see a dermatologist" message.

## Engineering decisions
- **The AI reads, the rules decide.** A vision model only extracts ingredients from the photo. The score is computed **on the phone by a deterministic rule engine** from the recognised ingredients and the user's profile, so the same product and profile always get the same, explainable score.
- **Refuses to guess.** If a label can't be read reliably, the app says so instead of inventing ingredients.
- **Fair monetisation.** Weekly free credits and auto-renewing Premium subscriptions (monthly and yearly, 3-day trial). Results are never paywalled and there are no ads or accounts.

---
<sub>Source code is private. Happy to walk through the architecture and code in an interview: meliksahkose90@gmail.com</sub>
