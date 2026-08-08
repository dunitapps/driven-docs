---
layout: default
title: Driven Privacy Policy
---

# Driven Privacy Policy

**Effective date:** August 8, 2026  
**Last updated:** August 8, 2026  
**Version:** 1.0

This Privacy Policy explains how the Driven iOS application (the **“App”**) handles personal data. It applies to App bundle identifier `com.dunit.cardash` and to support communications sent to the address below. It does not replace the privacy terms of Apple or other independent services that the App makes available.

Driven is a driving aid, not a safety instrument. Please also read the [Driven Terms of Service](TERMS_OF_SERVICE.md), especially the sections about distracted driving and the limitations of speed, speed-limit, camera, route, and map information.

## 1. Controller and contact

The controller responsible for Driven is:

**Ilija Ivkovic**  
Belgrade, Republic of Serbia  
The controller is a private individual.  
Email: [contact@dunitapps.com](mailto:contact@dunitapps.com)

There is no separately appointed data protection officer, because Driven does not carry out the regular and systematic large-scale monitoring, or the large-scale special-category processing, that would require one. Privacy requests may be sent to the email address above with the subject **“Driven Privacy Request.”**

### 1.1 EEA and United Kingdom contact

The controller is established in Serbia and has not appointed a separate representative in the European Economic Area or the United Kingdom. Users in those regions may contact the controller directly at the address above. This statement does not waive any representative-appointment requirement that may apply under mandatory law.

## 2. Important summary

- Driven has no developer-operated account system, advertising network, behavioral analytics SDK, cross-app tracking SDK, or general-purpose developer backend.
- Most settings and content are stored in the App's private container on the device.
- Location, map searches, destinations, and routes are processed through Apple technologies when map or navigation features are used.
- If **Road Data Lookups** is enabled and paid road-data features apply, location-derived areas or sampled route coordinates are sent to public Overpass API services to retrieve OpenStreetMap speed-camera and road speed-limit data.
- RevenueCat receives an anonymous App User ID, purchase history, entitlement status, and limited technical information to validate purchases, provide subscription access, prevent fraud, and produce purchase analytics. Driven does not send location, contacts, calendar data, music data, or wallpaper photos to RevenueCat.
- With permission, Contacts and Calendar content is read for display on the device. Driven does not upload that content to a Driven server.
- Apple Music data is handled through MusicKit, MediaPlayer, and Apple services. Selected wallpaper photos remain on the device.
- Driven does not sell personal data and does not use personal data for third-party advertising or cross-context behavioral advertising.

“No developer-operated backend” does not mean that nothing leaves the device. Apple, RevenueCat, public Overpass operators, artwork hosts, telephone providers, external websites, and email providers process data in the circumstances described below.

## 3. Data handled by the App

### 3.1 Location, motion, map, and navigation data

When Location permission is granted and the App is in use, Driven may receive from iOS:

- latitude and longitude;
- altitude, course, and heading;
- GPS-derived speed;
- horizontal, vertical, heading, and speed accuracy values;
- timestamps and other Core Location status information; and
- whether precise or reduced-accuracy location is available.

The App uses this information to show the vehicle position, calculate and display speed, orient the map, search nearby places, obtain routes, guide navigation, reroute, match the device to a road, and generate road alerts.

GPS samples and the live speed calculation are normally processed in memory. Driven does not maintain a developer-side location-history database. The App does, however, store some location-related information locally, including saved and recent places, exact destination coordinates, an active navigation destination and route snapshot, and local road-data caches.

MapKit may send Apple information needed to render a map and answer a request, including the visible map area, search terms, selected places, origin, current location, destination, route details, transport mode, device and software information, time, and service interactions. Apple describes this processing in [Apple Maps & Privacy](https://www.apple.com/legal/privacy/data/en/apple-maps/) and [Location Services & Privacy](https://www.apple.com/legal/privacy/data/en/location-services/).

Map requests can occur when an Apple map or a static demonstration map is displayed even if the App does not have permission to use the device's live location.

### 3.2 Road Data Lookups: speed cameras and road speed limits

Road Data Lookups use OpenStreetMap data obtained through public Overpass API instances. The setting is enabled by default after the App's onboarding disclosure and can be disabled at any time in **Driven > Settings > Privacy > Road Data Lookups**. Disabling it stops Driven's Overpass requests and disables speed-camera and road speed-limit features. It does not stop Apple Maps processing that is necessary for map, search, or navigation features.

Speed-camera and road speed-limit lookups belong to the paid Driven Pro feature set, so these requests are normally sent only while paid access applies. During the short period after launch when entitlement status has not yet been confirmed, the App treats access as granted so that a subscriber is never cut off mid-drive, and a request can therefore be sent before that check completes. Turning Road Data Lookups off prevents the request in every case.

The data sent depends on how the App is being used:

- **Nearby driving without an active route.** Speed-camera lookups use a region snapped to a grid of approximately `0.05` degrees. Road speed-limit lookups use a smaller region snapped to a grid of approximately `0.0125` degrees. The query contains a bounding area centered on the grid cell, not the device's exact live coordinate. Grid-cell dimensions vary by latitude. This remains location-derived data and can reveal an approximate area.
- **Active navigation.** The App samples sections of the planned route and places coordinates in an Overpass query at up to six decimal places. The source GPS and route data are less accurate than that formatting may suggest, but the query can reveal the roads being traveled, an approximate origin or destination, and travel direction.

The App first contacts `overpass.private.coffee`, then may retry or fail over to `overpass.kumi.systems`, and finally may use `overpass-api.de`. One or more operators can therefore receive a request. Each operator necessarily processes the request content to return matching OpenStreetMap data and can also receive the source IP address, request time, HTTP method, endpoint, protocol and network information, and the App's User-Agent, which identifies Driven, its bundle identifier, the purpose of the request, and a contact page for the App. The App does not add a name, email address, Driven account, advertising identifier, RevenueCat identifier, contact, calendar item, or music identifier to an Overpass request.

Requests use HTTPS. That protects data in transit but does not prevent the receiving operator from processing it. Public-instance logging and retention practices differ and can change:

- [Private.coffee's Overpass notice](https://overpass.private.coffee/) currently states that it truncates source IP addresses, logs limited request metadata for up to 48 hours, and does not log GET parameters. Its notice does not eliminate the processing of a POST query needed to answer it.
- `overpass-api.de` uses IP addresses for rate limiting, and the Overpass software can maintain operational query logs. See the [Overpass public-instance documentation](https://dev.overpass-api.de/overpass-doc/en/preface/commons.html).

Public Overpass operators act under their own notices and operational rules. Driven cannot control their independent logs, legal disclosures, security, location, or retention.

Responses are cached on the device to reduce repeat network requests. Speed-camera cache entries can be used as fresh for up to 12 hours and, after a network failure, as stale for up to 7 days. Road speed-limit entries can be used as fresh for up to 7 days and as stale for up to 30 days. Each disk cache is pruned at approximately 25 MB and 30 days. Empty-result entries use shorter freshness periods. Cached data may include camera coordinates, OpenStreetMap identifiers, road geometry, speed tags, timestamps, and the endpoint used.

### 3.3 Saved places and local navigation state

Driven stores saved and recent places locally. Records can include a place name, subtitle or address, exact coordinate, Apple map-item identifiers, a custom name, icon or color, pin status, recent-use timestamps, and use count. While navigation is active, the App may also store the destination, route geometry, instructions, route metadata, and progress state so it can restore the session.

These records remain until deleted in the App, cleared or overwritten by App behavior, or removed with the App. They may be included in device backups according to the user's Apple backup settings.

### 3.4 Purchases and subscriptions

Apple processes App Store downloads, payments, refunds, subscription renewals, billing details, and the user's Apple Account under [App Store & Privacy](https://www.apple.com/legal/privacy/data/en/app-store/) and the applicable Apple Media Services terms. Driven does not receive full payment-card details.

The App uses [RevenueCat](https://www.revenuecat.com/privacy) to retrieve subscription offerings, validate Apple receipts and transactions, restore purchases, prevent fraud, determine entitlement access, and provide purchase and subscription analytics. At App launch, RevenueCat can receive or generate:

- a random, anonymous RevenueCat App User ID stored for the App on the device;
- Apple receipt, transaction, product, purchase, renewal, expiration, refund, trial, and entitlement information;
- device type, operating-system version, App version, locale, currency, network/IP information, request times, and last-seen information; and
- purchase and entitlement events needed for RevenueCat's customer history, charts, and service operation.

Driven does not set a custom user account ID and does not intentionally attach a name, email address, advertising identifier, location, contact, calendar item, music activity, or wallpaper to the RevenueCat profile. Purchase history is not used by Driven or RevenueCat for cross-app advertising tracking.

A limited entitlement snapshot—active status, expiration date, and the time recorded—is stored locally so paid access does not disappear during a short network interruption. Apple and RevenueCat keep transaction and fraud records under their own legal and contractual retention requirements.

### 3.5 Contacts and telephone calls

If Contacts permission is granted, Driven can read contact identifiers, formatted names or organization names, telephone numbers and labels, and available thumbnail images. This is used to display and search callable contacts on the device. The App does not persist the address book to disk and does not upload it to the developer, RevenueCat, or Overpass.

When the user chooses a number, Driven passes that number through a `tel:` link to the system Phone app. The system, mobile carrier, calling service, and call recipient may process the number and normal call metadata under their own terms. Driven does not record call audio or maintain a call log.

### 3.6 Calendar

If full Calendar access is granted, Driven reads non-cancelled events across the calendars on the device for the date range behind the agenda view. That range covers the week being displayed together with a surrounding window of roughly one week before and eight weeks after it, so past events within that window are read as well as upcoming ones. Data can include the event identifier, title, calendar name and color, start and end times, all-day and recurrence status, location, and notes. The App uses this content to show the agenda and event detail on the device. It does not intentionally write, edit, or delete calendar events and does not store event content in its own persistent database or send it to the developer, RevenueCat, or Overpass.

The user's configured calendar provider, such as iCloud or an Exchange provider, may independently sync and process calendar data outside Driven.

### 3.7 Apple Music, media library, and artwork

With the relevant Apple authorization, the App uses MusicKit and MediaPlayer to access and display music authorization and subscription capability, library playlists, songs, albums, artists, stations, recently played items, recommendations, catalog results, and playback state. Search text submitted to Apple Music is sent to Apple. Playback is performed by Apple's system music player.

Apple processes music-library, catalog, search, account, recommendation, and playback information as described in [Apple Music & Privacy](https://www.apple.com/legal/privacy/data/en/apple-music/). Driven does not send Apple Music data to the developer, RevenueCat, or Overpass.

The App stores limited playlist UI preferences locally, such as playlist identifiers, pin state, pin time, and local last-played state. Artwork returned by Apple or the media library may be downloaded from the artwork URL's host and cached locally. The host receives the ordinary network request, including the source IP address. Artwork disk caching is pruned at approximately 100 MB.

### 3.8 Wallpaper photos

Driven uses Apple's Photos Picker, so the user chooses the specific image made available to the App. The App does not request unrestricted access to the entire photo library for this feature. The selected image is resized, re-encoded as JPEG, and stored in the App's local Application Support directory together with crop/transform data. A smaller thumbnail of the same image is written to the App's caches directory, which iOS may clear on its own. The App does not intentionally preserve the original photo metadata and does not upload the image.

Up to 12 custom wallpapers are retained until the user deletes them or removes the App. The user is responsible for the content selected as described in the Terms of Service.

### 3.9 Preferences, local caches, and device state

Driven stores preferences and operational state in the iOS App container, including onboarding completion, selected dashboard and appearance, speed units, keep-screen-awake choice, road-data and camera settings, wallpaper selection, subscription-entitlement cache, music UI state, and a short-lived camera-alert session. A camera-alert session can contain a route key and up to 200 alerted camera identifiers and is ignored after 24 hours.

These items support App functionality, restore the user's choices, avoid repeat alerts, and control access. iOS can expose ordinary device and App technical information to Apple and enabled service providers when their services are called.

### 3.10 Support and legal communications

If a user emails `contact@dunitapps.com`, the developer and email provider receive the sender's name and email address, message, attachments, header and routing metadata, and any other information voluntarily provided. This data is used to answer the request, troubleshoot, protect the App and users, handle privacy or consumer requests, enforce the Terms, and comply with law.

Users should not send full payment-card numbers, passwords, unnecessary precise routes, contact lists, calendar exports, or other sensitive data in support email.

### 3.11 Diagnostics and App Store information

The release App contains no developer-added general analytics or crash-reporting SDK. Apple may independently process App Store activity and, depending on the user's Apple settings, device analytics, crash reports, and performance diagnostics. Apple may provide the developer with aggregated App Store metrics and limited diagnostics. This Apple-controlled processing is governed by Apple's privacy notices.

Driven uses local system logging for limited operational errors, such as RevenueCat configuration or road-data request failures. The App does not intentionally log live GPS coordinates, contact content, calendar content, music searches, or wallpaper images. Public road-cache keys or endpoint/error details can appear in device diagnostic logs.

## 4. Purposes and legal bases

Depending on the jurisdiction, Driven relies on the following legal bases:

| Purpose | Typical legal basis |
| --- | --- |
| Provide maps, location, speed, navigation, searches, road data, media, contacts, calendar, wallpaper, and user-requested features | Performance of the user agreement or steps taken at the user's request; consent or device permission where required |
| Send location-derived Overpass queries when Road Data Lookups is enabled | User choice/consent where required; performance of the requested road-data feature |
| Validate purchases, restore access, prevent purchase fraud, and operate subscription access | Performance of the user agreement; compliance with legal obligations; legitimate interests in securing and administering paid access |
| Maintain local settings, caches, session state, and service reliability | Performance of the user agreement; legitimate interests in reliable, secure, and efficient operation |
| Answer support, privacy, and consumer requests | Performance of the user agreement; legitimate interests in support; compliance with legal obligations |
| Establish, exercise, or defend legal claims; prevent abuse; comply with authorities | Legal obligation and legitimate interests in protecting legal rights and service security |

Where processing is based on consent, consent may be withdrawn at any time without affecting processing that was lawful before withdrawal. Some features will no longer work after permission or consent is withdrawn. Where legitimate interests are used, Driven balances those interests against the user's rights and expectations and limits the data to what is reasonably necessary.

Driven does not use personal data for a decision based solely on automated processing that produces legal or similarly significant effects. Subscription entitlement checks automatically determine access to paid App features, but do not make decisions about credit, employment, insurance, health, or legal status.

## 5. Recipients and independent services

Data is disclosed only as described in this Policy:

- **Apple:** App distribution, payment, StoreKit, MapKit, Core Location platform services, MusicKit, MediaPlayer, Photos Picker, device backup, system Phone, and optional Apple diagnostics. Apple generally acts under its own terms and privacy notices.
- **RevenueCat:** subscription processing, receipt validation, entitlement operation, fraud prevention, and purchase analytics. RevenueCat acts as a service provider/processor for developer customer data and also processes some information under its own legal obligations.
- **Private.coffee-operated Overpass domains (`overpass.private.coffee` and `overpass.kumi.systems`) and the `overpass-api.de` operators:** independent public services that answer road-data queries.
- **OpenStreetMap:** source of road, speed-limit, and speed-camera data. Driven reads data; it does not use the App to edit the user's OpenStreetMap account. OpenStreetMap data is licensed under ODbL. See [OpenStreetMap copyright](https://www.openstreetmap.org/copyright).
- **Artwork hosts:** receive ordinary image download requests for artwork URLs returned by Apple services.
- **Telephone carriers and calling services:** process calls deliberately initiated through the system Phone app.
- **Email provider:** processes support and legal correspondence.
- **Authorities or transaction participants:** only where disclosure is required by applicable law, necessary to protect rights or safety, needed for a corporate reorganization, or requested by the user. Any successor must honor this Policy for data it receives, subject to notice and law.

The App contains links that open Apple-managed views, Safari, or third-party sites. A visited site can receive the IP address, browser/device information, request time, referrer where applicable, and cookies or similar data under that site's policy.

## 6. Retention

Driven applies these general periods:

- **Live GPS and in-memory feature data:** for the active session or as long as needed to answer the immediate request, except for the local records described below.
- **Contacts and calendar content:** in memory while needed for the displayed feature; not intentionally persisted by the App.
- **Saved places, recent places, active navigation state, settings, music UI state, and wallpapers:** until deleted, cleared, overwritten, or the App is removed. Wallpaper thumbnails sit in the caches directory and may also be cleared by iOS at any time.
- **Speed-camera and road speed-limit disk caches:** pruned at approximately 30 days and 25 MB per cache; data shown as stale uses the shorter limits described in Section 3.2.
- **Artwork cache:** subject to eviction and an approximate 100 MB cap.
- **Camera-alert session:** ignored after 24 hours and limited to 200 camera identifiers.
- **RevenueCat and transaction data:** for as long as needed to operate or document the subscription, meet fraud, tax, accounting, dispute, and legal duties, and under the RevenueCat agreement and provider notices. Apple can retain purchase records for longer statutory periods.
- **Support correspondence:** normally up to 24 months after the matter is closed, and longer only when reasonably necessary for an unresolved dispute, security incident, legal claim, or mandatory recordkeeping period.

Removing the App deletes its active iOS container from the device, but copies may remain temporarily in Apple-controlled device backups or provider systems under their separate retention rules. The developer cannot remotely locate or delete data that exists only inside the user's App container.

## 7. User choices and controls

- **Location:** change access, including Precise Location, in **iOS Settings > Privacy & Security > Location Services > Driven**. Core map and driving features may not work without location.
- **Road Data Lookups:** turn the setting off inside Driven to stop Overpass location-derived requests. This does not disable Apple Maps processing.
- **Speed Camera Alerts:** turn alerts off independently. Road speed-limit lookups can continue if Road Data Lookups remains enabled.
- **Contacts, Calendar, Apple Music, and media access:** revoke access in iOS Settings. Permission can also be declined when requested.
- **Wallpaper:** delete custom images in the App. Removing the App deletes active local copies from the device container.
- **Saved places and routes:** remove saved items or end/replace navigation where the App provides those controls. Removing the App clears the remaining active local store.
- **Subscription:** manage or cancel through the Apple subscription-management interface. Cancellation stops future renewal but does not itself erase transaction records.
- **All local App data:** remove the App from the device, subject to backup caveats above.

## 8. Rights

Subject to applicable law and exceptions, a user may request:

- confirmation and access to personal data controlled by the developer;
- correction of inaccurate data;
- deletion;
- restriction of processing;
- data portability;
- objection to processing based on legitimate interests;
- withdrawal of consent; and
- information about recipients and international safeguards.

Send requests to [contact@dunitapps.com](mailto:contact@dunitapps.com). A user in the EEA or the United Kingdom may instead contact the representative named in Section 1.1. The developer may need to verify the request and may ask for the anonymous RevenueCat App User ID or limited transaction evidence where the request concerns a subscription. Do not send full card information. Because Driven has no account and most data is stored only on the device, the developer may have no way to identify or retrieve that local data.

Requests are answered without undue delay and ordinarily within 30 days, subject to extensions and exceptions permitted by law. A user may complain to the [Serbian Commissioner for Information of Public Importance and Personal Data Protection](https://www.poverenik.rs/en/) or, where applicable, the supervisory authority in the user's country or region.

Residents of jurisdictions with additional privacy rights may exercise them through the same contact. Under United States state privacy laws, that includes the rights to know what personal information is collected and to whom it is disclosed, to obtain a copy, to correct it, to delete it, and to appeal a refused request. Section 3 sets out the categories of personal information the App handles, the purpose of each, and the recipients; Section 6 sets out retention.

Driven will not discriminate against a user for making a valid privacy request. Driven does not sell personal data, does not share it for cross-context behavioral advertising, and does not use or disclose sensitive personal information for a purpose that would create a right to limit that use. There is accordingly no sale, sharing, or limitation opt-out to process.

## 9. International processing

The controller is in Serbia. Apple, RevenueCat, public Overpass operators, content delivery hosts, and email infrastructure can process data in Serbia, the European Economic Area, the United States, and other countries where they or their service providers operate. Those countries can have different privacy laws.

Where the developer appoints a processor and a restricted international transfer applies, the developer relies on an approved legal mechanism where required, such as contractual safeguards, and evaluates supplementary measures as appropriate. Independent providers determine their own transfer mechanisms under their notices. Public Overpass failover services do not provide the same contractual guarantees as a dedicated developer-controlled processor, and users can stop those transfers by disabling Road Data Lookups.

## 10. Security

The App uses iOS sandboxing, platform permission controls, HTTPS for direct Overpass requests, platform network-security controls for artwork downloads, local file protection provided by iOS, data minimization, and limited dependencies. No system is completely secure. The developer cannot guarantee the security or uninterrupted availability of a device, backup, carrier, public API, Apple service, RevenueCat, external website, or email transmission.

Users should secure their device with an appropriate passcode, keep iOS and the App updated, review permissions, and avoid including sensitive information in support messages.

## 11. Children

Driven is a driving-oriented product and is not directed to children under 16. A minor may use the App only with the involvement and authorization of a parent or legal guardian and only where lawful. The developer does not knowingly seek a child's contact, calendar, location, music, or photo data for advertising or profiling. A guardian who believes a child supplied data to the developer may contact [contact@dunitapps.com](mailto:contact@dunitapps.com).

## 12. Changes to this Policy

This Policy may be updated to reflect App changes, providers, law, or security practices. The date and version will be changed, and material changes will be presented through the App, App Store listing, policy page, or another reasonable channel where required. If a new purpose requires consent, consent will be requested before that processing begins.

## 13. Contact

Questions, complaints, and requests about this Policy may be sent to:

**Ilija Ivkovic**  
Belgrade, Republic of Serbia  
[contact@dunitapps.com](mailto:contact@dunitapps.com)

Users in the EEA and the United Kingdom may contact the controller directly at this address.
