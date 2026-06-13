# AI Native Shopper CRM Product Specification

## 1. Product Vision

Build an AI-native CRM platform that helps consumer brands understand shoppers, create intelligent customer segments, generate campaigns, simulate customer communication, track engagement, and receive actionable AI recommendations.

The product should feel like a modern CRM, campaign command center, and AI growth strategist in one platform.

The goal is not to build a full enterprise CRM in 4 days. The goal is to build a credible, demo-ready MVP that shows how AI can help a brand marketer go from:

> I have customer and order data.
>
> I know whom to target, what to say, where to send it, and what worked.

### Core Product Promise

For a D2C, retail, or omnichannel brand:

> Upload or manage your customer and order data, ask AI to find growth opportunities, create smart segments, launch simulated campaigns, and understand performance in one place.

### Strategic Positioning

This is not just another CRM dashboard.

It is an AI-native Shopper CRM where AI helps with:

- Segment discovery
- Campaign ideation
- Copy generation
- Channel strategy
- Performance explanation
- Next-best-action recommendations
- Retention, reactivation, and upsell planning

### Primary Business Outcomes

The platform should help brands:

1. Increase repeat purchases
2. Reduce customer churn
3. Improve campaign conversion
4. Personalize communication at scale
5. Save marketer time
6. Turn raw shopper and order data into decisions

## 2. User Personas

### Persona 1: Growth Marketer

**Role:** Runs campaigns across email, SMS, WhatsApp, push, and ads.

**Goals:**

- Create targeted campaigns quickly
- Increase conversions
- Improve retention and repeat purchases
- Understand which segment responds best

**Pain Points:**

- Manual segmentation is slow
- Campaign copy takes time
- Hard to know what campaign to run next
- Performance data is scattered

**Key Features Needed:**

- Audience builder
- AI campaign generator
- Campaign performance dashboard
- AI recommendations

### Persona 2: CRM Manager

**Role:** Owns lifecycle marketing and customer engagement.

**Goals:**

- Maintain clean customer data
- Build lifecycle segments
- Track communication events
- Improve customer retention

**Pain Points:**

- Customer data is fragmented
- Segments are hard to manage
- Difficult to track customer-level communication history

**Key Features Needed:**

- Customer profiles
- Order history
- Segment manager
- Communication timeline
- Campaign history

### Persona 3: Brand Founder / CXO

**Role:** Wants high-level visibility into growth and customer health.

**Goals:**

- Understand business health
- See campaign ROI
- Identify revenue opportunities
- Get AI-generated strategic recommendations

**Pain Points:**

- Does not want to inspect raw data
- Needs clear answers, not complex dashboards
- Wants to know what to do next

**Key Features Needed:**

- Executive dashboard
- Revenue and engagement summaries
- AI insights
- Campaign performance reports

### Persona 4: Data / Ops Admin

**Role:** Manages customer and order data import and platform setup.

**Goals:**

- Ensure data is available and clean
- Import customers and orders
- Validate records
- Monitor system state

**Pain Points:**

- Messy data imports
- Duplicate customers
- Missing fields
- No visibility into data quality

**Key Features Needed:**

- Customer CRUD
- Order CRUD
- Data import status
- Error handling
- Basic validation

## 3. Product Modules

### Module 1: Authentication & Workspace

**Purpose:** Allow users to securely access the CRM and operate inside a brand workspace.

**MVP Scope:**

- Login
- Register
- JWT authentication
- Protected routes
- User context
- Brand/workspace placeholder

**Future Scope:**

- Role-based access control
- Multiple workspaces
- Invite teammates
- Audit logs

### Module 2: Customer Data Management

**Purpose:** Store and manage shopper/customer profiles.

**Core Data Fields:**

- Name
- Email
- Phone
- Gender
- City
- Tags
- Total spend
- Order count
- Last order date
- Created date

**MVP Features:**

- View customers list
- Search customers
- Filter by city, spend, order count, and last purchase
- View customer profile
- Add, edit, and delete customer
- Show customer metrics

**Future Features:**

- CSV import
- Duplicate detection
- Customer merge
- Consent management
- Customer lifetime value prediction

### Module 3: Order Data Management

**Purpose:** Store shopper transaction history and link it to customers.

**Core Data Fields:**

- Order ID
- Customer ID
- Amount
- Items
- Category
- Status
- Order date
- Channel/source

**MVP Features:**

- View orders list
- Create, edit, and delete order
- Link orders to customers
- Show customer order history
- Calculate basic metrics

**Future Features:**

- Shopify/WooCommerce integration
- Return/refund tracking
- SKU-level analytics
- Product affinity modeling

### Module 4: Audience Segmentation

**Purpose:** Allow marketers to create target groups based on customer and order attributes.

**Segment Types:**

- Rule-based segments
- AI-suggested segments

**MVP Segment Rules:**

- Total spend greater than / less than
- Order count greater than / less than
- Last order before / after date
- City equals
- Tags include
- Inactive customers
- High-value customers

**MVP Features:**

- Create segment
- Define rules
- Preview matching customers
- Save segment
- View segment size
- Delete segment

**Example Segments:**

- High-value customers
- At-risk customers
- First-time buyers
- Inactive for 60 days
- Customers from Mumbai
- Frequent buyers
- Low spend but high engagement

**Future Features:**

- Nested AND/OR logic
- Predictive segments
- RFM segmentation
- AI natural language segment creation
- Segment overlap analysis

### Module 5: AI Campaign Generator

**Purpose:** Use AI to help marketers generate campaign ideas and communication copy.

**MVP Inputs:**

- Campaign goal
- Selected segment
- Channel
- Tone
- Offer
- Brand context

**Campaign Goals:**

- Repeat purchase
- Win-back
- Upsell
- Cross-sell
- Festive sale
- New product launch
- Loyalty reward

**Channels:**

- Email
- SMS
- WhatsApp
- Push notification

**MVP Outputs:**

- Campaign name
- Campaign objective
- Suggested subject line
- Message copy
- CTA
- Recommended channel
- Reasoning
- Expected audience behavior

**AI Provider:** OpenRouter API

**Future Features:**

- A/B variants
- Multilingual copy
- Brand voice training
- Send-time optimization
- Personalized copy per customer

### Module 6: Campaign Management

**Purpose:** Store and manage generated or manually created campaigns.

**MVP Features:**

- Create campaign
- Save AI-generated campaign
- Select segment
- Select channel
- Set campaign status
- Simulate sending
- View campaign details

**Campaign Statuses:**

- Draft
- Scheduled
- Sent
- Completed

**Future Features:**

- Campaign calendar
- Approval workflow
- Real delivery integrations
- Campaign templates
- Journey automation

### Module 7: Channel Simulation Service

**Purpose:** Simulate communication delivery without integrating real SMS, email, WhatsApp, or push providers.

**MVP Features:**

- Simulate campaign send
- Generate communication events
- Mark events as sent, delivered, opened, clicked, failed, and converted
- Store events in database
- Show event timeline

**Simulated Event Types:**

- Sent
- Delivered
- Opened
- Clicked
- Failed
- Converted

**Why Simulation First:**

Real channel integrations are expensive and time-consuming. For a 4-day MVP, simulation proves the platform logic without dependency on Twilio, Meta, SendGrid, or Firebase.

**Future Features:**

- Email integration
- WhatsApp Cloud API
- SMS gateway
- Push notifications
- Webhooks
- Delivery retries

### Module 8: Communication Event Tracking

**Purpose:** Track every campaign communication event against customers.

**MVP Features:**

- Store event per customer per campaign
- Event type
- Timestamp
- Channel
- Status
- Campaign reference
- Customer reference

**Views:**

- Campaign event feed
- Customer communication timeline
- Aggregated performance metrics

**Future Features:**

- Real-time event ingestion
- Webhook ingestion
- Attribution modeling
- Unsubscribe tracking

### Module 9: Campaign Performance Analytics

**Purpose:** Help users understand how campaigns performed.

**MVP Metrics:**

- Audience size
- Sent count
- Delivered count
- Open count
- Click count
- Conversion count
- Failed count
- Delivery rate
- Open rate
- Click rate
- Conversion rate

**MVP Views:**

- Campaign performance page
- Channel breakdown
- Event funnel
- Segment-level summary

**Future Metrics:**

- Revenue generated
- Average order value
- Incremental lift
- ROI
- Cohort retention
- LTV movement

### Module 10: AI Recommendations

**Purpose:** Turn CRM and campaign data into clear next actions.

**MVP Recommendation Types:**

- Re-engage inactive customers
- Create offer for high-value customers
- Run win-back campaign for customers inactive over 60 days
- Promote best-selling category to repeat buyers
- Improve click rate by testing shorter WhatsApp copy

**MVP Inputs to AI:**

- Customer summary
- Order summary
- Segment summary
- Campaign performance summary

**MVP Output:**

- Recommendation title
- Reason
- Suggested segment
- Suggested campaign idea
- Suggested channel
- Priority level

**Future Features:**

- Autonomous campaign suggestions
- Weekly growth report
- Natural language CRM analyst
- Forecasted campaign impact
- Budget allocation recommendations

## 4. User Journeys

### Journey 1: Brand User Onboarding

1. User registers
2. User logs in
3. User lands on dashboard
4. User sees sample CRM data or empty state
5. User adds customers and orders
6. Dashboard updates with basic metrics

**MVP Decision:** Use seeded/demo data to make the product feel alive immediately.

### Journey 2: Create Customer Segment

1. User opens Audience Segments
2. User clicks Create Segment
3. User adds rules, such as total spend greater than 5000 or last order older than 60 days
4. System previews matching customers
5. User saves segment
6. Segment appears in segment list

### Journey 3: Generate AI Campaign

1. User opens Campaigns
2. User clicks Create Campaign
3. User selects segment
4. User selects campaign goal
5. User selects channel
6. User adds offer/tone
7. User clicks Generate with AI
8. AI returns campaign copy and reasoning
9. User edits and saves campaign

### Journey 4: Simulate Campaign Send

1. User opens saved campaign
2. User clicks Simulate Send
3. Channel service creates communication events
4. Events are stored per customer
5. Campaign status changes to Sent/Completed
6. Performance metrics become available

### Journey 5: Analyze Performance

1. User opens Campaign Performance
2. User selects campaign
3. User views funnel: sent, delivered, opened, clicked, converted
4. User checks rates
5. User reads AI explanation of performance

### Journey 6: Get AI Recommendations

1. User opens AI Insights
2. System summarizes CRM and campaign data
3. AI generates recommendations
4. User can convert a recommendation into a campaign idea

## 5. MVP Features

The MVP should be scoped for a strong 4-day build.

### Must-Have MVP

**Authentication**

- Register
- Login
- JWT-based auth
- Protected app routes

**Dashboard**

- Total customers
- Total orders
- Total revenue
- Active segments
- Campaigns sent
- Recent activity
- AI insight card

**Customers**

- Customer list
- Customer details
- Add, edit, and delete customer
- Search/filter customers

**Orders**

- Order list
- Add, edit, and delete order
- Link order to customer
- Basic revenue calculation

**Segments**

- Rule-based segment builder
- Segment preview
- Save segment
- Segment list

**Campaigns**

- Campaign list
- Create campaign
- Generate campaign using OpenRouter
- Save campaign
- Select segment and channel

**Channel Simulation**

- Simulate send
- Generate mock events
- Store events

**Performance**

- Campaign metrics
- Event funnel
- Channel summary

**AI Recommendations**

- Generate recommendations from CRM/campaign summary
- Display actionable cards

## 6. Stretch Features

Only build these if MVP is complete.

### High-Value Stretch

1. CSV upload for customers and orders
2. Natural language segment creation
3. AI-generated campaign variants
4. AI performance explanation
5. Customer communication timeline
6. Campaign calendar
7. Segment templates

### Medium-Value Stretch

1. Role-based permissions
2. Advanced filters
3. RFM analysis
4. Export segment as CSV
5. Campaign duplication
6. Dark mode
7. Notification center

### Low-Value for 4-Day Build

1. Real WhatsApp integration
2. Real SMS integration
3. Real email provider
4. Payment/billing
5. Complex workflow automation
6. Enterprise admin controls
7. Multi-brand hierarchy

## 7. Required Screens

### Core App Screens

1. Login
2. Register
3. Dashboard
4. Customers list
5. Customer detail
6. Orders list
7. Segments list
8. Segment builder
9. Campaigns list
10. Campaign create/edit
11. Campaign detail
12. Campaign performance
13. AI recommendations
14. Settings

### Optional Screens

1. Import data
2. Campaign calendar
3. Customer communication timeline
4. Segment templates
5. AI chat analyst

## 8. Navigation Structure

### Primary Sidebar Navigation

1. Dashboard
2. Customers
3. Orders
4. Segments
5. Campaigns
6. Performance
7. AI Insights
8. Settings

### Campaign Sub-Navigation

- All Campaigns
- Create Campaign
- Drafts
- Sent Campaigns
- Performance

### Customer Detail Tabs

- Profile
- Orders
- Campaign Events
- Segments

### Campaign Detail Tabs

- Overview
- Audience
- Message
- Events
- Performance
- AI Analysis

## 9. What Not To Build

For a 4-day startup CTO build, avoid anything that slows down demo value.

### Do Not Build Yet

1. Real email/SMS/WhatsApp sending
2. Complex journey automation builder
3. Drag-and-drop workflow canvas
4. Enterprise permission system
5. Billing/subscriptions
6. Multi-tenant organization hierarchy
7. Native mobile app
8. Complex data warehouse sync
9. Advanced attribution modeling
10. Custom report builder
11. Full customer support ticketing
12. Loyalty points engine
13. Product catalog management beyond simple order items
14. Real-time notification infrastructure
15. Overly complex AI chat interface

**Reason:** The MVP must prove the core loop:

> Data -> Segment -> AI Campaign -> Simulated Send -> Events -> Performance -> AI Recommendation

Anything outside this loop should be deferred.

## 10. Feature Prioritization

### Priority Framework

Use this scoring model:

- **Impact:** Does it prove the product value?
- **Speed:** Can it be built quickly?
- **Demo Value:** Will it impress users, investors, or evaluators?
- **Dependency:** Does another feature rely on it?

### P0: Critical MVP

These must be built.

| Feature | Impact | Reason |
| --- | --- | --- |
| Auth | High | Required for app access |
| Dashboard | High | First impression and product overview |
| Customer CRUD | High | Foundation data |
| Order CRUD | High | Enables revenue and behavior analysis |
| Segment Builder | Very High | Core CRM capability |
| AI Campaign Generator | Very High | AI-native differentiation |
| Campaign Save/View | High | Core workflow |
| Simulated Send | Very High | Proves channel architecture |
| Communication Events | High | Enables performance tracking |
| Campaign Analytics | High | Shows measurable outcome |
| AI Recommendations | Very High | Strategic AI value |

### P1: Strong Stretch

Build after P0 if time remains.

| Feature | Impact | Reason |
| --- | --- | --- |
| CSV Import | High | Makes product feel practical |
| Customer Timeline | High | Strong CRM experience |
| AI Performance Summary | High | Enhances intelligence layer |
| Campaign Variants | Medium-High | Shows AI usefulness |
| Segment Templates | Medium | Speeds up demo workflow |

### P2: Later

| Feature | Impact | Reason |
| --- | --- | --- |
| Real WhatsApp/SMS/Email | High, but slow | Integration-heavy |
| RBAC | Medium | Not needed for demo |
| Campaign Calendar | Medium | Nice but not core |
| Workflow Automation | High, but slow | Too large for 4 days |
| Advanced Analytics | Medium | Can wait |

## 11. Recommended 4-Day Build Plan

### Day 1: Foundation

**Backend**

- Set up Express app
- Connect MongoDB
- Create models: User, Customer, Order, Segment, Campaign, CommunicationEvent
- Auth APIs
- Customer APIs
- Order APIs

**Frontend**

- Vite + React setup
- Tailwind setup
- Auth context
- Layout/sidebar
- Login/register
- Dashboard shell
- Customers and orders pages

### Day 2: CRM Core

**Backend**

- Segment APIs
- Rule evaluation logic
- Dashboard metrics API

**Frontend**

- Segment list
- Segment builder
- Segment preview
- Customer detail page
- Dashboard metrics

### Day 3: AI + Campaigns

**Backend**

- OpenRouter integration
- Campaign generation API
- Campaign CRUD
- Channel simulation service
- Communication event generation

**Frontend**

- Campaign list
- Campaign create page
- AI generation form
- Campaign detail page
- Simulate send button

### Day 4: Analytics + Polish

**Backend**

- Campaign performance API
- AI recommendations API
- Seed/demo data
- Error handling

**Frontend**

- Performance dashboard
- AI insights page
- Empty states
- Loading states
- UI polish
- Final demo flow testing

## 12. Suggested Data Models

### User

```js
{
  name,
  email,
  passwordHash,
  role,
  createdAt
}
```

### Customer

```js
{
  name,
  email,
  phone,
  gender,
  city,
  tags,
  totalSpend,
  orderCount,
  lastOrderDate,
  createdAt
}
```

### Order

```js
{
  customerId,
  amount,
  items,
  category,
  status,
  source,
  orderDate,
  createdAt
}
```

### Segment

```js
{
  name,
  description,
  rules,
  customerCount,
  createdBy,
  createdAt
}
```

### Campaign

```js
{
  name,
  goal,
  segmentId,
  channel,
  subject,
  message,
  cta,
  status,
  aiReasoning,
  createdAt,
  sentAt
}
```

### CommunicationEvent

```js
{
  campaignId,
  customerId,
  channel,
  eventType,
  status,
  timestamp
}
```

## 13. AI Product Architecture

### AI Use Cases

1. Generate campaign copy
2. Suggest campaign strategy
3. Explain performance
4. Recommend next actions
5. Suggest audience segments

### AI Design Principle

AI should not be decorative. It should help users make or accelerate decisions.

### Recommended AI API Endpoints

```txt
POST /api/ai/generate-campaign
POST /api/ai/recommendations
POST /api/ai/analyze-performance
POST /api/ai/suggest-segments
```

### Example Campaign Prompt

```txt
You are an expert CRM marketer for a consumer brand.

Create a campaign for:
Goal: Win back inactive customers
Segment: Customers who have not ordered in 60 days
Channel: WhatsApp
Tone: Friendly and premium
Offer: 15% off

Return:
- Campaign name
- Message
- CTA
- Reasoning
- Expected customer behavior
```

## 14. Success Metrics

### Product Usage Metrics

- Number of customers added
- Number of segments created
- Number of campaigns generated
- Number of campaigns simulated
- Number of AI recommendations viewed

### Campaign Metrics

- Delivery rate
- Open rate
- Click rate
- Conversion rate
- Segment performance
- Channel performance

### Business Metrics

- Repeat purchase rate
- Revenue from campaigns
- Customer reactivation rate
- Average order value
- Customer lifetime value

For MVP, campaign revenue can be simulated.

## 15. MVP North Star

The MVP should make this flow impressive and smooth:

1. View shopper dashboard
2. Create audience segment
3. Generate AI campaign
4. Simulate send
5. See campaign performance
6. Receive AI recommendation for next campaign

Build this loop well, and the platform will feel credible even without real channel integrations.
