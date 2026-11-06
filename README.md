# SubGasto

Local-first iPhone ledger for bills and subscriptions.

See what renews, cancel in time, and never pay a subscription to manage subscriptions. Your list stays on this iPhone.

**Developer:** Alexandar Vincet Paulraj  
**Platform:** iPhone (iOS 26+)  
**Price:** Free for five active charges. Lifetime Unlock is one StoreKit payment (not a subscription).  
**Privacy:** [App Privacy](Docs/PRIVACY_POLICY.md)

SubGasto does not connect to your bank and is not financial advice.

## Description

People already use apps to track bills and cancel subscriptions, then get charged by *those* apps, lose the free tier, or cannot cancel cleanly.

SubGasto is a manual, on-device tracker for charges you already pay. You add Netflix, rent, and the gym from a catalog, or import an Apple Subscriptions screenshot. Upcoming sorts what hits next. Detail walks through cancel steps with a checklist and a link. Mark something canceled and see what you no longer pay.

There is no SubGasto account, no bank login, and no analytics SDK. OCR runs on the device. The upcoming list works without a purchase.

## Features

### Free

- Upcoming list sorted by days until renew (overdue, today, soon)
- Catalog of 250+ services with typical prices, brand color, and cancel URL
- Five active charges
- One reminder style (3 days before)
- One screenshot import
- First-run picks from popular services, or skip

### Lifetime Unlock (one-time)

- Unlimited active charges
- Full cancel checklists
- Reminders at 7, 3, 1 day and same day
- Unlimited screenshot and statement import, plus CSV
- Statement reconciliation (price hike, ghost charge, missing from statement)
- CSV / JSON export
- Home Screen widgets
- Optional Face ID / passcode lock
- Savings: what you still pay vs what you stopped paying

### Always on-device

- Share a screenshot or statement PDF into SubGasto
- Photos picker / Files import with review-before-save
- Restore Purchases for this Apple ID
- Privacy Policy and Standard EULA links in Settings, onboarding, and the paywall

## What is unique

1. **This app is not a subscription.** The job of the product is “see what renews.” That job stays free. Lifetime is one payment, restored with Apple ID.
2. **No bank login.** SubGasto does not use Plaid or open banking. You are not handing a finance app your accounts in order to list Netflix.
3. **On-device OCR instead of inbox scraping.** Settings → Apple ID → Subscriptions → screenshot → Import (or Share). Vision runs locally. You confirm rows before save.
4. **Cancel is a checklist, not a black box.** Catalog services ship with steps and a cancel URL. SubGasto does not claim to cancel the merchant for you.
5. **Statement cross-check.** After OCR, the app can flag a price that does not match your ledger, a statement charge you never added, or a ledger charge missing from the statement.
6. **Data Not Collected.** No account, no analytics SDK, no SubGasto server. Delete the app and the ledger is gone.

## Competitors vs SubGasto

Incumbents people already use for this job: Rocket Money, YNAB, Copilot, Monarch, PocketGuard, Hiatus, Spendee, EveryDollar, and manual trackers such as Bobby.

| | SubGasto | Rocket Money / Hiatus | Copilot / Monarch / PocketGuard | YNAB / EveryDollar / Spendee | Bobby-style manual apps |
|---|---|---|---|---|---|
| Bank or card login | No | Yes | Yes | Often yes | No |
| Core job behind a monthly fee | No. Upcoming is free | Often yes | Often yes | Yes (budgeting product) | Usually no |
| This app’s own subscription | None. Lifetime only | Common complaint in reviews | Common | Subscription is the product | Lifetime or paid up front |
| How charges appear | You add them, or screenshot OCR | Aggregation | Aggregation | You budget / import | You type them |
| Cancel help | Checklist + merchant URL you open | Concierge / negotiation (varies) | Limited | Not the product | Varies |
| Analytics / account | None | Account required | Account required | Account required | Usually none |
| Where data lives | This iPhone | Vendor cloud | Vendor cloud | Vendor cloud | Device |
| What it is not | Not a bank, not advice | Money-management service | Money-management service | Full budget | Same class as SubGasto |

**How SubGasto differs from aggregation apps:** it will not auto-detect every merchant from your checking account. That is the trade for no bank login and no hostage free tier.

**How SubGasto differs from other local trackers:** catalog with cancel steps, Apple Subscriptions screenshot import, Share extension, statement discrepancy checks, and a free Upcoming list capped at five charges instead of a trial that expires.

## Who it is for

Someone who already knows they pay Netflix, rent, and iCloud, wants the next 30 days on one screen, and does not want another monthly bill for the tracker.

## Who it is not for

- People who want Plaid / automatic bank sync
- People who want SubGasto to cancel Netflix for them
- Full envelope budgeting (use YNAB)
- Credit score, investing, or an AI spend coach
- Family sharing or Android in v1

## Stack

Swift 6, SwiftUI, SwiftData, StoreKit 2, UserNotifications, Vision, PDFKit, WidgetKit, App Group. IBM Plex Sans is bundled. No third-party analytics or networking SDKs.

## Open in Xcode

1. Open `SubGasto.xcodeproj`.
2. Select the **SubGasto** scheme.
3. Scheme → Run → Options → StoreKit Configuration → `SubGasto.storekit`.
4. Run on an iPhone simulator or device.

```bash
xcodebuild -scheme SubGasto -destination 'platform=iOS Simulator,name=iPhone 17' test
```

## Identifiers

| Item | Value |
|---|---|
| Bundle ID | `com.subgasto.app` |
| Widgets | `com.subgasto.app.widgets` |
| Share extension | `com.subgasto.app.share` |
| App Group | `group.com.subgasto.app` |
| Lifetime IAP | `com.subgasto.app.lifetime` |

## Docs

- [App Privacy](Docs/PRIVACY_POLICY.md)
- [App Store copy](Docs/AppStoreCopy.md)
- [App Store Connect](Docs/AppStoreConnectSetup.md)
- [App Review notes](Docs/AppReviewNotes.md)
- [Accessibility](Docs/Accessibility.md)
