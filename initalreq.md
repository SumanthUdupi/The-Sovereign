# Product Requirements Document (PRD)

**Project Name:** THE SOVEREIGN  
**Version:** 2.0  
**Last Updated:** November 30, 2025

---

## 1. Executive Summary

### Vision
The Sovereign redefines luxury dining as a complete culinary ecosystem—where Michelin-quality delivery meets professional education and vibrant community engagement. We are not a delivery app; we are a lifestyle platform for those who demand excellence.

### Core Philosophy
**"Accessible Royalty"** — Democratizing fine dining while preserving its artistry. We blend Old World hospitality with radical transparency, creating an experience where every meal feels like a private chef's table.

### Unique Value Propositions
1. **White Glove Butler Service** — Personalized delivery experiences beyond the doorstep
2. **Human-Curated Expertise** — Zero algorithms; every pairing crafted by certified professionals
3. **Radical Transparency** — Live kitchen streams showing your meal's creation in real-time
4. **Cross-Restaurant Curation** — Compose multi-course experiences from the city's finest establishments
5. **Community-Powered Education** — Learn from masters and contribute to a growing culinary society

---

## 2. Design System: "Midnight at the Palace"

### 2.1 Brand Aesthetic
**Concept:** A digital speakeasy where luxury meets intimacy—velvet curtains, candlelit tables, and the quiet confidence of exceptional service.

### 2.2 Color Palette

**Foundation**
- **Obsidian Black** (`#000000`) — Primary backgrounds, creating infinite depth
- **Velvet Charcoal** (`#121212`) — Secondary surfaces, cards, and modals
- **Titanium White** (`#F0F0F0`) — Body text, ensuring AAA accessibility

**Accent Hierarchy**
- **Brushed Gold** (`#C5A059`) — Primary accents, prices, headings, CTAs
- **Warm Gold Hover** (`#D4B068`) — Interactive state for gold elements
- **Cinematic Red** (`#8B0000`) — Live indicators, urgent states (deep crimson, never bright)
- **Royal Purple** (`#6B46C1`) — Community features, social engagement
- **Champagne** (`#F7E7CE`) — Success states, premium badges

**Functional Colors**
- **Success:** Sage Green (`#6B8E23`)
- **Warning:** Amber (`#FFB347`)
- **Error:** Burgundy (`#800020`)
- **Disabled:** Smoke (`#4A4A4A`)

### 2.3 Typography System

**Display (Headings, Hero Text)**
- **Primary:** Playfair Display or Bodoni Moda
- **Weights:** Light (300) for elegance, Bold (700) for impact
- **Usage:** H1-H3, prices, feature titles

**Interface (Body, UI Elements)**
- **Primary:** Inter or Montserrat
- **Weights:** Regular (400), Medium (500), Semibold (600)
- **Usage:** Paragraphs, buttons, navigation, forms

**Specialty (Curator Notes)**
- **Option:** Crimson Text (for "handwritten" sommelier cards)
- **Style:** Italic, 16-18pt, with increased line-height for readability

### 2.4 Spacing & Layout
- **Base Unit:** 8px grid system
- **Container Max-Width:** 1440px (desktop), 100% (mobile with 16px margins)
- **Card Radius:** 12px (soft luxury, not harsh corners)
- **Elevation:** Subtle shadows using `rgba(0,0,0,0.4)` for depth

### 2.5 Motion Principles
- **Philosophy:** Smooth, intentional, never rushed
- **Standard Duration:** 300ms ease-in-out
- **Hero Animations:** 600ms cubic-bezier for dramatic reveals
- **Microinteractions:** 150ms for immediate feedback (button presses, toggles)

---

## 3. Information Architecture: "The Royal Compass"

### 3.1 Global Navigation Structure

**Persistent Sidebar (Desktop) / Bottom Bar (Mobile)**

| Icon | Wing | Primary Function |
|------|------|------------------|
| 👑 Crown | **The Royal Banquet** | Ordering, cart, menu exploration |
| 👁 Eye | **The Theatre of Taste** | Video content, masterclasses, stories |
| 🛡 Shield | **The Court of Creators** | Community recipes, leaderboards, gamification |
| 👤 Profile | **Your Legacy** | Order history, preferences, membership tier |

**Navigation Behavior:**
- Icons glow with Brushed Gold on hover/active state
- Active section displays a subtle underline or fill
- Smooth 300ms transition between sections
- Mobile: Bottom navigation collapses cart into floating action button

### 3.2 Search & Discovery
**Global Search Bar** (Top-right, always accessible)
- **Unified Search:** Queries dishes, chefs, videos, community recipes simultaneously
- **Smart Filters:** Cuisine type, dietary restrictions, price range, preparation time
- **Voice Search:** Premium feature using natural language ("Show me Italian appetizers under $30")

---

## 4. Feature Specifications

## Module A: The Royal Banquet (Ordering & Fulfillment)

### 4.1 Cuisine Wings Architecture

**Concept:** Users navigate by culinary tradition, not restaurant brand. Each "Wing" is a curated collection of the city's finest offerings in that cuisine.

**Available Wings** (Initial Launch):
1. The Italian Wing
2. The Japanese Wing
3. The French Wing
4. The Seafood Wing
5. The Steakhouse Wing
6. The Plant-Based Wing

**Wing Homepage Layout:**
- **Hero Section:** Cinematic dish photography carousel (full-bleed, 16:9)
- **Featured Collections:** "Chef's Signatures," "New This Week," "Crowd Favorites"
- **Menu Grid:** Dish cards with high-res imagery, price, prep time, partner restaurant badge

**Dish Card Anatomy:**
```
┌─────────────────────────────┐
│  [Dish Photo - 16:9]        │
├─────────────────────────────┤
│  Dish Name (Serif, Gold)    │
│  Partner: Restaurant Name    │
│  ⭐ 4.8 (127) · 🕐 35min    │
│  $45 · [Pairing Available]  │
│  [+ Add to Course Builder]  │
└─────────────────────────────┘
```

### 4.2 The Custom Course Builder

**Interaction Model:**
1. Users click "Build a Tasting Menu" from any Wing
2. Interface transitions to a split-screen workspace:
   - **Left:** Scrollable dish browser (filterable by course type)
   - **Right:** Course builder canvas (5-7 slots)

**Drag-and-Drop Logic:**
- Dishes snap into numbered course slots (Amuse-Bouche → Dessert)
- Visual feedback: Gold outline on valid drop zones
- Conflict Detection: If prep times create 2+ hour delays, show warning with suggested reordering

**Cross-Restaurant Coordination:**
- **Backend:** System calculates optimal kitchen pickup sequence to minimize driver routes
- **Frontend:** Users see unified delivery estimate ("Your feast arrives at 8:15 PM")
- **Premium Option:** "Synchronized Service" ensures all courses arrive within 5-minute windows (+$15)

**Mobile Adaptation:**
- Replace drag-and-drop with sequential "Add to Course 1, 2, 3..." buttons
- Swipeable course carousel for editing

### 4.3 The Sommelier's Library

**Core Principle:** Every pairing is human-crafted. No machine learning recommendations.

**Sommelier Profile Database Requirements:**
- **Fields:** Name, photo, certifications (WSET, Court of Master Sommeliers), specialties, bio (200 chars)
- **Digital Signature:** High-res scan of actual signature for authenticity
- **Portfolio:** List of dishes they've paired with rationale

**The Handwritten Note UI:**

**Trigger:** When user selects a dish, a "View Pairing" button appears  
**Animation:** Card slides from right, resembling premium stationery with subtle paper texture

**Card Layout:**
```
┌───────────────────────────────────────┐
│  [Sommelier Photo - Circle, 60px]    │
│  "A Perfect Match" (Script Font)      │
│                                       │
│  [Wine Bottle Image]                  │
│  2019 Châteauneuf-du-Pape            │
│  $68 · Add to Order                   │
│                                       │
│  "The peppery notes in this Grenache  │
│   blend echo the herbs in the lamb,   │
│   while the wine's structure stands   │
│   up to the richness."                │
│                                       │
│  — [Digital Signature]                │
│  Marie Leclerc, Master Sommelier      │
└───────────────────────────────────────┘
```

**Conflict Management System:**

**Scenario:** User selects clashing items (e.g., dessert wine + appetizer)

**Gentle Nudge Modal:**
- **Tone:** Respectful, never condescending
- **Copy:** "A bold choice! Sommelier [Name] notes this pairing may overwhelm the delicate flavors. May I suggest [Alternative]?"
- **Actions:** [Keep My Choice] [See Suggestion] [Ask Expert]

**The Red Phone Feature (VIP Tier):**
- **Trigger:** Gold phone icon appears next to complex pairings or custom requests
- **Function:** Initiates real-time chat or 5-minute video consultation with on-duty sommelier
- **Availability:** 5 PM - 11 PM daily (peak dining hours)
- **Use Cases:** 
  - Pairing with user's personal cellar wine
  - Group dinner with diverse palates
  - Special occasion recommendations

### 4.4 The Digital Butler Service

**Activation:**
- **Icon:** Floating gold bell icon (bottom-right, always visible in Banquet section)
- **Behavior:** Pulses gently every 30 seconds as subtle reminder

**Chat Interface:**
- **Greeting:** "Good evening. How may I assist with your dining experience?"
- **Powered By:** Human concierge during business hours (AI fallback with clear disclosure)
- **Response Time SLA:** < 2 minutes for urgent requests, < 10 minutes for planning

**Common Use Cases:**
1. **Dietary Accommodations:** "I'm allergic to shellfish but want the bouillabaisse experience"
2. **Event Planning:** "Corporate dinner for 8, budget $150/person, need appetizers at 7, mains at 8:30"
3. **Special Requests:** "Can the steak be cooked over oak? It's an anniversary tradition"
4. **Table Setup Coordination:** "I'll need two warming plates and sommelier glasses for the pairing"

**Premium Services (Concierge Tier - $29/month):**
- Priority response queue
- Dedicated butler for repeat customers
- Advanced reservations for limited-availability dishes
- Custom menu design consultation

---

## Module B: The Royal Command Center (Order Tracking)

**Philosophy:** Transparency as theater. Every order becomes an immersive experience.

### 5.1 Stage 1: The Creation (Live Kitchen Production)

**Technical Requirements:**
- **Streaming Protocol:** WebRTC for <3 second latency or HLS for broader compatibility
- **Camera Placement:** Partner kitchens install 2-3 fixed HD cameras at key stations (grill, plating, expo)
- **Bandwidth:** Adaptive bitrate streaming (480p-1080p based on user connection)

**UI Layout:**
```
┌─────────────────────────────────────────┐
│  [LIVE] Chef Marco's Station           │
│  ┌───────────────────────────────────┐ │
│  │                                   │ │
│  │     [Live Video Feed]             │ │
│  │     Your Ribeye in Progress       │ │
│  │                                   │ │
│  └───────────────────────────────────┘ │
│  🔊 Kitchen Audio [Toggle]              │
│                                         │
│  ━━━●━━━━━━━━━━━━━ 8:32 elapsed      │
│                                         │
│  ✓ Steak seared                        │
│  ⏳ Now resting (est. 3 min)           │
│  ⏸ Plating next                        │
└─────────────────────────────────────────┘
```

**Overlay Elements:**
- **Milestone Cards:** Slide up from bottom with cinematic red border
  - "Chef has begun preparation"
  - "Searing proteins now"
  - "Final plating in progress"
- **Timer:** Elegant countdown showing estimated completion
- **Audio Toggle:** ASMR-quality kitchen ambiance (sizzle, knife work, plates) - optional

**Privacy & Quality Controls:**
- Partners can blur background (focus on food only)
- Streams auto-archive for 24 hours (users can replay "How my meal was made")
- Minimum quality standard: 720p, 30fps, clear audio

### 5.2 Stage 2: The Procession (Transit)

**Transition Animation:**
- Video feed fades to black over 2 seconds
- Map fades in with gold particle effect (like embers)

**Custom Map Styling (Mapbox Dark Theme):**
- **Base:** Charcoal gray (`#1a1a1a`)
- **Roads:** Soft white (`#333333`)
- **Route Path:** Animated gold line (`#C5A059`) with pulsing glow effect
- **Driver Icon:** Stylized crown or chef's toque (not generic car)

**Information Hierarchy:**
```
┌─────────────────────────────────────────┐
│  Your Feast is en Route                │
│  ┌───────────────────────────────────┐ │
│  │                                   │ │
│  │     [Dark Mode Map]               │ │
│  │     [Gold Pulsing Route]          │ │
│  │     [Crown Icon Moving]           │ │
│  │                                   │ │
│  └───────────────────────────────────┘ │
│                                         │
│  Arrives in 12 minutes                 │
│  ━━━━━━━━━━━━━━━━━●━━ 85% complete    │
│                                         │
│  ✓ Picked up from Chef Marco           │
│  ✓ Entered your district               │
│  ⏳ 2 blocks away                       │
└─────────────────────────────────────────┘
```

**Live Updates (Push Notifications):**
- "Your Procession has entered [Neighborhood]"
- "Butler arriving in 5 minutes - prepare for service"

### 5.3 Stage 3: The Arrival (White Glove Delivery)

**Pre-Arrival Prompt (2 minutes before):**
```
┌─────────────────────────────────────────┐
│  Your Butler Has Arrived                │
│                                         │
│  How shall we serve you this evening?   │
│                                         │
│  ○ Door Handoff                        │
│    Quick, contactless delivery          │
│                                         │
│  ○ Entryway Setup                      │
│    Butler arranges items on your       │
│    console table or counter             │
│                                         │
│  ○ Dining Table Service (+ $15)        │
│    Full plating, courses set,          │
│    warming instructions provided        │
│                                         │
│  ○ Talk to Butler                      │
│    Special requests? Call now           │
└─────────────────────────────────────────┘
```

**Post-Delivery:**
- **Photo Confirmation:** Butler uploads image of setup (builds trust + showcases service)
- **Rating Prompt (3 hours later):** "How was your Royal Banquet?"
- **Reorder Shortcut:** "Craft this feast again" one-click button

---

## Module C: The Theatre of Taste (Video Content Hub)

**Dual Interface Strategy:** Serve professional learners and casual scrollers with equal elegance.

### 6.1 The Pro Tier (Cinematic Learning)

**Content Categories:**
1. **Masterclasses** — 20-45 min deep dives (e.g., "Mastering Beef Wellington")
2. **Behind the Menu** — Documentary-style kitchen tours and chef interviews
3. **Ingredient Journeys** — Farm-to-table stories, terroir explorations
4. **Pairing Philosophy** — Sommelier education series
5. **Technique Library** — Searchable database of fundamental skills

**UI Layout (Desktop):**
- **Netflix-Style Carousels:** Horizontal scrolling rows
- **Thumbnail Specs:** 16:9, 1920x1080px minimum, elegant title cards
- **Hover Behavior:** Thumbnail expands 10%, shows duration + difficulty badge
- **Watch Progress:** Gold progress bar beneath saved videos

**Video Player Features:**
- **Chapters:** Jump to specific techniques or recipe steps
- **Ingredient List Sidebar:** Synchronized to video timestamp
- **Watch to Order:** Click on-screen dishes to add to Banquet cart
- **Download for Offline (Premium):** For paid subscribers

**Example Masterclass Card:**
```
┌─────────────────────────────────────────┐
│  [Thumbnail: Chef rolling pasta]        │
│  ⏱ 38:24 · Advanced                    │
├─────────────────────────────────────────┤
│  Fresh Pasta from Scratch               │
│  Chef Isabella Rossi                    │
│  ⭐ 4.9 (2.3K) · 🏆 Connoisseur        │
└─────────────────────────────────────────┘
```

### 6.2 The Community Tier (Social Discovery)

**Content Types:**
1. **Quick Recipes** — 60-90 second tutorials
2. **Home Kitchen Hacks** — Tips, shortcuts, ingredient swaps
3. **Restaurant Reviews** — User-generated dining experiences
4. **Trend Challenges** — "Recreate this Michelin dish at home"

**UI Layout (Mobile-First):**
- **Vertical Scroll:** TikTok/Instagram Reels format (9:16 aspect ratio)
- **Infinite Feed:** Algorithm-free chronological or "Top This Week"
- **Quick Actions:** Like (heart), Save (bookmark), Share, Comment

**Automatic Quality Enhancement:**
- **Color Grading:** All uploads processed with "Sovereign Warmth" LUT
  - +10% saturation on reds/golds
  - +15 contrast for depth
  - Slight vignette for focus
- **Audio Normalization:** Consistent volume levels across uploads
- **Thumbnail Auto-Generation:** AI selects most appetizing frame (manual override available)

**Community Features:**
- **Duet/Stitch:** Users can create side-by-side reactions to recipes
- **Ingredient Tags:** Click a tag (e.g., #truffle) to see all videos featuring it
- **Chef Spotlights:** Partner chefs' accounts verified with gold checkmark

---

## Module D: The Court of Creators (Community & Gamification)

**Mission:** Transform users into culinary storytellers while maintaining platform prestige.

### 7.1 The "Give Back" Kitchen (Recipe Repository)

**Upload Flow:**
1. **Record or Upload:** Video (max 3 min) + written recipe
2. **Tag & Categorize:** Cuisine, difficulty, time, dietary tags
3. **Sovereign Check:** Brief moderation queue (24-hour review for quality/appropriateness)
4. **Publish:** Recipe goes live with creator's profile linked

**Recipe Page Anatomy:**
```
┌─────────────────────────────────────────┐
│  [Video Player - User's Tutorial]       │
├─────────────────────────────────────────┤
│  Truffle Mac & Cheese                   │
│  by @HomeCookAlex (Silver Ring)         │
│  ⭐ 4.7 (89) · 🍴 342 cooked this      │
│                                         │
│  Ingredients          Instructions      │
│  □ 1 lb pasta         1. Boil water... │
│  □ 2 cups cream       2. Make roux...  │
│  [Export List]        [Print Recipe]   │
│                                         │
│  📸 Community Cooks (swipeable gallery) │
│  [User photos of finished dishes]       │
└─────────────────────────────────────────┘
```

**Social Proof Mechanics:**
- **"Cook This" Button:** Users commit to making the recipe
- **24-Hour Check-In:** App prompts user to upload their result photo
- **Community Gallery:** All successful cooks displayed on recipe page
- **Creator Rewards:** Every 100 successful cooks → Bronze Badge → unlocks perks

### 7.2 The Society (Membership Tiers & Gamification)

**Tier System (Inspired by Luxury Memberships):**

| Tier | Badge | Requirements | Benefits |
|------|-------|--------------|----------|
| **Member** | Bronze Ring | Account created | Basic access, community participation |
| **Insider** | Silver Ring | 10 orders OR 5 recipes shared | 5% order discount, priority support |
| **Connoisseur** | Gold Ring | 50 orders OR 20 high-rated recipes | 10% discount, free delivery, early access to new Wings |
| **Curator** | Platinum Ring | Invited only (top 5% contributors) | 15% discount, Red Phone access, exclusive events |
| **Sovereign** | Diamond Crown | Top 1% (calculated quarterly) | 20% discount, personal sommelier, test kitchen invites |

**Progression Mechanics:**
- **XP System:** Transparent point values for actions
  - Order = 10 XP
  - Recipe upload = 50 XP
  - Recipe reaches 100 cooks = 200 XP bonus
  - High-rated review = 25 XP
- **Leaderboard:** Monthly + all-time (opt-in public visibility)
- **Achievements:** Unlockable badges (e.g., "Sushi Master" for 10 Japanese Wing orders)

**Visual Identity:**
- **Rings:** Subtle glow effect on user avatars indicating tier
- **Leaderboard Design:** Clean table with user avatars, tier badges, and XP counts
  - Top 10 highlighted with champagne gold background
  - Current user's rank always visible (sticky row)

### 7.3 Rewards & Incentives

**Connoisseur Tier Unlocks:**
1. **Free Delivery:** All orders (normally $5-12)
2. **Butler Upgrade:** Complimentary Dining Table Service once/month
3. **Early Access:** New cuisine Wings launch 48 hours early
4. **Exclusive Recipes:** Pro Tier masterclasses from partner chefs

**Curator/Sovereign Perks:**
1. **Personal Sommelier:** Dedicated advisor for all orders
2. **Test Kitchen Invites:** Quarterly events to taste R&D dishes
3. **Revenue Share:** Curators earn 5% commission when their recipes are featured in Pro Tier content (for original recipe creators who reach this level)

---

## 8. Technical Architecture

### 8.1 Platform Requirements

**Frontend:**
- **Framework:** React (Web), React Native (Mobile iOS/Android)
- **State Management:** Redux or Zustand for cart/user state
- **Styling:** Tailwind CSS with custom Sovereign theme
- **Animation:** Framer Motion for complex transitions

**Backend:**
- **API:** Node.js + Express or Python/Django REST Framework
- **Database:** PostgreSQL (relational data) + Redis (caching/sessions)
- **Video Storage:** AWS S3 or Cloudflare Stream
- **Live Streaming:** Mux or AWS IVS (Interactive Video Service)

**Third-Party Integrations:**
- **Maps:** Mapbox for custom dark-mode styling
- **Payments:** Stripe (with support for split payments to multiple restaurants)
- **Logistics:** Custom routing algorithm OR integration with DoorDash Drive/Uber Direct for white-label delivery
- **Video Processing:** Mux for transcoding, thumbnail generation, and quality enforcement

### 8.2 Core Systems

**The Multi-Restaurant Cart Logic:**
- **Challenge:** User orders Appetizer from Restaurant A, Main from Restaurant B
- **Solution:**
  1. Backend calculates prep times (API from restaurant POSsystems)
  2. Determines optimal driver route (Traveling Salesman Problem variant)
  3. Schedules pickups so food arrives within 10-minute window
  4. Shows user unified ETA: "Delivery at 8:15 PM" (not separate times)

**Database Schema Highlights:**

**Users Table:**
```
- user_id (PK)
- email, name, phone
- membership_tier (ENUM: Member, Insider, Connoisseur, Curator, Sovereign)
- xp_points (INT)
- created_at, updated_at
```

**Orders Table:**
```
- order_id (PK)
- user_id (FK)
- restaurant_ids (ARRAY) — Handles multi-restaurant orders
- total_amount, tip_amount
- delivery_type (ENUM: Door, Entryway, TableService)
- status (ENUM: Preparing, InTransit, Delivered)
- created_at, delivered_at
```

**Sommelier_Profiles Table:**
```
- sommelier_id (PK)
- name, photo_url, signature_url
- certifications (ARRAY)
- bio (TEXT, 200 chars max)
- specialties (ARRAY: e.g., "Italian wines", "Sake")
```

**Pairings Table:**
```
- pairing_id (PK)
- dish_id (FK)
- wine_id (FK)
- sommelier_id (FK)
- rationale (TEXT) — The "handwritten note"
- conflict_warnings (ARRAY) — Dishes this pairs poorly with
```

**Recipes Table (Community):**
```
- recipe_id (PK)
- creator_id (FK → Users)
- video_url, thumbnail_url
- ingredients (JSON)
- instructions (TEXT)
- cook_count (INT) — How many users made this
- avg_rating (FLOAT)
- status (ENUM: Pending, Approved, Featured)
```

### 8.3 Performance & Scalability

**Live Streaming Infrastructure:**
- **Peak Load:** Assume 1,000 concurrent viewers per kitchen during dinner rush
- **CDN:** Cloudflare or AWS CloudFront for global low-latency delivery
- **Fallback:** If live stream fails, show animated "Kitchen in Progress" placeholder with last-known milestone

**Search & Discovery:**
- **Elasticsearch:** For fast, fuzzy search across dishes, recipes, videos
- **Indexing:** Real-time updates when new content published

**Security:**
- **PCI Compliance:** For payment processing (Stripe handles most heavy lifting)
- **Video Privacy:** Partner kitchens can toggle "Blur Background" mode
- **User Data:** GDPR/CCPA compliant data export and deletion tools

---

## 9. Go-to-Market Strategy

### 9.1 Launch Phases

**Phase 1: Closed Beta (Months 1-2)**
- Target: 500 early adopters in single metro (NYC, SF, or LA)
- Focus: Test multi-restaurant logistics, gather UX feedback
- Incentive: Lifetime 15% discount for beta testers

**Phase 2: Public Launch (Month 3)**
- Open to full metro area
- 10 partner restaurants across 6 Cuisine Wings
- Marketing: Influencer partnerships (food YouTubers, luxury lifestyle accounts)

**Phase 3: Content Expansion (Months 4-6)**
- Launch Pro Tier masterclasses (partner with 3-5 celebrity chefs)
- Community features go live (Give Back Kitchen, Leaderboards)
- PR push: "The Netflix of Fine Dining"

**Phase 4: Geographic Expansion (Months 7-12)**
- Expand to 2-3 additional metros
- Franchise model for sommeliers (independent experts join platform)

### 9.2 Revenue Model

**Commission Structure:**
- **Restaurant Orders:** 15-20% commission (competitive with DoorDash/Uber Eats, justified by premium clientele)
- **Alcohol Sales:** 10% commission to sommelier + 10% to platform

**Subscription Tiers:**
- **Concierge Membership:** $29/month
  - Priority butler service
  - 10% discount on all orders
  - Exclusive recipes library access
- **Platinum Membership:** $99/month
  - All Concierge perks
  - Free delivery + 1 free Butler Upgrade/month
  - Early access to new Wings + test kitchen events

**Content Monetization:**
- **Pro Tier Subscription:** $19/month or $180/year
  - Access to all masterclasses and premium content
  - Download for offline viewing
- **À La Carte Masterclasses:** $15-30 per video (for non-subscribers)

**B2B Opportunities:**
- **Corporate Gifting:** Branded Sovereign gift cards
- **Event Catering:** White glove service for company dinners (minimum $500 orders)

---

## 10. Success Metrics (KPIs)

### 10.1 Business Metrics
- **GMV (Gross Merchandise Value):** Monthly order volume
- **Average Order Value (AOV):** Target $85+ (vs. $30-40 for typical delivery)
- **Customer Lifetime Value (LTV):** Target $2,500 over 18 months
- **Retention Rate:** % of users ordering 2+ times/month
- **Membership Conversion:** % of free users upgrading to Concierge/Platinum

### 10.2 Product Engagement
- **Live Stream Viewership:** % of orders where user watches kitchen stream
- **Course Builder Usage:** % of orders using multi-restaurant feature
- **Pairing Adoption:** % of orders including sommelier recommendation
- **Community Activity:** Recipes uploaded per week, cook-this completions
- **Video Completion Rate:** % of Pro Tier videos watched to 80%+

### 10.3 Quality Metrics
- **On-Time Delivery:** >95% within 15-minute window
- **Food Quality Ratings:** Avg 4.5+ stars
- **Butler Service NPS:** Net Promoter Score for White Glove delivery
- **Content Moderation Speed:** 24-hour max review time for community uploads

---

## 11. Risk Mitigation

### 11.1 Operational Risks

**Risk:** Restaurant partner fails to meet quality standards  
**Mitigation:** Quarterly audits, user ratings trigger review, 3-strike removal policy

**Risk:** Live stream technical failures during peak hours  
**Mitigation:** Redundant streaming infrastructure, graceful degradation to progress bar + milestones

**Risk:** Multi-restaurant orders create delivery delays  
**Mitigation:** AI-powered route optimization, max 3 restaurants per order, clear delay warnings before checkout

### 11.2 Market Risks

**Risk:** User price sensitivity (delivery apps race to bottom on fees)  
**Mitigation:** Position as luxury alternative, not commodity service. Target affluent demos (HHI $150K+)

**Risk:** Restaurant fatigue with commission rates  
**Mitigation:** Prove premium customer acquisition, offer marketing support, transparent fee structure

### 11.3 Content Risks

**Risk:** Community uploads contain low-quality or inappropriate content  
**Mitigation:** 24-hour moderation queue, AI flagging for explicit content, community reporting system

**Risk:** Copyright claims on Pro Tier content  
**Mitigation:** Exclusive partnerships with chefs (original content), legal team for clearances

---

## 12. Future Roadmap (12-24 Months)

### Phase 5: Sovereign Experiences
- **Pop-Up Dinners:** Quarterly IRL events with partner chefs
- **Culinary Travel:** Curated food tours (e.g., "Wine Country Weekend")
- **Private Chef Network:** On-demand in-home chef bookings

### Phase 6: AI-Assisted (But Not AI-Replaced) Features
- **Dish Recommendation Engine:** Uses order history + preferences (but always shows sommelier overrides)
- **Voice Ordering:** "Alexa, order my usual from The Italian Wing"
- **Smart Pantry Integration:** Connect to smart fridges to suggest recipes based on ingredients

### Phase 7: B2B Expansion
- **Corporate Platform:** Branded portals for companies (expensable meals, team events)
- **Hotel Partnerships:** In-room dining powered by Sovereign
- **Airline Lounges:** Pre-order gourmet meals for pickup before flights

---

## 13. Appendices

### A. Competitor Analysis

| Competitor | Strength | Our Differentiation |
|------------|----------|---------------------|
| DoorDash/Uber Eats | Market dominance, logistics | We're luxury-first, not volume-first |
| Caviar | Upscale positioning | We add education + community, not just delivery |
| MasterClass | Premium education | We integrate learning with ordering |
| TikTok/Instagram | Social engagement | Curated quality, monetization for creators |

### B. User Personas

**Persona 1: "The Connoisseur" (Primary)**
- Age: 35-55, HHI $200K+
- Values: Quality > convenience, authenticity, learning
- Pain Point: Tired of mediocre delivery, wants restaurant experience at home

**Persona 2: "The Aspiring Chef" (Secondary)**
- Age: 25-40, HHI $75K+
- Values: Education, community recognition
- Pain Point: Wants to learn from pros but can't afford culinary school

**Persona 3: "The Corporate Host" (B2B)**
- Age: 40-60, corporate card
- Values: Reliability, white glove service, wow factor
- Pain Point: Needs impressive catering that doesn't feel like "catering"

### C. Legal & Compliance Checklist
- [ ] Food handling permits (varies by state)
- [ ] Alcohol delivery licenses (state-specific, partner with licensed retailers)
- [ ] GDPR/CCPA compliance for user data
- [ ] Accessibility (WCAG 2.1 AA compliance for web/app)
- [ ] Terms of Service (community content ownership, moderation rights)
- [ ] Sommelier credential verification system

---

**Document Owner:** Product Team  
**Last Reviewed:** November 30, 2025  
**Next Review:** January 2026

---

## Key Improvements Made:

1. **Structured Hierarchy:** Clear sections with numbered sub-sections for easy navigation
2. **Visual Aids:** Added ASCII mockups, tables, and formatted code blocks
3. **Quantified Specs:** Specific dimensions, response times, and performance targets
4. **Risk Analysis:** Added comprehensive risk mitigation section
5. **User Personas:** Defined target users with pain points
6. **Success Metrics:** Concrete KPIs to measure platform health
7. **Technical Depth:** Detailed database schemas, API requirements, and infrastructure needs
8. **Roadmap:** Clear phased rollout with future vision
9. **Competitive Positioning:** Explicit differentiation from competitors
10. **Legal/Compliance:** Checklist for regulatory requirements

This PRD is now ready for engineering handoff, investor presentations, and cross-functional alignment. Would you like me to expand any specific section or create supporting documents (e.g., API specification, user flow diagrams)?
