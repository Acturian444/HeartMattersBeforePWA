# Heart Matters - Project Specification

## Current Website Structure

### 1. Core Pages & Features
- **Home Page**
  - Hero section with "YOUR HEART MATTERS"
  - Mission statement ("What You Carry Matters")
  - Scrolling quotes bar
  - Call-to-action to join movement
  - Mobile-responsive design

- **Join Movement Page**
  - Movement information
  - Newsletter signup (Google Forms integration)
  - Social media links (Instagram, TikTok)
  - Contact information

- **Heart Room Page**
  - Show information
  - Social media integration
  - Contact section

- **Share Story**
  - Tally form integration
  - External form submission

### 2. Technical Stack
- HTML/CSS
- JavaScript
- Mobile-first design
- Responsive images
- Google Forms integration
- Social media integration

### 3. User Experience
- Responsive design
- Mobile-optimized navigation
- Hamburger menu for mobile
- Smooth transitions
- Social media integration

## Planned Let It Out Feature

### 1. User Stories

#### Anonymous Posting
```gherkin
As a user
I want to express my feelings anonymously
So that I can share without fear of judgment

Given I am on the Let It Out page
When I type my feelings
And select emotion tags
And optionally add my city
Then I can submit my post anonymously
And receive a gentle confirmation
```

#### Emotion Tagging
```gherkin
As a user
I want to tag my emotions
So that others can find similar experiences

Given I am writing a post
When I type my feelings
Then I see suggested emotion tags
And I can select up to 3 tags
And these tags help categorize my post
```

#### Content Discovery
```gherkin
As a user
I want to find posts that resonate with me
So that I feel less alone

Given I am on the Wall tab
When I use the filter system
Then I can find posts by emotion
And optionally by city
And see the most recent or most felt posts
```

### 2. Feature Logic

#### Anonymous ID System
1. **Generation**
   - Power word + Trait + Random number
   - Bilingual support (EN/ES)
   - localStorage persistence
   - Session-based tracking

2. **Storage**
   - Local device only
   - No cross-device sync
   - Clear on browser clear
   - Incognito mode detection

#### Emotion Tagging System
1. **Categories**
   - Pain & Pressure
   - Hidden & Buried
   - Hope & Healing
   - Longing & Love
   - Identity & Self
   - Transformation & Release

2. **Selection**
   - Auto-suggest while typing
   - Manual selection option
   - Maximum 3 tags
   - Category organization

#### Content Moderation
1. **Automated**
   - Keyword filtering
   - Sensitive content detection
   - Spam prevention
   - Rate limiting

2. **Manual**
   - Report system
   - Moderation queue
   - Content review
   - Support resources

### 3. Technical Implementation

#### Database Structure (Firestore)
```javascript
// Posts Collection
{
  id: string,
  content: string,
  emotionTags: string[],
  city: string?,
  timestamp: timestamp,
  anonymousId: string,
  feltCount: number,
  replyCount: number
}

// Replies Subcollection
{
  id: string,
  content: string,
  timestamp: timestamp,
  anonymousId: string,
  postId: string
}
```

### 4. UI/UX Design

#### Layout
1. **Write Tab**
   - Large text input
   - Emotion tag selector
   - City input (optional)
   - Submit button

2. **Wall Tab**
   - Filter bar
   - Post cards
   - Infinite scroll
   - Action buttons

#### Components
1. **Post Card**
   - Anonymous ID
   - Content
   - Emotion tags
   - City tag
   - Timestamp
   - Action buttons

2. **Filter System**
   - Emotion selector
   - City filter
   - Sort options
   - Search bar

### 5. Performance Requirements
- Initial load < 2s
- Post submission < 1s
- Filter updates < 500ms
- Offline support

### 6. Security & Privacy
- No personal data
- Anonymous IDs
- Content encryption
- Secure API calls
- Content moderation
- Report system
- Privacy controls
- Support resources

### 7. Implementation Phases

#### Phase 1: Foundation
- Basic PWA setup
- Post creation
- Feed display
- Emotion tagging

#### Phase 2: Enhancement
- Real-time updates
- Offline support
- Content sharing
- Language support

#### Phase 3: Security
- Content moderation
- Privacy controls
- Performance optimization
- Monitoring setup 