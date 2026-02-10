## Use Case UC-05: Save Submission Draft

### Test Case TC-05-01: Main Success Scenario - Save Incomplete Draft
**Objective**: Verify author can save draft at any stage of submission.

**Preconditions**: 
- Author is logged in and on submission page

**Test Steps**:
1. Author enters author information and abstract
2. Author has not yet entered keywords or uploaded file
3. Author clicks "Save Draft" button

**Expected Result**: 
- System validates entered information for format (not completeness)
- Draft is stored in database
- Confirmation message displayed: "Draft saved successfully"
- Author can retrieve draft later

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-05-02: Extension 2a - Format Violation in Draft
**Objective**: Verify system validates format even for drafts.

**Test Steps**:
1. Author enters information with invalid email format
2. Author clicks "Save Draft"

**Expected Result**: 
- System validates format and detects invalid email
- Error message displayed: "Cannot save draft: Invalid email format"
- Draft is not saved
- Author must correct format before saving

**Flow Coverage**: Extension 2a

---

