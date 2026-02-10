# Feature Specification: Register New User

**Feature Branch**: `uc-01`  
**Created**: 2026-02-10  
**Status**: Draft  
**Input**: User description: "Feature is UC-01. Use authoritative inputs at lab2-uc-01/UC-01.md and lab2-uc-01/UC-01-AT.md. Copy the flows verbatim into spec.md (only minor grammar/style ok). Extract functional requirements directly from those files. Do not invent features."

## Scope

- **In Scope**: Conference Management System user registration for new users.
- **Out of Scope**: Any features not described in UC-01 and UC-01-AT.

## User Scenarios & Testing *(mandatory)*

### Authoritative User Flows (Verbatim)

**Main Success Scenario**
1. User requests to be registered.
2. System redirects to registration form.
3. User fills and submits the form with email, password, and other required information.
4. System validates email/password fields.
5. System verifies email is unique and valid.
6. System stores user information in database.
7. System redirects user to login screen.

**Extensions**
* **4a**: Email/password fields invalid
  * 4a1: System shows error message indicating invalid fields.
  * 4a2: User corrects fields and resubmits.
* **5a**: Email not unique or not valid
  * 5a1: System displays error message indicating email is already registered or invalid format.
  * 5a2: User enters different email or proceeds to login if already registered.

**Test Case TC-01-01: Main Success Scenario - Successful Registration**
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

**Test Case TC-01-02: Extension 4a - Invalid Email/Password Fields**
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

**Test Case TC-01-03: Extension 5a - Email Already Exists**
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

### User Story 1 - Successful Registration (Priority: P1)

A new user registers with valid information to gain access to the system.

**Why this priority**: This is the core onboarding path and the primary goal of the use case.

**Independent Test**: Can be fully tested by completing a registration with a unique email and valid password, resulting in account creation and redirect to login.

**Acceptance Scenarios**:

1. **Given** a user is not registered and the system is operational, **When** the user submits the registration form with valid email, password, name, and affiliation, **Then** the system validates the inputs, stores the user information, and redirects the user to the login screen with a success message.

---

### User Story 2 - Invalid Email/Password (Priority: P2)

A user is prevented from registering when email or password fields are invalid.

**Why this priority**: Preventing invalid registrations preserves data integrity and enforces security standards.

**Independent Test**: Can be tested by submitting invalid email or weak password and verifying errors are shown and no account is created.

**Acceptance Scenarios**:

1. **Given** a user is not registered, **When** the user submits the registration form with invalid email format or weak password, **Then** the system highlights the invalid fields, shows error messages indicating requirements, and does not complete registration.
2. **Given** a user sees validation errors, **When** the user corrects the fields and resubmits, **Then** the system revalidates the inputs and proceeds with successful registration.

---

### User Story 3 - Duplicate Email (Priority: P3)

A user is prevented from registering with an email that is already registered.

**Why this priority**: Ensures uniqueness of accounts and avoids duplicate registrations.

**Independent Test**: Can be tested by submitting a registration with an email already in the system and verifying the error and that no account is created.

**Acceptance Scenarios**:

1. **Given** an email address is already registered, **When** a user submits the registration form with that email, **Then** the system shows the duplicate email error and keeps the user on the registration form without creating an account.
2. **Given** a duplicate email error, **When** the user enters a different email and submits the form, **Then** the system validates the new email and proceeds with successful registration if all inputs are valid.

---

### Edge Cases

- What happens when the user submits the form with missing required information?
- How does the system handle an email that is not unique or not valid?
- How does the system respond when email/password fields are invalid and the user resubmits?

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: System MUST provide a registration form when a user requests to be registered.
- **FR-002**: System MUST accept email, password, and other required information for registration (including name and affiliation).
- **FR-003**: System MUST validate email and password fields on submission.
- **FR-004**: System MUST verify the email is unique.
- **FR-005**: System MUST validate email format and reject invalid email formats.
- **FR-006**: System MUST validate the password against security standards and reject weak passwords.
- **FR-007**: System MUST store user information in the database upon successful validation.
- **FR-008**: System MUST redirect the user to the login screen after successful registration.
- **FR-009**: System MUST display a success message upon successful registration.
- **FR-010**: System MUST display error messages indicating invalid fields when email/password validation fails.
- **FR-011**: System MUST highlight email and password fields when validation fails.
- **FR-012**: System MUST display an error message when the email is already registered.
- **FR-013**: System MUST keep the user on the registration form when registration fails.
- **FR-014**: System MUST allow the user to correct invalid fields and resubmit.
- **FR-015**: System MUST allow the user to enter a different email when the email is already registered.

### Key Entities *(include if feature involves data)*

- **User Account**: Represents a registered user with unique email, password, name, and affiliation.
- **Registration Submission**: Represents the data entered by a user during registration (email, password, name, affiliation).
- **Email Address**: Represents the unique identifier for a user account and the target for uniqueness validation.

### Dependencies

- Database (store user information).
- Email validation service (validate email uniqueness and format).
- System availability for registration access.

### Assumptions

- None beyond the stated preconditions in UC-01 and UC-01-AT.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: 100% of successful registration attempts with valid inputs create a user account and redirect the user to the login screen with a success message.
- **SC-002**: 100% of registration attempts with invalid email format or weak password are rejected with error messages and highlighted fields, and no account is created.
- **SC-003**: 100% of registration attempts with an already-registered email are rejected with the duplicate email error, and the user remains on the registration form.
- **SC-004**: Users can complete the registration flow by providing email, password, name, and affiliation without additional steps beyond the registration form and submission.
