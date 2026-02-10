## Use Case UC-10: Generate Schedule

### Test Case TC-10-01: Main Success Scenario - Successful Schedule Generation
**Objective**: Verify administrator can generate schedule for accepted papers.

**Preconditions**: 
- Administrator is logged in
- Multiple accepted papers exist in system

**Test Steps**:
1. Administrator navigates to "Generate Schedule"
2. Administrator clicks "Generate Schedule"
3. System retrieves accepted papers
4. System runs Algorithm X
5. System generates HTML schedule

**Expected Result**: 
- Algorithm X executes successfully
- Schedule generated in HTML format
- Schedule displayed to administrator
- Schedule sent to authors of accepted papers

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-10-02: Extension 2a - Algorithm Failure
**Objective**: Verify system handles algorithm failures.

**Preconditions**: 
- Algorithm X is simulated to fail

**Test Steps**:
1. Administrator requests schedule generation
2. Algorithm X encounters error

**Expected Result**: 
- Error is caught
- Error message displayed: "Schedule generation failed"
- Administrator is advised to contact support or retry

**Flow Coverage**: Extension 2a

---

