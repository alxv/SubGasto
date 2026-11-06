# SubGasto App Privacy

**Product:** SubGasto  
**Bundle ID:** `com.subgasto.app`  
**Developer:** Alexandar Vincet Paulraj  
**Effective date:** 6 November 2026  
This is the App Privacy document for SubGasto. It is written for users and for App Store Review Guideline 5.1.1(i). It must stay consistent with the App Store privacy label (**Data Not Collected**, tracking **No**) and with `PrivacyInfo.xcprivacy`.

SubGasto is a local-first bill and subscription tracker for iPhone. It does not connect to your bank and is not financial advice. There is no SubGasto account and no SubGasto server.

## Privacy nutrition label (App Store)

| Question | Answer |
|---|---|
| Data used to track you | No |
| Data linked to you | None |
| Data not linked to you | None |
| Data Not Collected | Yes |

The privacy manifest declares:

- `NSPrivacyTracking` = false
- No tracking domains
- No collected data types
- UserDefaults access reason `CA92.1` (app functionality: remember settings and the lifetime unlock cache on this device)

`ITSAppUsesNonExemptEncryption` is **NO**. SubGasto does not use custom cryptography.

## What the app does not do

- Create a SubGasto account or require an email login
- Connect to a bank, card issuer, or email inbox
- Upload screenshots, statements, or charge lists to a SubGasto backend
- Include advertising, analytics, crash, or attribution SDKs
- Sell, rent, or share charge data with third parties
- Use App Tracking Transparency, because there is no tracking

## Information processed on this iPhone

All of the following stays in the app sandbox, and where needed for widgets or Share import, in the on-device App Group `group.com.subgasto.app`. Optional iCloud sync is **not** enabled in v1.

| Category | How it is collected | Why |
|---|---|---|
| Charges you enter or confirm | Typed, picked from the catalog, or confirmed after on-device OCR | Upcoming list, ledger, reminders, savings |
| Screenshots, PDFs, and CSV files you choose | Photos picker, Files, or the Share extension | On-device text recognition / parse. Nothing is saved until you review and tap Save selected |
| Notification preferences | You enable renewal reminders | Local alerts only. Not remote push |
| Lifetime unlock cache | Apple StoreKit, copied into UserDefaults / App Group | Remember the one-time purchase on this device |
| Optional Face ID or device passcode | System LocalAuthentication when you turn on lock | App lock. Lifetime feature |

## Permissions

| Permission | Required to use the app? | Purpose string / notes |
|---|---|---|
| Notifications | No | Local renewal reminders. Upcoming still works if you decline |
| Face ID | No | Optional app lock only. Purpose: lock SubGasto so charges stay private on this iPhone |
| Full Photo Library | Not requested | Import uses the system photos picker / share sheet, not a blanket library grant |

## On-device import

Screenshot and statement import uses Apple Vision on the files **you** pick. Recognition runs on the device. SubGasto does not send those images to a server. Detected rows are suggestions. You choose what to save.

## Widgets and Share extension

The Home Screen widget and the Share extension are part of SubGasto. They do not show ads and they do not sell in-app purchases. They may read or write a small snapshot or inbox file in the App Group on this iPhone so a shared screenshot can be imported, or so Upcoming can appear on the Home Screen.

## Purchases

Lifetime Unlock is a StoreKit 2 non-consumable in-app purchase (`com.subgasto.app.lifetime`). Apple processes the payment under Apple’s privacy policy. SubGasto never sees your card number. Restore Purchases uses your Apple ID. This is not a subscription, so there is no SubGasto cancellation step.

## Third parties

SubGasto does not share user data with analytics tools, advertising networks, or other SDKs. There is no parent or subsidiary service that receives charge data.

The only party that may receive purchase-related data is **Apple**.

If that practice ever changed, a recipient would have to provide the same or equal protection described here, and this document would be updated **before** any such sharing.

## Retention and deletion

- Charge data is kept on this iPhone until you delete it or delete the app.
- Delete charges in the app: **Settings → Delete all charges**.
- Delete everything SubGasto stored: delete the app. That removes the sandbox and the App Group files SubGasto created.
- Lifetime Unlock lives with your Apple ID. Restoring it does not require a SubGasto account.
- For deletion help, email **privacy@subgasto.app**. There is no server copy of your ledger. Data that exists only on a device we do not control can only be removed on that device.

## Children

SubGasto is not directed at children under 13.

## Contact

Developer: Alexandar Vincet Paulraj  
