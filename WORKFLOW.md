# Legal Practice Workflow & Procedures

This document outlines standard operating procedures for using this repository to manage your legal practice.

## 📋 Table of Contents

1. [Matter Intake Process](#matter-intake-process)
2. [Document Management](#document-management)
3. [Email Workflow](#email-workflow)
4. [Records Management](#records-management)
5. [Deadline Tracking](#deadline-tracking)
6. [Checklists](#checklists)

---

## Matter Intake Process

### Step 1: Create New Matter Issue
1. Go to **Issues** tab
2. Click **"New issue"** → Select **"New Matter Intake"** template
3. Fill in required fields:
   - Client Name
   - Matter Type (e.g., Divorce, Contract Review, Litigation)
   - Practice Area
   - Date Opened
   - Important Deadlines
   - Initial Notes

4. Assign to yourself and add labels (e.g., `urgent`, `corporate`, `family-law`)
5. Submit issue

### Step 2: Create Matter Folder
1. Navigate to `/documents/client-matters/`
2. Create new folder: `[YYYYMMDD]-[CLIENT-ID]-[MATTER-TYPE]`
   - Example: `20260515-SMITH-001-DIVORCE`
3. Add subfolders as needed:
   - `correspondence/` - All letters and emails
   - `pleadings/` - Court documents and motions
   - `evidence/` - Exhibits and supporting docs
   - `billing/` - Time entries for this matter

### Step 3: Document Initial Consultation
1. Create file: `00-INTAKE-FORM.md`
2. Include:
   - Client information
   - Matter summary
   - Initial legal issues identified
   - Proposed timeline
   - Fee arrangement
   - Contact preferences

### Step 4: Set Initial Deadlines
1. Add all known deadlines to `/records/calendars/`
2. Link calendar entries to the Matter Issue
3. Enable notifications in GitHub for this issue

---

## Document Management

### Version Control Best Practices

**For All Documents:**
1. Save with descriptive name: `[YYYYMMDD]-[DOCUMENT-TYPE]-[VERSION].docx`
2. Example: `20260515-COMPLAINT-v3.docx`, `20260515-SETTLEMENT-AGREEMENT-FINAL.docx`
3. Add commit message explaining changes: "Revised complaint per client feedback on damages section"

### Document Review Workflow

**For Important Documents:**
1. Create a Pull Request with the document
2. Add comment: "Please review and approve [DOCUMENT NAME]"
3. Assign to reviewer
4. Reviewers comment on changes needed
5. Make revisions and push updates
6. Once approved, merge PR and move to appropriate folder

### Template Usage

1. Navigate to `/documents/templates/`
2. Copy template to your matter folder
3. Rename: `[YYYYMMDD]-[CLIENT-SPECIFIC-NAME].docx`
4. Customize with matter-specific details
5. Commit with message: "Created [document name] from template"

### Archiving Completed Matters

1. When matter is closed, move entire folder to `/documents/archives/`
2. Rename with completion date: `CLOSED-20260515-[ORIGINAL-NAME]`
3. Close the GitHub Issue with status update
4. Document outcome and lessons learned

---

## Email Workflow

### Incoming Email Log

**File:** `/email-workflow/incoming/EMAIL-LOG.md`

For each important incoming email:
```markdown
| Date | From | Subject | Matter | Action Required | Deadline | Status |
|------|------|---------|--------|-----------------|----------|--------|
| 2026-05-15 | opposing-counsel@example.com | Settlement Offer | SMITH-001 | Review + Respond | 2026-05-22 | In Progress |
```

### Email Response Workflow

1. Review email and identify matter
2. Check `/email-workflow/templates/` for relevant response template
3. Create response using template as starting point
4. Save draft: `/email-workflow/correspondence-tracking/[MATTER-ID]/[DATE]-DRAFT-[SUBJECT].md`
5. Optional: Create PR for review before sending
6. Send from your email client
7. Move finalized response to `/email-workflow/correspondence-tracking/[MATTER-ID]/[DATE]-SENT-[SUBJECT].md`
8. Commit: "Sent [email description] to [recipient]"

### Email Storage

**Organize by matter:**
```
/email-workflow/correspondence-tracking/
  /SMITH-001-DIVORCE/
    /2026-05-10-FROM-OPPOSING-COUNSEL-SETTLEMENT-OFFER.md
    /2026-05-12-TO-CLIENT-SETTLEMENT-REVIEW.md
    /2026-05-15-FROM-COURT-HEARING-NOTICE.md
```

### Email Template Examples

Create templates for:
- Initial client consultation follow-up
- Status update letters
- Opposing counsel communication
- Court filing confirmations
- Settlement proposals
- Cease and desist letters
- Document request responses

---

## Records Management

### Deadline Calendar

**File:** `/records/calendars/MASTER-CALENDAR-2026.md`

Track all deadlines:
```markdown
| Date | Matter | Description | Type | Status | Notes |
|------|--------|-------------|------|--------|-------|
| 2026-05-22 | SMITH-001 | Motion deadline | Court | Pending | 7 days remaining |
| 2026-06-15 | ABC-CORP-002 | Settlement deadline | Negotiation | Active | Client to decide |
| 2026-07-10 | JONES-003 | Statute of Limitations | Case | Monitor | 12 months from incident |
```

### Billing & Time Tracking

**File Format:** `/records/billing/[YEAR]/[MATTER-ID]-TIME-LOG.md`

```markdown
# Time Log - SMITH-001 Divorce

| Date | Description | Hours | Rate | Amount | Notes |
|------|-------------|-------|------|--------|-------|
| 2026-05-10 | Initial consultation | 1.5 | $300 | $450 | Discovery topics discussed |
| 2026-05-12 | Prepare response | 2.0 | $300 | $600 | Opposing counsel motion |
| 2026-05-15 | Court filing | 0.5 | $300 | $150 | Motion submitted |
```

### Docket Management

**File:** `/records/dockets/[MATTER-ID]-DOCKET.md`

Track all court activities:
```markdown
# Court Docket - SMITH-001

| Date | Event | Description | Document Filed | Status |
|------|-------|-------------|-----------------|--------|
| 2026-05-10 | Case Filed | Divorce Complaint | COMPLAINT.pdf | ✓ |
| 2026-05-15 | Motion Filed | Motion for Temporary Support | MOTION-SUPPORT.pdf | ✓ |
| 2026-05-20 | Hearing Scheduled | Motion hearing | - | Pending |
```

### Matter Index

**File:** `/records/index/ACTIVE-MATTERS.md`

Keep current list of all active matters:
```markdown
# Active Matters - 2026

| Matter ID | Client | Type | Opened | Attorney | Status |
|-----------|--------|------|--------|----------|--------|
| SMITH-001 | Jane Smith | Divorce | 2026-05-10 | You | Active |
| ABC-CORP-002 | ABC Inc. | Contract | 2026-04-15 | You | Under Review |
| JONES-003 | John Jones | Personal Injury | 2026-03-20 | You | Investigation |
```

---

## Deadline Tracking

### Using GitHub Issues for Deadlines

Each Matter Issue should include:
- Important case deadlines
- Response deadlines
- Filing deadlines
- Internal milestones

### Notification Strategy

1. **GitHub Notifications:** Enable for matters you're actively handling
2. **Calendar Reminders:** Use your personal calendar for critical deadlines
3. **Weekly Review:** Every Monday, check `/records/calendars/` for upcoming deadlines
4. **Two-Week Warning:** Create task 14 days before major deadline

---

## Checklists

### ✅ New Matter Checklist

- [ ] Matter Issue created in GitHub
- [ ] Matter folder created in `/documents/client-matters/`
- [ ] Intake form completed and filed
- [ ] All known deadlines added to calendar
- [ ] Initial email/correspondence saved
- [ ] Fee arrangement documented
- [ ] Matter added to `/records/index/ACTIVE-MATTERS.md`
- [ ] Client contact info verified
- [ ] Conflicts check completed

### ✅ Motion/Brief Preparation Checklist

- [ ] Research completed and documented
- [ ] Outline drafted
- [ ] Template selected from `/documents/templates/`
- [ ] First draft completed
- [ ] Peer review completed (if applicable)
- [ ] Client review and approval
- [ ] Edits incorporated
- [ ] Format checked (court rules compliant)
- [ ] Citations verified
- [ ] Filed with court
- [ ] Confirmation saved to `/records/dockets/`

### ✅ Email Response Checklist

- [ ] Understand question/request fully
- [ ] Check matter issue for context
- [ ] Select appropriate template
- [ ] Customize to specific situation
- [ ] Review for accuracy and tone
- [ ] Check spelling and grammar
- [ ] Get peer review if complex/important
- [ ] Send with appropriate follow-up date
- [ ] Save sent copy to correspondence folder
- [ ] Update email log with response

### ✅ Matter Closing Checklist

- [ ] Final status documented in Issue
- [ ] All files saved to matter folder
- [ ] Billing finalized and recorded
- [ ] Client notified of closure
- [ ] Matter folder moved to archives
- [ ] GitHub Issue closed
- [ ] Matter removed from active matters index
- [ ] Any lessons learned documented
- [ ] Client contact info archived
- [ ] Follow-up date set if applicable

---

## Best Practices

### File Naming
- Use consistent naming: `[YYYYMMDD]-[TYPE]-[DESCRIPTION]`
- Avoid special characters (use dashes instead of spaces)
- Include version numbers for drafts: `v1`, `v2`, `FINAL`

### Commit Messages
- Be descriptive: "Added discovery request responses per client"
- Include matter ID: "SMITH-001: Completed financial affidavit"
- Explain reasoning: "Removed settlement language per client instructions"

### Organization
- One folder per matter (not per document type)
- Archive completed matters regularly
- Delete draft/temporary files after finalization
- Keep templates current and relevant

### Security
- Don't commit sensitive personal data
- Use redacted versions for examples
- Review privacy settings on repository
- Consider making repository Private

---

**Last Updated:** 2026-05-15
