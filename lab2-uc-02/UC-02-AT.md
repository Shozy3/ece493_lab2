## Use Case UC-02: User Login

### Test Case TC-02-01: Main Success Scenario - Successful Login
**Objective**: Verify registered user can log in with correct credentials.

**Preconditions**: 
- User "testuser@university.edu" is registered with password "TestPass123!"

**Test Steps**:
1. User navigates to login page
2. User enters username "testuser@university.edu"
3. User enters password "TestPass123!"
4. User clicks login button

**Expected Result**: 
- System validates credentials against database
- User is authenticated
- User is redirected to appropriate home page based on role
- Login is successful

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-02-02: Extension 4a - Invalid Credentials
**Objective**: Verify system rejects login with incorrect credentials.

**Preconditions**: 
- User "testuser@university.edu" is registered with password "CorrectPass123!"

**Test Steps**:
1. User navigates to login page
2. User enters username "testuser@university.edu"
3. User enters incorrect password "WrongPass123"
4. User clicks login button

**Expected Result**: 
- System finds username but password hash doesn't match
- Error message displayed: "Invalid username or password"
- User remains on login page
- No access granted

**Flow Coverage**: Extension 4a

---

