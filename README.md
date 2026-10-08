# MASTER BUILD PROMPT — STUDENT BURGERS & SHAWARMA

## Vercel v0 + Next.js + GitHub + Supabase

Act as a senior full-stack engineer, UI/UX designer, database architect, security engineer and restaurant ordering-system specialist.

Build a complete, production-oriented restaurant website and online ordering web app for **Student Burgers & Shawarma / Student Pizza Fastfood**, based on the provided physical menu photos and the business's existing brand identity.

This is a real business project, not a mockup or a frontend-only demo.

## PHASE 1 — CONNECT TO THE CORRECT GITHUB REPOSITORY

The target repository is:

https://github.com/kaleemdurrani514-collab/student-burgers-shawarma

**This exact existing repository is the required source of truth. Do not create an unrelated replacement repository.**

Before writing or modifying code:

1. Connect/import this existing repository into v0 using the GitHub integration.
2. Verify that the connected repository is `kaleemdurrani1978-cell/Student-Burgers-Shawarma-`.
3. Inspect the complete project structure, current branches, existing code, package manager, framework, dependencies, environment variables, routes, assets and configuration.
4. Identify what already works and what needs to be built.
5. Create or use a dedicated feature branch for development.
6. Preserve all existing useful functionality.
7. Do not overwrite the production branch or perform destructive operations without explicit approval.
8. Do not delete existing files simply to simplify development.

If repository access is unavailable, stop and tell me precisely which GitHub authorization or repository permission is needed. Do not pretend that you connected to it.

If the repository already has an established framework or working application, extend it safely. Do not blindly replace its architecture.

## PHASE 2 — UNDERSTAND THE BUSINESS AND ORIGINAL MENU

Business Facebook page:

https://www.facebook.com/p/Student-pizza-Fastfood-100089295146903/

Inspect the publicly accessible page and extract verifiable information:

* Official business name
* Public phone number
* WhatsApp number, if listed
* Address
* Opening hours
* Facebook page URL
* Publicly available location information

Use only verified information. If Facebook does not reveal a detail, make it configurable in Admin Settings and mark it as requiring verification.

The two uploaded menu photographs are the primary source of truth for the existing menu and logo.

Inspect both photographs carefully, including the yellow menu and the black Student Deals menu.

Extract every readable product, deal, item quantity, price and Urdu/English name.

Rules:

* Preserve the actual menu items and original prices.
* Include the complete menu, not just selected popular products.
* Do not invent menu items or deal contents.
* Do not guess unclear prices.
* Flag uncertain OCR results for manual admin verification.
* Preserve the recognizable original logo.
* Do not replace the original brand with an unrelated AI-generated logo.

Create a structured menu import file or database seed containing the extracted products and deals. Maintain a verification field for uncertain menu entries.

## PHASE 3 — DESIGN A PREMIUM MOBILE-FIRST EXPERIENCE

Build a polished, modern Pakistani fast-food ordering experience.

Brand direction:

* Yellow, black, red and white inspired by the original printed menu.
* Modern, clean layouts rather than copying the crowded printed menu.
* Attractive typography and excellent readability.
* Strong contrast and accessible controls.
* Smooth, restrained animations.
* Fast loading on mobile internet.
* Excellent usability on small phone screens.

The website must feel like a professional restaurant application, not a generic template.

### Homepage

Include:

* Original Student logo
* Restaurant name
* Attractive food-focused hero
* Order Now CTA
* View Menu CTA
* Featured menu items/deals
* Menu category navigation
* Restaurant opening status
* Contact and WhatsApp shortcuts
* Location and business information, once verified
* Professional footer

Use concise, natural English copy. Support Urdu product names where applicable and render Urdu text correctly.

### Navigation

Create:

* Home
* Menu
* Deals
* Contact
* Cart
* Admin access through a protected route

Do not expose admin management features to public customers.

## PHASE 4 — UNIQUE FOOD IMAGES

Every product and deal that needs an image must have its own appropriate image asset.

Generate or source realistic, attractive food photography that matches each actual menu item.

Examples:

* Zinger burger: crispy chicken burger
* Shawarma: appropriate shawarma wrap
* Fries: fries
* Chicken burger: chicken burger
* A specific deal: image representing that deal's actual contents

Requirements:

* No single generic burger image reused across all products.
* No accidental duplicate images assigned to different products.
* Deal images should reflect the deal's actual contents.
* Keep a consistent photography style and suitable aspect ratios.
* Optimize images for mobile and desktop.
* Use descriptive filenames and alt text.
* Store image references in the product database.
* Provide image upload/replacement functionality in Admin.

Use generated or properly licensed assets. Do not hotlink random third-party image URLs.

Create a final image audit that checks whether separate products accidentally reference the same image. If an image is intentionally shared, report it explicitly.

Do not use the photographed printed menu as every product's food image. Extract the information and logo; create separate clean product images.

## PHASE 5 — COMPLETE DIGITAL MENU

Build a database-driven menu with categories derived from the actual menu.

Each product should support:

* Unique ID
* English name
* Optional Urdu name
* Category
* Price in PKR
* Description
* Image
* Availability
* Featured status
* Display order
* Creation/update timestamps

Deals must support:

* Deal name/number
* Original menu price
* Included items and quantities
* Description
* Unique image
* Availability
* Featured status
* Display order

Provide:

* Category filters
* Search
* Product cards
* Add to cart
* Quantity adjustment
* Out-of-stock states
* Deal cards
* Mobile-friendly product browsing

Never hard-code prices in UI components.

All prices must come from trusted database records. Calculate totals on the server using current product prices.

## PHASE 6 — SHOPPING CART AND CHECKOUT

Build a functional cart with:

* Product image and name
* Unit price
* Quantity controls
* Remove item
* Subtotal
* Delivery charge when applicable
* Final total
* Customer notes
* Order type selection

Support three order types:

1. Delivery
2. Takeaway
3. Dine-in

### Delivery checkout

Collect:

* Customer full name
* Phone number
* Complete delivery address
* Area
* Landmark
* Delivery instructions

### Takeaway checkout

Collect:

* Customer name
* Phone number
* Optional pickup notes

### Dine-in checkout

Collect:

* Customer name
* Phone number if required by the restaurant
* Table number when ordering through a table QR code

Allow dine-in orders without a numbered table by selecting “No Table” and entering the customer's name.

Validate the checkout fields according to the selected order type.

Do not require an online payment gateway for the initial release.

## PHASE 7 — WHATSAPP ORDERING

WhatsApp ordering is a core requirement.

Use the restaurant's verified WhatsApp number from database-backed Restaurant Settings. Never hard-code the number in multiple components.

When the customer confirms the cart:

1. Validate the cart and customer details.
2. Recalculate prices and totals using trusted server-side data.
3. Create a persistent order record and unique order ID.
4. Generate a complete, readable WhatsApp message.
5. Open WhatsApp using a correctly encoded `wa.me` link.
6. Clearly explain that the customer must send the prepared message.
7. Do not falsely claim that WhatsApp was sent automatically or that the restaurant has accepted the order.

Use this message structure:

STUDENT BURGERS & SHAWARMA
NEW ORDER

Order ID: ST-XXXXXXXX

Order Type: DINE-IN

Customer Name: [customer name]
Phone: [phone number]
Table: [table number or No Table]

ORDER ITEMS:
1 × [actual product name] — Rs. [price]
2 × [actual product name] — Rs. [price]

Subtotal: Rs. [amount]
Delivery Charges: Rs. [amount]
TOTAL: Rs. [amount]

Customer Notes: [notes]

Please confirm this order.

For delivery orders, include the full address, area, landmark and delivery instructions.

For takeaway orders, include pickup details.

The message must use the actual cart contents, prices and order details. Never send placeholder values in a real order.

### Order confirmation

After preparing the order, show:

* Order ID
* Order summary
* Total
* Customer/order details
* A clear “Send Order on WhatsApp” button

The system must distinguish between:

* Order record created
* WhatsApp opened
* Restaurant confirmation received

Do not claim the restaurant has confirmed an order unless the business has actually confirmed it.

## PHASE 8 — DINE-IN QR CODE ORDERING

Build a dynamic QR code system.

Example URL:

`/order?table=5`

When a customer scans the QR code:

* Open the website on their phone.
* Detect the table number.
* Display “Ordering for Table 05”.
* Preserve table context throughout browsing and checkout.
* Create the order with the correct table number.
* Include that table number in the WhatsApp message.

Do not hard-code a fixed number of tables.

Admin must be able to:

* Create tables
* Edit table names/numbers
* Activate/deactivate tables
* Generate QR codes
* Preview QR codes
* Download printable QR cards
* Regenerate QR codes

QR codes must contain the correct deployed application URL, not localhost.

Generate QR codes dynamically from the configured production base URL. Do not embed secrets or private tokens in QR codes.

Validate table identifiers server-side.

If an invalid or inactive table number is supplied, show a friendly error and let the customer choose another order type.

Provide a printable branded QR layout:

STUDENT BURGERS & SHAWARMA

TABLE 05

SCAN TO ORDER

[QR CODE]

Scan with your phone camera.

Support dine-in orders without tables using the customer-name option.

## PHASE 9 — SECURE ADMIN DASHBOARD

Create a protected `/admin` area.

Implement genuine authentication and authorization. Hiding the admin link is not security.

Admin features:

### Dashboard

* Today's order count
* New/pending orders
* Confirmed orders
* Completed orders
* Cancelled orders
* Sales totals based on recorded orders
* Popular products
* Recent orders

Clearly distinguish order totals from verified payments. Since online payments are not initially integrated, do not label every order total as money received.

### Menu management

* Add product
* Edit product
* Update price
* Upload/replace image
* Change category
* Set availability
* Feature/unfeature product
* Reorder products
* Soft-delete or deactivate products safely

### Deal management

* Create new deals
* Edit existing deals
* Change deal prices
* Configure included products and quantities
* Upload deal images
* Activate/deactivate deals

### Order management

Display:

* Order ID
* Date/time
* Customer details
* Order type
* Table number
* Delivery address
* Items and quantities
* Subtotal
* Delivery charges
* Total
* Notes
* Status

Statuses:

* New
* Confirmed
* Preparing
* Ready
* Out for Delivery
* Completed
* Cancelled

Allow admins to update order statuses and contact customers through WhatsApp.

### Table/QR management

* Create and manage tables
* Generate and download QR codes
* Print QR cards
* Deactivate tables

### Restaurant settings

Allow authorized admins to edit:

* Restaurant name
* Logo
* WhatsApp number
* Phone number
* Address
* Maps link
* Facebook link
* Opening hours
* Delivery availability
* Delivery charges
* Minimum delivery order
* Service areas
* Announcement banner
* Currency
* Restaurant open/closed state

Changes must persist in the database and reflect on the public website.

## PHASE 10 — DATABASE AND BACKEND

Preferred stack, subject to the existing repository architecture:

* Next.js
* TypeScript
* React
* Tailwind CSS
* shadcn/ui where appropriate
* Supabase PostgreSQL
* Supabase Auth
* Supabase Storage

If the repository already uses a compatible working stack, preserve it unless a change is necessary.

Create proper relational tables for:

* Admin users/profiles
* Categories
* Products
* Deals
* Deal items
* Orders
* Order items
* Restaurant tables
* Restaurant settings

Use database migrations or another reproducible schema setup.

Requirements:

* Persistent orders
* Persistent menu changes
* Persistent prices
* Persistent restaurant settings
* Persistent tables
* Persistent image references

Implement server-side validation and appropriate database access controls.

Enable appropriate Row Level Security policies if using Supabase. Public customers should not be able to read private customer order history or modify administrative data.

Only authorized administrators may manage products, prices, orders, settings and tables.

Never expose service-role keys or other secrets in browser code.

Use environment variables for credentials.

If Supabase or another required integration is not connected, tell me exactly what setup or authorization is needed. Do not substitute fake database operations or claim persistence without verifying it.

## PHASE 11 — OPEN/CLOSED AND DELIVERY SETTINGS

Allow admin to configure:

* Restaurant open/closed state
* Opening hours
* Delivery enabled/disabled
* Delivery charge
* Minimum order
* Available service areas
* Product availability

When the restaurant is closed, display its status clearly.

If orders are disabled, prevent accidental checkout and explain why. Do not silently accept orders when the restaurant is configured as closed unless the admin has explicitly enabled that behavior.

## PHASE 12 — SEO AND LOCAL PRESENCE

Prepare the public website for local discovery.

Implement:

* Appropriate page titles
* Meta descriptions
* Open Graph metadata
* Sitemap
* robots.txt
* Canonical URLs where appropriate
* Restaurant structured data using verified business information
* Menu/product structured data where appropriate
* Fast mobile page loading
* Accessible navigation
* Semantic HTML

Use the verified business name, address, telephone and hours.

Do not fabricate Google reviews, ratings, business listings or location information.

Make the site ready for the owner to create or claim a Google Business Profile separately.

## PHASE 13 — VERCEL DEPLOYMENT

Make the application compatible with Vercel deployment.

Requirements:

* Production build succeeds
* Correct environment-variable handling
* No localhost assumptions in production URLs
* Correct image configuration
* Functional server routes
* Persistent external database/storage
* Correct production URL handling for QR codes
* No secrets committed to Git

Prepare a `.env.example` containing variable names and safe placeholders only. Never include real credentials.

Document the environment variables that must be configured in v0/Vercel.

Do not claim a successful deployment until the deployment status and URL have been verified.

## PHASE 14 — TEST THE COMPLETE SYSTEM

Test the actual application, not only its visual appearance.

### Customer tests

* Homepage loads.
* Menu categories work.
* Search works.
* Product images load.
* Product quantities update correctly.
* Cart totals are correct.
* Delivery validation works.
* Takeaway checkout works.
* Dine-in checkout works.
* No-table ordering works.
* WhatsApp messages contain correct details.
* QR table context is preserved.
* Unavailable products cannot be ordered.
* Invalid table IDs are handled safely.

### Admin tests

* Authentication works.
* Unauthorized users cannot access admin functions.
* Product creation works.
* Price changes persist.
* Image replacement works.
* Deal creation works.
* Table creation and QR generation work.
* Order statuses persist.
* Restaurant settings persist.
* The customer-facing website reflects admin changes.

### Technical tests

* TypeScript checks pass.
* Production build succeeds.
* No important console errors.
* No broken internal routes.
* No broken images.
* No accidental duplicate image assignments.
* No exposed credentials.
* No insecure public admin operations.
* No horizontal overflow on mobile.

Fix discovered issues before reporting completion.

## PHASE 15 — GITHUB DELIVERY IS MANDATORY

The final source code must be delivered to this exact repository:

https://github.com/kaleemdurrani1978-cell/Student-Burgers-Shawarma-

Use v0's connected GitHub workflow.

1. Work on a feature branch.
2. Commit all required project changes through the supported integration.
3. Run the available checks.
4. Create a pull request against the repository's production branch.
5. Summarize the changes in the pull request.
6. Include database setup instructions and environment-variable documentation.
7. Do not overwrite or bypass the protected production branch.
8. Do not claim the code has been pushed unless the commit/branch is actually visible in GitHub.
9. Do not claim the project is production-ready if essential integrations remain unconfigured.
10. If merging requires my approval, leave the pull request ready for review and tell me exactly how to approve and merge it.

Do not create a new repository with a similar name.

Do not upload credentials, `.env` files containing secrets, private customer data or unnecessary generated files.

## PHASE 16 — FINAL DELIVERY REPORT

At completion, provide:

1. Repository URL.
2. Development branch name.
3. Pull request URL, if created.
4. List of implemented features.
5. Framework and database details.
6. Database migrations/setup status.
7. Authentication setup status.
8. Required environment variables.
9. WhatsApp configuration status.
10. Verified Facebook/business details and any missing information.
11. Menu entries that need manual verification.
12. Unique-image audit results.
13. Build and test results.
14. Vercel deployment URL and verified deployment status, if deployed.
15. Any remaining manual setup required before customers can place real orders.

### FINAL NON-NEGOTIABLE RULES

* Work in the exact existing GitHub repository.
* Inspect before modifying.
* Preserve useful existing code.
* Keep the original Student brand recognizable.
* Use the supplied menu photographs as the source of truth.
* Never invent menu items, prices, contact information or ratings.
* Give each menu product/deal an appropriate unique image.
* Implement real persistent storage and secure admin access.
* Make WhatsApp ordering and dine-in QR ordering functional.
* Make admin changes persist.
* Test the complete customer and admin flows.
* Commit the work and prepare the GitHub pull request.
* Report honestly what works and what still requires configuration.

**Start by connecting to the existing repository and auditing its current contents. Then implement the project incrementally. Do not stop at a static design or a frontend prototype.**
