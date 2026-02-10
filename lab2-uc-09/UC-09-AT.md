## Use Case UC-09: Make Final Decision

### Test Case TC-09-01: Main Success Scenario - Accept Paper
**Objective**: Verify editor can make and save acceptance decision.

**Preconditions**: 
- Editor is logged in
- Paper has three completed reviews

**Test Steps**:
1. Editor views papers ready for decision
2. Editor selects paper with three reviews
3. Editor reviews paper and all three review forms
4. Editor selects "Accept" decision
5. Editor confirms decision

**Expected Result**: 
- Decision is saved in database
- Paper status updated to "Accepted"
- Author receives email notification
- Confirmation displayed to editor

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-09-02: Main Success Scenario - Reject Paper
**Objective**: Verify editor can make rejection decision.

**Test Steps**:
1. Editor reviews paper with three negative reviews
2. Editor selects "Reject" decision
3. Editor confirms decision

**Expected Result**: 
- Decision saved as "Rejected"
- Paper status updated
- Author receives rejection email with feedback
- Confirmation displayed

**Flow Coverage**: Main Success Scenario (alternative outcome)

---

