## Use Case UC-11: Edit and Update Schedule

### Test Case TC-11-01: Main Success Scenario - Successful Schedule Edit
**Objective**: Verify editor can edit and update schedule.

**Preconditions**: 
- Editor is logged in
- Schedule exists in system

**Test Steps**:
1. Editor navigates to "Edit Schedule"
2. Editor views current schedule
3. Editor modifies time slot for a paper
4. Editor saves changes

**Expected Result**: 
- Schedule changes validated (no conflicts)
- Schedule updated in database (replaces old version)
- Updated schedule sent to authors via email
- Schedule updated on CMS webpage
- Confirmation displayed to editor

**Flow Coverage**: Main Success Scenario

---

