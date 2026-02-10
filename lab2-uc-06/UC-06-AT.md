## Use Case UC-06: Assign Referees to Papers

### Test Case TC-06-01: Main Success Scenario - Assign Three Referees
**Objective**: Verify editor can successfully assign three referees to a paper.

**Preconditions**: 
- Editor is logged in
- Paper is submitted and awaiting assignment
- Referees exist in system with <5 assignments each

**Test Steps**:
1. Editor navigates to referee assignment for a paper
2. Editor enters first referee email (has 2 assignments)
3. System assigns and sends invitation
4. Editor enters second referee email (has 3 assignments)
5. System assigns and sends invitation
6. Editor enters third referee email (has 4 assignments)
7. System assigns and sends invitation
8. System confirms three referees assigned

**Expected Result**: 
- Each referee has <5 assignments, so assignment succeeds
- Invitation emails sent to all three referees
- System confirms: "Three referees successfully assigned"
- Paper shows three assigned referees

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-06-02: Extension 2a - Referee Already Has 5+ Assignments
**Objective**: Verify system prevents assigning to overloaded referee.

**Preconditions**: 
- Referee "overloaded@university.edu" has exactly 6 assigned papers

**Test Steps**:
1. Editor attempts to assign paper to "overloaded@university.edu"
2. System checks assignment count

**Expected Result**: 
- System detects referee has 6 assignments (exceeds maximum of 5)
- Warning message displayed: "Referee already has 6 assigned papers (maximum allowed is 5)"
- Assignment is not completed
- Editor must select different referee

**Flow Coverage**: Extension 2a

---

### Test Case TC-06-03: Extension 3a - Referee Rejects Invitation
**Objective**: Verify system handles referee rejection of invitation.

**Preconditions**: 
- Editor has assigned referee and invitation email sent

**Test Steps**:
1. Referee receives invitation email
2. Referee clicks "Reject" link in email
3. System processes rejection

**Expected Result**: 
- Rejection is recorded in database
- Editor receives notification of rejection
- Paper remains available for assignment to another referee

**Flow Coverage**: Extension 3a

---

