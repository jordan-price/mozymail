# ✨ MozyMail - AI Email Organization Made Simple

**Transform your email chaos into organized productivity with AI-powered intelligence.**

MozyMail is an AI email agent that automatically extracts tasks, reminders, and inspiration from your emails. Simply forward any email to **send@mozymail.com** and watch our AI organize your life.

## 🚀 How It Works

1. **Forward or Send** any email to `send@mozymail.com`
2. **AI Processes** your email content automatically
3. **Get Organized** with extracted tasks, reminders, and notes
4. **Access Everything** in your beautiful dashboard

## ✨ What MozyMail Does

- 📋 **Extracts Tasks** - Finds action items and deadlines automatically
- ⏰ **Sets Reminders** - Never forget important follow-ups
- 💡 **Captures Ideas** - Saves inspiration and insights for later
- 🏷️ **Smart Tagging** - Organizes everything with intelligent categories
- 🔍 **Full Search** - Find anything instantly across all your items

## 🎯 Try It Now

**Live Demo**: [mozymail.com](https://mozymail.com)

### Quick Test:
Send this email to `send@mozymail.com`:
```
Subject: Project Meeting Next Week
Hi there! Don't forget we have our quarterly review meeting next Tuesday at 2 PM. 
Please bring your project updates and the budget proposal we discussed.
Also, I found this great article about productivity tips: https://example.com/tips
```

**MozyMail will automatically extract:**
- ✅ Task: "Attend quarterly review meeting" (Due: Next Tuesday 2 PM)
- 📝 Reminder: "Bring project updates and budget proposal"
- 💡 Inspiration: "Productivity tips article" with saved link

## 🎨 Beautiful Dashboard

![MozyMail Dashboard](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/avrmztsy6egus8u4y5ld.png)

![Example Task](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wd3tv1rrsbr9su6g12g9.png)

## 🔒 Privacy First

- Only processes emails you explicitly send or forward
- No access to your email accounts required
- Secure processing with enterprise-grade encryption
- Your data remains private and protected

## 💰 Simple Pricing

**🆓 Free Trial** - 30 days, no credit card required

**📧 Essential Plan** - $19/month
- Unlimited email processing
- AI task extraction
- Smart reminders
- Full dashboard access

**⭐ Premium Plan** - $39/month
- Everything in Essential
- Priority AI processing
- Advanced automation
- Team collaboration features

## 🌟 Perfect For

- **Busy Professionals** who email themselves reminders
- **Project Managers** tracking action items from meetings
- **Entrepreneurs** capturing ideas and follow-ups
- **Anyone** who wants to stay organized effortlessly

## 🎉 Get Started

1. Visit [mozymail.com](https://mozymail.com)
2. Send an email to `send@mozymail.com`
3. Sign up with the same email address
4. See your AI-organized items instantly!

## 🛠️ How It Works Under the Hood

For developers curious about the technical implementation:

### Email Processing Pipeline

```javascript
// 1. Postmark webhook receives inbound email
const emailData = {
  MessageID: "abc123",
  From: "user@example.com",
  Subject: "Project deadline tomorrow",
  TextBody: "Don't forget the presentation is due tomorrow at 5 PM",
  HtmlBody: "<p>Don't forget the presentation is due tomorrow at 5 PM</p>",
  Attachments: []
};

// 2. Email queued for AI processing
ProcessEmailJob.dispatch(emailData);
```

### AI Extraction Process

```javascript
// 3. OpenAI analyzes email content
const aiPrompt = `
Analyze this email and extract actionable items:
Subject: ${email.subject}
Body: ${email.body}

Extract:
- Tasks (with due dates if mentioned)
- Reminders 
- Ideas/inspiration
- Important links
`;

const aiResponse = {
  tasks: [
    {
      title: "Complete presentation",
      due_date: "2024-01-15T17:00:00Z",
      priority: "high"
    }
  ],
  reminders: [
    {
      title: "Presentation deadline",
      remind_at: "2024-01-15T16:00:00Z"
    }
  ],
  inspiration: [],
  links: []
};
```

### Data Structure

```javascript
// 4. Processed items stored in database
const processedItem = {
  id: "item_123",
  user_id: "user_456",
  type: "task", // task, reminder, note, inspiration
  title: "Complete presentation",
  content: "Presentation is due tomorrow at 5 PM",
  due_at: "2024-01-15T17:00:00Z",
  completed: false,
  tags: ["work", "deadline"],
  source_email: {
    id: "email_789",
    subject: "Project deadline tomorrow",
    from: "user@example.com"
  },
  ai_confidence: 0.95,
  created_at: "2024-01-14T10:00:00Z"
};
```

### Frontend Dashboard

```tsx
// 5. React component displays organized items
function Dashboard() {
  const { data: items } = useQuery('/api/items');
  
  return (
    <div className="space-y-4">
      {items.map(item => (
        <ItemCard 
          key={item.id}
          item={item}
          onComplete={() => markComplete(item.id)}
          onView={() => openEmailModal(item.source_email)}
        />
      ))}
    </div>
  );
}
```

### Tech Stack

**Backend:**
- Laravel 12 (PHP)
- PostgreSQL database
- OpenAI GPT-4 API
- Postmark webhooks
- Queue system for processing

**Frontend:**
- React 19 with TypeScript
- Inertia.js for SPA experience
- Tailwind CSS + shadcn/ui
- Real-time updates

**Infrastructure:**
- AWS S3 for attachments
- Redis for caching/queues
- Stripe for billing

---

**Questions?** Email us at hello@mozymail.com

**Built with ❤️ for people who want to stay organized without the hassle.** 
