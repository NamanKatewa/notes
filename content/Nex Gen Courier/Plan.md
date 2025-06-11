# Phase 1
Requirements Finalization & Planning

## Goals
- Define MVP scope clearly
- Set up project management (Notion/Trello)
- Finalize functional & non-functional requirements

## Tasks
- [x] Review and Confirm Admin + Client Panel feature lists
- [x] Finalize functional requirements matrix
- [x] Defined MVP features to build first
- [x] Finalize non-functional goals
- [x] Define initial KYC process
- [x] Choose hosting

# Phase 2
Architecture, Design & Dev Setup

## Goals
- Lay down a scalable foundation
- Setup backend/ frontend monorepo

## Tasks
- [x] Design full ERD
- [x] Initialize Next.js App Router
- [x] Setup tailwindCSS, shadcn/ui and Layout
- [x] Setup @trpc/server + @trpc/react + next-auth
- [x] Setup Prisma with PostgreSQL and generate base models
- [x] Plan modular folder structure
- [x] Define base Zod schemas for input validation

# Phase 3
UI / UX Wireframes & Components

## Goals
- Lay UI groundwork using reusable components

## Tasks
- [x] Create wireframes for Admin & Client Panels
- [x] Build reusable layout components
- [x] Build auth screens
- [x] Create Quick Actions Section
- [x] Design Dashboard pages

# Phase 4
Authentication & User Management

## Goals
- Secure user auth, basic client registration

## Tasks
- [x] Setup next-auth with credentials provider
- [x] JWT + cookie based sessions
- [x] Add RBAC logic with middleware
- [ ] Implement Signup API with KYC file upload
- [ ] Implement Login + Forgot Password via email
- [ ] Create Admin screen to verify/reject KYC

# Phase 5
Wallet System & Payments

## Goals
- Build secure wallet + Razorpay recharge flow

## Tasks
- Create wallet, walletTransaction, paymentTransaction models
- Integrate Payment Processor
- Handle webhook for payment verification
- Update wallet balance on successful recharge i.e. manually by admin, separate page on admin dashboard
- Add passbook view ( client ) and admin view ( all users )
- Implement wallet adjustment flows

# Phase 6
Order Booking & Labeling System

## Goals
- Build shipment booking engine and AWB generation

## Tasks
- [ ] Define order creation flow ( form input + bulk import via csv )
- [ ] Call internal rate calculation API
- [ ] Deduct from wallet if balance is sufficient
- [ ] Create AWB logic ( user offset + ID based )
- [ ] Store order details and status
- [ ] Implement carrier adapter pattern
- [ ] Get label PDF and allow download/print
- [ ] Admin approval/rejection flows with reasons

# Phase 7
Carrier Integration & Tracking

## Goals
- Integrate real-time tracking for all orders

## Tasks
- [ ] Finish adapters
- [ ] Standardize status internally
- [ ] Design shipment + tracking update model
- [ ] Polling or webhook-based updates
- [ ] Real-time dashboard updates
- [ ] Homepage public tracking + Rate Estimation tool\

# Phase 8
Admin dashboards & Analytics

## Goals
- Show financial and operational metrics

## Tasks
- [ ] Revenue dashboard ( filter by date, user, carrier )
- [ ] Shipment performance summary ( delivered, pending, RTO )
- [ ] Implement search across entities ( AWB, phone, email )
- [ ] Exportable client sales reports ( Excel )
- [ ] Admin label bulk download

# Phase 9
Support & Misc features

## Goals
- Build support ticket system

## Tasks
- [ ] Create supportTicket + supportConversation model
- [ ] Allow clients to raise new tickets
- [ ] Admin can respond, close/reopne tickets
- [ ] Notification system ( toasts + optional email later)
- [ ] Employee management screen ( roles + permissions )
- [ ] Basic Notification bell + settings ( optional )