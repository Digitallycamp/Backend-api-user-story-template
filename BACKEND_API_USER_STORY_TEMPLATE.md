# 📋 Backend API User Story Template

## Story Overview

**Story ID:** [e.g., API-001]  
**Story Title:** [Brief, descriptive name]  
**Priority:** ☐ Critical  ☐ High  ☐ Medium  ☐ Low  
**Estimated Effort:** ☐ Small (1-2 days)  ☐ Medium (3-5 days)  ☐ Large (1-2 weeks)

---

## 1. 📖 User Story

**As a** [type of user/system]  
**I want to** [action/capability]  
**So that** [business value/outcome]

**Example:**  
*As a mobile app user*  
*I want to register a new account using my email*  
*So that I can access the platform and save my preferences*

---

## 2. 🎯 Business Goal

**What problem does this solve?**  
[Explain in 1-2 sentences why this feature is needed]

**Example:**  
*We need a registration system to allow new users to create accounts and access our platform. This is essential for user onboarding and tracking user activity.*

---

## 3. 📥 Input (What the API Receives)

**What information does the user/app send?**

| Field Name | Description | Required? | Example |
|------------|-------------|-----------|---------|
| first_name | User's first name | Yes | "John" |
| last_name | User's last name | Yes | "Doe" |
| email | User's email address | Yes | "john@example.com" |
| password | User's password | Yes | "SecurePass123!" |
| phone | User's phone number | No | "+233501234567" |

---

## 4. 📤 Output (What the API Returns)

**What happens after the request is processed?**

### ✅ Success Response

**What the user receives when everything works:**

```json
{
  "success": true,
  "message": "Account created successfully! Check your email for verification.",
  "data": {
    "user_id": "12345",
    "email": "john@example.com",
    "name": "John Doe"
  }
}
```

### ❌ Error Responses

**What happens when something goes wrong:**

| Error Scenario | Message Shown | Why This Happens |
|----------------|---------------|------------------|
| Email already exists | "An account with this email already exists" | User trying to register with existing email |
| Invalid email format | "Please provide a valid email address" | Email doesn't follow proper format |
| Weak password | "Password must be at least 8 characters" | Password doesn't meet security requirements |
| Missing fields | "First name is required" | Required information not provided |

---

## 5. 🔄 Process Flow

**Step-by-step: What happens behind the scenes?**

1. User submits registration form
2. System checks if email already exists
3. System validates password strength
4. System creates new user account
5. System sends verification email
6. System returns success message to user

**Visual representation:**
```
User → Submit Form → Check Email → Validate Data → Create Account → Send Email → Show Success
```

---

## 6. ✅ Acceptance Criteria

**How do we know this is working correctly?**

- [ ] User can successfully register with valid information
- [ ] System prevents duplicate email registrations
- [ ] User receives verification email within 2 minutes
- [ ] Password is securely stored (not visible in database)
- [ ] Error messages are clear and helpful
- [ ] System handles 100+ registrations per minute
- [ ] Works on web, iOS, and Android apps

---

## 7. 🔐 Security & Privacy Requirements

**What safeguards are needed?**

- [ ] Password must be encrypted (not stored as plain text)
- [ ] Email must be verified before account is fully active
- [ ] Protect against automated bot registrations
- [ ] User data must comply with GDPR/data protection laws
- [ ] Rate limiting: Maximum 5 registration attempts per IP per hour

---

## 8. 📧 Notifications & Communications

**What messages does the user receive?**

| Trigger | Channel | Content |
|---------|---------|---------|
| Successful registration | Email | "Welcome! Verify your email to get started" |
| Failed registration | In-app | Error message explaining what went wrong |
| Email verification | Email | "Click here to verify your account" |

---

## 9. 🔗 Dependencies

**What else needs to be ready first?**

- [ ] Email service configured
- [ ] Database tables created
- [ ] SMS service (if phone verification needed)
- [ ] Frontend registration form
- [ ] Terms of service page

---

## 10. 🧪 Testing Scenarios

**What should QA/testers check?**

### Happy Path (Everything Works)
- [ ] Register with valid data → Account created successfully
- [ ] Receive verification email → Can click link and verify

### Error Cases (Things That Can Go Wrong)
- [ ] Try to register with existing email → See error message
- [ ] Submit form with missing fields → See validation errors
- [ ] Use weak password → See password requirements
- [ ] Enter invalid email format → See format error

### Edge Cases (Unusual Situations)
- [ ] Register with very long name (100+ characters)
- [ ] Register with special characters in name
- [ ] Try to register 10 times quickly (rate limiting)

---

## 11. 📊 Success Metrics

**How do we measure if this is working well?**

- Registration success rate: Target 95%+
- Average registration time: Under 30 seconds
- Email delivery rate: 99%+
- User drop-off rate: Less than 10%

---

## 12. 📝 Additional Notes

**Any other important information:**

- This API will be used by web, iOS, and Android apps
- Consider adding social login (Google, Facebook) in future
- Need to support international phone numbers
- Must work in low-bandwidth areas

---

## 13. ❓ Questions/Clarifications

**Things to discuss with the development team:**

1. Should we allow registration with phone number only (no email)?
2. How long should the verification link be valid?
3. What happens to unverified accounts after 7 days?
4. Should we allow special characters in names?

---

## 14. 🚀 Definition of Done

**This story is complete when:**

- [ ] API endpoint is built and tested
- [ ] Frontend can successfully call the API
- [ ] All acceptance criteria are met
- [ ] QA has tested all scenarios
- [ ] Documentation is updated
- [ ] Product manager has approved the feature
- [ ] Feature is deployed to production

---

## 📚 Quick Reference Guide

### For Product Managers:

**When filling this template:**
1. ✍️ Start with sections 1-3 (Story, Goal, Input/Output)
2. 🤔 Think through section 5 (Process Flow) - what should happen?
3. ✅ Be specific in section 6 (Acceptance Criteria)
4. 🧪 Describe real user scenarios in section 10 (Testing)
5. ❓ Ask questions early (section 13)

**You don't need to:**
- Write code or technical specifications
- Know database structures
- Understand programming concepts

**You DO need to:**
- Describe what the user experiences
- Define success and error cases
- Explain the business value
- Think about security and privacy

---

## 💡 Tips for Success

### Writing Clear User Stories
- Focus on the **user's perspective**, not technical implementation
- Use **simple language** - avoid jargon
- Be **specific** about what success looks like
- Include **real examples** whenever possible

### Common Mistakes to Avoid
- ❌ Being too vague: "User can do stuff"
- ✅ Being specific: "User can register with email and receive verification code"
- ❌ Focusing on "how": "Using PostgreSQL database..."
- ✅ Focusing on "what": "System stores user information securely"
- ❌ Missing error cases: Only describing the happy path
- ✅ Including errors: "What if email already exists?"

### Questions to Ask Yourself
1. What is the user trying to accomplish?
2. What information do they need to provide?
3. What do they get back?
4. What can go wrong?
5. How do we know it's working?

---

## 📋 Checklist Before Submitting

- [ ] Story title is clear and descriptive
- [ ] Business goal is explained
- [ ] All input fields are documented
- [ ] Success and error responses are defined
- [ ] Process flow is outlined
- [ ] Acceptance criteria are specific and measurable
- [ ] Security requirements are considered
- [ ] Testing scenarios are comprehensive
- [ ] Dependencies are identified
- [ ] Questions are documented

---

## 🔄 Template Versions

**Version 1.0** - Initial release  
**Last Updated:** February 2026  
**Maintained by:** Product Management Team

---

## 📞 Need Help?

If you're unsure about any section:
1. **Ask the development team** - They can help clarify technical aspects
2. **Review past user stories** - Look at previous examples
3. **Start simple** - Fill in what you know, ask questions about the rest
4. **Iterate** - User stories can be refined during planning meetings

---

## 📖 Example User Story

Here's a complete example to guide you:

### Story: User Email Verification

**Story ID:** API-015  
**Story Title:** Email Verification for New Users  
**Priority:** ☑ Critical  
**Estimated Effort:** ☑ Medium (3-5 days)

**User Story:**  
As a new user who just registered  
I want to verify my email address  
So that I can activate my account and prove I own the email

**Business Goal:**  
Ensure users provide valid email addresses and reduce fake accounts. Email verification is critical for password recovery and important notifications.

**Input:**
| Field Name | Description | Required? | Example |
|------------|-------------|-----------|---------|
| verification_code | 6-digit code from email | Yes | "123456" |
| email | User's email address | Yes | "john@example.com" |

**Success Response:**
```json
{
  "success": true,
  "message": "Email verified successfully! You can now log in.",
  "data": {
    "verified": true,
    "verified_at": "2026-02-09T10:30:00Z"
  }
}
```

**Error Responses:**
- Invalid code: "The verification code is incorrect"
- Expired code: "This verification code has expired. Request a new one"
- Already verified: "This email is already verified"

**Process Flow:**
1. User receives email with 6-digit code
2. User enters code in app
3. System checks if code matches and is not expired
4. System marks email as verified
5. User can now access full features

**Acceptance Criteria:**
- [ ] Code expires after 10 minutes
- [ ] User can request new code if expired
- [ ] Maximum 5 attempts before requiring new code
- [ ] Code is case-insensitive
- [ ] Works across all platforms (web, iOS, Android)

---

## 🎓 Learning Resources

### Recommended Reading
- **User Story Basics:** Understanding "As a...I want...So that" format
- **Acceptance Criteria:** How to write testable requirements
- **API Fundamentals:** Basic understanding of requests and responses

### Internal Resources
- Previous user stories repository
- Product requirements document (PRD) templates
- Development team office hours

---

**Remember:** A good user story focuses on **what** the user needs, not **how** it's built. The development team will figure out the "how"!

---

*This template is designed to bridge communication between product managers and development teams. Feel free to adapt it to your organization's needs.*
