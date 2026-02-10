## Use Case UC-07: Accept or Reject Review Invitation

### Test Case TC-07-01: Main Success Scenario - Referee Accepts Invitation
**Objective**: Verify referee can accept valid invitation.

**Preconditions**: 
- Referee receives valid invitation email
- Paper has <3 assigned reviewers

**Test Steps**:
1. Referee clicks "Accept" link in invitation email
2. System verifies invitation is valid
3. System checks paper has <3 reviewers (currently 1)
4. System adds paper to referee's account
5. System notifies editor

**Expected Result**: 
- Invitation is validated
- Paper is added to referee's account
- Editor receives notification
- Referee is redirected to account showing assigned paper

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-07-02: Extension 2a - Referee Rejects Invitation
**Objective**: Verify referee can reject review invitation.

**Preconditions**: 
- Referee receives valid invitation email
- Referee is registered in system

**Test Steps**:
1. Referee clicks "Reject" link in invitation email
2. System verifies invitation is valid
3. System records rejection
4. System notifies editor

**Expected Result**: 
- Invitation is validated
- Rejection is recorded in database
- Editor receives notification of rejection
- Referee is redirected to confirmation page
- Paper remains available for assignment to another referee

**Flow Coverage**: Extension 2a

---

### Test Case TC-07-03: Extension 4a - Paper Already Has Three Reviewers
**Objective**: Verify system prevents accepting when paper is fully assigned.

**Preconditions**: 
- Paper already has three accepted reviewers

**Test Steps**:
1. Fourth referee receives invitation
2. Referee clicks accept link
3. System checks current reviewer count

**Expected Result**: 
- System detects paper already has 3 reviewers
- Message displayed: "This paper already has three assigned reviewers"
- Paper is not added to referee's account
- Editor is notified

**Flow Coverage**: Extension 4a

---

