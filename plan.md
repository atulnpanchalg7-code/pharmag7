# PHARMA-G7 — वेबसाइट अंमलबजावणी व डिझाइन प्लॅन

## उत्पादनाचा सारांश

PHARMA-G7 ही S.Y. BCA प्रोजेक्ट डेमोसाठी तयार केलेली **Smart Online Pharmacy Management System** ची polished academic prototype वेबसाइट असेल. ती online pharmacy shopping flow आणि pharmacy administration workflow दोन्ही दाखवेल. ही साइट diagnosis, medical recommendation किंवा automated prescription approval देणार नाही.

## अंमलबजावणीची दिशा

- **Frontend-first prototype:** HTML, CSS आणि vanilla JavaScript वापरून install/build complexity कमी ठेवायची.
- **Responsive single-page experience:** Home, Medicines, About/Safety, Contact आणि Admin Dashboard हे sections एका स्पष्ट navigation flow मध्ये.
- **Demo interactions:** medicine search/filter, category chips, add-to-cart, quantity update, cart drawer, demo checkout, prescription upload simulation, dashboard tab switching आणि toast feedback.
- **Data layer:** सध्या realistic in-memory demo data; database/authentication/payment integration यांना पुढील academic phase साठी स्पष्ट extension points.
- **Route manifest:** `/manus-routes.json` मध्ये `/` हा पूर्ण सध्याचा page route घोषित करायचा.
- **Serving:** project root मधून port 3000 वर `0.0.0.0` bind करणारा छोटा Node static server.

## डिझाइन दिशा

### Design Movement

**Editorial healthcare commerce** — modern SaaS dashboard clarity आणि premium pharmacy trust यांचा संगम. UI marketplace सारखा उपयोगी, पण clinic-grade संयमी आणि जबाबदार दिसेल.

### Core Principles

1. **Trust before conversion:** pharmacist review, safe-use notes आणि prototype disclaimer हे CTA पेक्षा लपवले जाणार नाहीत.
2. **Scan-friendly hierarchy:** मोठे section labels, compact metadata, clear pricing आणि distinct status badges.
3. **Calm precision:** रंग, spacing आणि micro-interactions मोजके; clutter किंवा generic stock imagery टाळायची.
4. **Useful motion:** cart count, drawer, filter आणि toast interactions subtle spring/fade transitions ने स्पष्ट करायच्या.

### Color Philosophy

Deep navy/ink हा clinical reliability आणि data clarity दाखवेल. Signature brand color म्हणून **electric aqua-teal** वापरला जाईल—digital access, cleanliness आणि active states साठी. Warm cream/sand surfaces UI ला institutional न वाटता approachable ठेवतील; coral फक्त warnings/expiry alerts साठी.

### Layout Paradigm

साध्या centered grid ऐवजी **asymmetric editorial split** वापरायचा: hero मध्ये copy + trust metrics एक बाजूला आणि abstract medicine-card composition दुसऱ्या बाजूला; catalog मध्ये filter rail + product list; dashboard मध्ये compact sidebar + dense but breathable data panels.

### Signature Elements

- डाव्या बाजूला aqua-teal vertical brand rail/marker.
- Capsule-shaped status pills आणि medicine metadata “spec rows”.
- प्रत्येक मोठ्या section साठी numbered eyebrow labels (`01 / Browse`, `02 / Review`, `03 / Deliver`).

### Interaction Philosophy

प्रत्येक action ने system state स्पष्ट दाखवायची: Add to cart नंतर count आणि toast, cart उघडल्यावर order summary, prescription upload नंतर “Pending pharmacist review”, dashboard मध्ये low-stock/expiry states. Invalid/unsafe assumptions न करता copy मध्ये योग्य guardrails दाखवायचे.

### Animation

- Page load: content blocks 40–80ms staggered fade/slide-in.
- Hover: product cards 2px lift, image tile हलका scale.
- Cart drawer: right-to-left spring-like transform, backdrop fade.
- Filter/search: results update instant; result count आणि empty state crossfade.
- Respect `prefers-reduced-motion`.

### Typography System

- **Display:** `Space Grotesk` — crisp, technical, confident headings.
- **Body/UI:** `DM Sans` — approachable readability for dense pharmacy data.
- Eyebrows uppercase with letter spacing; body 15–17px; prices and KPIs use tabular numerals.

### Brand Essence

**Positioning:** Everyday medicine access आणि pharmacy operations समजण्यास सोपे करणारा student-built digital prototype.

**Personality:** trustworthy, precise, progressive.

### Brand Voice

Headline copy practical आणि reassuring; CTA action-oriented पण responsible.

- “A clearer way to manage every medicine order.”
- “Browse eligible products. Leave prescription decisions to your pharmacist.”

### Wordmark & Logo

`PHARMA-G7` शब्दचिन्हाच्या सुरुवातीला rounded capsule-outline मध्ये छोटा `+` mark; `G7` ला aqua-teal accent. Default text logo न वापरता custom CSS mark आणि typographic lockup तयार करायचा.

## मुख्य UI भाग

### Customer experience

- Hero: “Pharmacy, organised for real life.”
- Search bar with medicine/category placeholder.
- Trust strip: Pharmacist reviewed, inventory aware, delivery tracked.
- Featured medicine catalog: sample products such as Paracetamol 500mg, Vitamin D3, Cetirizine 10mg, ORS sachets, and Amoxicillin 500mg marked as prescription required.
- Category filters: Pain relief, Vitamins, Allergy, Digestive, First aid.
- Product cards with price, stock state, prescription badge, manufacturer and add button.
- Safety callout and prescription upload panel.
- Cart drawer with quantity controls, subtotal, delivery note and demo checkout.
- About/contact footer with academic prototype disclosure.

### Admin experience

- “Operations overview” dashboard toggle.
- KPI cards: Orders today, Pending review, Low stock, Expiring soon.
- Inventory table with stock, expiry, reorder status.
- Orders timeline/list with status pills.
- Prescription review queue.
- Billing/payment and delivery status panels.
- Clear “Demo data” labeling.

## प्रोजेक्ट रचना

```text
pharmag7/
├── plan.md                 # हा implementation/design plan
├── TODO.md                 # मंजुरीनंतर acceptance outcomes
├── package.json            # start script आणि pinned runtime metadata
├── server.js               # port 3000 static server
├── public/
│   ├── index.html          # customer + dashboard page shell
│   ├── styles.css          # responsive visual system
│   ├── app.js              # demo data, interactions आणि state
│   └── manus-routes.json   # website page route manifest
└── app.config.ts           # project logo metadata
```

## डिलिव्हरी व बिल्ड वर्कफ्लो

1. Plan मंजूर झाल्यावर `TODO.md` मध्ये स्वतंत्र customer, cart/safety आणि admin outcomes नोंदवायचे.
2. Static prototype files लिहायचे आणि route manifest तयार करायचा.
3. Host-managed diagnostics साठी JavaScript/HTML/CSS तपासणी configure करायची.
4. Port 3000 server सुरू करून `/`, `/manus-routes.json` आणि assets HTTP 200 verify करायचे.
5. `webdev-mcp` screenshot ने desktop आणि mobile layout visually inspect करायचा.
6. आवश्यक fixes करून Git checkpoint commit/push करायचा.
7. अंतिम उत्तरात सध्याचा Preview URL द्यायचा; explicit publication न मागितल्यामुळे स्वतःहून public publish करायचे नाही.

## मर्यादा आणि पुढील विस्तार

- हा prototype demo data वापरेल; user authentication, real prescription storage, pharmacist approval workflow, backend API, database, payment gateway आणि notifications production-safe स्वरूपात या आवृत्तीत pretend केले जाणार नाहीत.
- Prescription-only products साठी UI फक्त review-required state दाखवेल; automatic approval किंवा medical advice देणार नाही.
- पुढील टप्प्यात server/database सक्षम करून role-based auth, secure file storage, audit logs आणि real order persistence जोडता येईल.
