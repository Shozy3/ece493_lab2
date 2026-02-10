## Use Case UC-03: Change Password

### Test Case TC-03-01: Main Success Scenario - Successful Password Change
**Objective**: Verify user can change password with all valid inputs.

**Preconditions**: 
- User is logged in
- Current password is "OldPass123!"

**Test Steps**:
1. User navigates to account settings
2. User clicks "Change Password"
3. User enters current password "OldPass123!"
4. User enters new password "NewPass456!"
5. User confirms new password "NewPass456!"
6. User submits form

**Expected Result**: 
- System validates current password matches
- System validates new password meets standards
- Password is updated in database
- Success message displayed
- User can log in with new password

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-03-02: Extension 3a - Wrong Current Password
**Objective**: Verify system rejects password change with incorrect current password.

**Preconditions**: 
- User is logged in
- Actual current password is "CorrectPass123!"

**Test Steps**:
1. User navigates to change password page
2. User enters incorrect current password "WrongPass123"
3. User enters new password "NewPass456!"
4. User confirms new password
5. User submits form

**Expected Result**: 
- System validates current password and finds mismatch
- Error message displayed: "Current password is incorrect"
- Password is not changed
- User can retry with correct current password

**Flow Coverage**: Extension 3a

---

### Test Case TC-03-03: Extension 4a - Weak New Password
**Objective**: Verify system enforces password standards for new password.

**Test Steps**:
1. User navigates to change password page
2. User enters correct current password
3. User enters weak new password "123" (doesn't meet standards)
4. User confirms new password
5. User submits form

**Expected Result**: 
- System validates new password against standards and finds it insufficient
- Error message displayed listing password requirements
- Password is not changed

**Flow Coverage**: Extension 4a

---

