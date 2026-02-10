## Use Case UC-08: Submit Review Form

### Test Case TC-08-01: Main Success Scenario - Submit Complete Review
**Objective**: Verify referee can submit complete review form.

**Preconditions**: 
- Referee is logged in
- Paper is assigned to referee

**Test Steps**:
1. Referee selects "Review" for assigned paper
2. System displays paper and review form
3. Referee reads the paper
4. Referee fills all required fields in review form
5. Referee submits review

**Expected Result**: 
- All required fields validated as complete
- Review saved in database
- System checks if all 3 reviews complete (if not, waits)
- Confirmation message displayed to referee
- If all complete, editor is notified

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-08-02: Extension 4a - Missing Required Fields
**Objective**: Verify system rejects incomplete review forms.

**Test Steps**:
1. Referee fills most of review form but leaves recommendation blank
2. Referee attempts to submit

**Expected Result**: 
- System validates all fields and finds recommendation missing
- Recommendation field is highlighted
- Error message displayed: "Please complete all required fields"
- Review is not submitted

**Flow Coverage**: Extension 4a

---

