# Pics & Prints — Build Checklist

This checklist tracks the new Pics & Prints website in this folder. The existing website in the parent folder is separate and should remain untouched.

## Current state

- [x] New editorial homepage concept
- [x] Photography and printing sections on the shared homepage
- [x] Brand logo and responsive navigation
- [x] Featured-offer placeholder for a manually updated Amazon link
- [ ] Connect real studio content, product data, ordering, booking, database, and admin tools

## 1. Shared website foundation

- [ ] Confirm final logo files, brand colors, fonts, and photography
- [ ] Replace demo/stock images with approved studio-owned or licensed images
- [ ] Add real studio introduction, contact details, service area, hours, and social links
- [ ] Add privacy, terms, cancellation/refund, shipping, and other required policy pages
- [ ] Add accessible labels, keyboard navigation, focus states, and image descriptions
- [ ] Review readability, mobile layouts, and navigation on common screen sizes
- [ ] Add page titles, descriptions, social share images, sitemap, and robots rules
- [ ] Add analytics only after choosing the tool and privacy approach

## 2. Photography experience

- [ ] Create photography landing page and service categories
- [ ] Add portfolio galleries with categories, captions, and image optimization
- [ ] Create photography packages with inclusions, duration, location, and INR pricing
- [ ] Add inquiry and booking flow
- [ ] Collect session type, preferred date/time, location, people, notes, and contact details
- [ ] Show date availability and prevent conflicting bookings
- [ ] Add deposit/full-payment options and booking confirmation
- [ ] Provide customer booking details and rescheduling/cancellation instructions
- [ ] Add private client gallery previews, favorites, downloads, and expiry controls

## 3. Printing and e-commerce

- [ ] Create printing catalogue with categories and searchable products
- [ ] Add product details: size, paper/material, finish, quantity breaks, turnaround, and INR price
- [ ] Add variants/options and price calculation before checkout
- [ ] Add artwork upload with accepted formats, size limits, and upload guidance
- [ ] Add proof/approval flow for custom designs
- [ ] Add templates and design choices where customers can personalize a product
- [ ] Build cart, delivery address, shipping selection, order review, and checkout
- [ ] Show order confirmation, status, and estimated dispatch/delivery
- [ ] Support guest checkout and customer accounts where appropriate
- [ ] Define packaging, delivery zones, shipping prices, and return/reprint handling

## 4. Homepage featured Amazon offer

- [ ] Build an admin form to edit offer title, description, image, button text, URL, and active dates
- [ ] Validate that offer URLs use HTTPS and point to an approved destination
- [ ] Add preview before publishing and an option to disable the offer
- [ ] Track clicks without exposing customer data
- [ ] Add affiliate disclosure text if the offer uses affiliate links
- [ ] Confirm Amazon/affiliate program requirements before publishing links

## 5. Admin dashboard and operations

- [ ] Secure admin sign-in, password reset, roles, and permissions
- [ ] Dashboard overview for new inquiries, bookings, orders, deadlines, and revenue
- [ ] Calendar for sessions, production deadlines, and delivery dates
- [ ] Lead and inquiry management with notes, owner, source, and follow-up reminders
- [ ] Project/task management with status, assignee, due date, and activity history
- [ ] Order tracking with customer, items, artwork, payment, production, and shipping statuses
- [ ] Client database with contact information, bookings, orders, preferences, and consent
- [ ] Product catalogue and photography package management
- [ ] Template/design management
- [ ] Staff management and task assignment
- [ ] Inventory tracking for paper, ink, packaging, and equipment where useful
- [ ] Finance tools for invoices, payments, refunds, and expenses
- [ ] Audit history for important admin changes
- [ ] Export business records in a practical format

## 6. Database and file storage

A database is needed once products, offers, bookings, orders, or admin changes must persist across devices and visitors. Browser-only storage is suitable only for a temporary prototype; it is not a reliable production database.

- [ ] Choose a managed relational database (for example PostgreSQL) and hosting region
- [ ] Model users, roles, clients, leads, products, variants, packages, bookings, orders, order items, payments, invoices, tasks, inventory, galleries, templates, and featured offers
- [ ] Define statuses, required fields, relationships, and deletion/retention rules
- [ ] Store money as integer paise with currency code INR; never use floating point for totals
- [ ] Add unique order numbers, timestamps, and audit fields
- [ ] Add database migrations and seed data for initial catalogue/admin account
- [ ] Store uploaded images/artwork in private object storage, not directly in database rows
- [ ] Use signed, expiring links for private gallery and artwork access
- [ ] Set upload type/size limits and scan/validate files
- [ ] Configure automated encrypted backups and test restore procedure
- [ ] Limit database access to the application; keep credentials out of frontend code
- [ ] Decide data retention, customer deletion/export requests, and consent records

## 7. Payments, notifications, and integrations

- [ ] Choose an India-supported payment provider after comparing fees and settlement needs
- [ ] Use hosted/tokenized checkout; do not store card numbers or security codes
- [ ] Verify payment status on the server using signed webhooks
- [ ] Make payment/order processing idempotent to prevent duplicate orders
- [ ] Handle failed, pending, successful, refunded, and partially refunded payments
- [ ] Configure email/SMS/WhatsApp notifications for inquiries, bookings, orders, and status changes
- [ ] Use a verified business sender and approved message templates where the provider requires them
- [ ] Add delivery/shipping integration if manual fulfillment is no longer practical
- [ ] Configure invoice numbering and applicable business/tax fields with the business owner

## 8. Security and reliability

- [ ] Enforce HTTPS on all public and admin pages
- [ ] Use secure sessions, password hashing, CSRF protection, and rate limits
- [ ] Restrict admin access by role and use multi-factor authentication if supported
- [ ] Validate all input on the server and escape output
- [ ] Protect uploads from executable files, oversized files, and public exposure
- [ ] Keep secrets in hosting environment settings, not source files
- [ ] Add error logging and uptime monitoring without recording sensitive data
- [ ] Set dependency/security update ownership and incident contact
- [ ] Test backup restoration and payment/webhook recovery before launch

## 9. Deployment checklist

### Before launch

- [ ] Choose hosting for the frontend, backend/API, database, and file storage
- [ ] Connect the production domain and configure DNS
- [ ] Enable HTTPS and redirect HTTP to HTTPS
- [ ] Set production environment variables and remove demo/test credentials
- [ ] Run database migrations and create the first admin securely
- [ ] Configure production payment keys and webhook endpoint
- [ ] Configure email/SMS sender, delivery/shipping rules, and business contact details
- [ ] Add privacy/terms/refund/shipping pages and cookie/analytics choices as applicable
- [ ] Confirm all product prices are INR and checkout totals match the catalogue
- [ ] Confirm image licenses, compression, responsive loading, and alt text
- [ ] Check forms, booking conflicts, checkout, payment status, order email, and admin permissions
- [ ] Test on mobile, desktop, keyboard-only, and a current major browser
- [ ] Check error pages, empty states, unavailable dates, and failed uploads/payments
- [ ] Verify sitemap, page metadata, social previews, and search indexing settings
- [ ] Take a backup and verify the restore process

### After launch

- [ ] Place a low-value real or provider-approved test order and refund it if appropriate
- [ ] Monitor errors, payment webhooks, email delivery, and uptime
- [ ] Confirm new orders and bookings appear in admin notifications
- [ ] Schedule database/file backups and review backup success
- [ ] Document how to update products, prices, Amazon offers, and content
- [ ] Review performance, accessibility, and abandoned checkout feedback
- [ ] Keep a rollback plan for frontend and database changes

## Suggested build sequence

1. Approve homepage content and visual direction.
2. Build Photography and Printing customer journeys with sample data.
3. Define database and backend around those journeys.
4. Build admin catalogue, booking, order, and featured-offer tools.
5. Connect uploads, payments, notifications, and fulfillment.
6. Complete launch checks and deploy to a staging site.
7. Review staging with real products and staff workflows, then launch.
