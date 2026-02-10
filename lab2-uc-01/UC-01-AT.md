## Use Case UC-01: Register New User

### Test Case TC-01-01: Main Success Scenario - Successful Registration
**Objective**: Verify that a new user can successfully register with valid information.

**Preconditions**: 
- User is not registered in the system
- System is operational

**Test Steps**:
1. User navigates to registration page
2. User enters valid email address (e.g., "newuser@university.edu")
3. User enters password that meets security standards (e.g., "SecurePass123!")
4. User enters name and affiliation
5. User submits registration form

**Expected Result**: 
- System validates email is unique
- System validates password meets standards
- User information is stored in database
- User is redirected to login page with success message
- Registration is successful

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-01-02: Extension 4a - Invalid Email/Password Fields
**Objective**: Verify system rejects registration with invalid email format or weak password.

**Preconditions**: 
- User is not registered in the system

**Test Steps**:
1. User navigates to registration page
2. User enters invalid email format (e.g., "invalid.email" without domain)
3. User enters weak password (e.g., "123" - too short, no uppercase, no special char)
4. User submits registration form

**Expected Result**: 
- System validates email format and detects invalidity
- System validates password against security standards and finds it insufficient
- Email and password fields are highlighted
- Error messages displayed indicating requirements
- Registration is not completed

**Flow Coverage**: Extension 4a

---

### Test Case TC-01-03: Extension 5a - Email Already Exists
**Objective**: Verify system rejects registration with duplicate email.

**Preconditions**: 
- Email "existing@university.edu" is already registered

**Test Steps**:
1. User navigates to registration page
2. User enters email "existing@university.edu" (already in database)
3. User enters valid password and other information
4. User submits registration form

**Expected Result**: 
- System detects email already exists
- Error message displayed: "This email address is already registered"
- Registration is not completed
- User remains on registration form

**Flow Coverage**: Extension 5a

---

