## Use Case UC-12: Pay for Conference Attendance

### Test Case TC-12-01: Main Success Scenario - Successful Registration and Payment
**Objective**: Verify user can register and pay for conference attendance.

**Preconditions**: 
- User is logged in as authorized user
- Payment gateway is operational

**Test Steps**:
1. User navigates to "Register for Conference"
2. System displays price list (based on user role)
3. User proceeds to payment
4. User enters valid credit card information
5. User confirms payment

**Expected Result**: 
- Payment processed successfully through gateway
- Payment confirmation stored in database
- Ticket generated
- Ticket and confirmation email sent to user
- Confirmation displayed on screen

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-12-02: Extension 3a - Payment Declined
**Objective**: Verify system handles payment declines.

**Preconditions**: 
- Payment gateway is configured to decline test payment

**Test Steps**:
1. User enters credit card information
2. User confirms payment
3. Payment gateway processes and declines

**Expected Result**: 
- Payment decline is received from gateway
- Error message displayed: "Payment was declined"
- Registration is not completed
- User can retry with different payment method

**Flow Coverage**: Extension 3a

---

### Test Case TC-12-03: Extension 4a - Database Error After Payment
**Objective**: Verify system handles database errors after successful payment.

**Preconditions**: 
- Payment is processed successfully
- Database storage is simulated to fail

**Test Steps**:
1. User completes successful payment
2. System attempts to store registration (fails)

**Expected Result**: 
- Payment succeeded (already processed)
- Error message displayed indicating registration storage failure
- User advised to contact support with payment reference
- Support can manually verify and complete registration

**Flow Coverage**: Extension 4a

---

## Test Coverage Summary

All test cases are designed to achieve **all-flows test coverage** for each use case:
- Main Success Scenario: Covered
- All Extensions: Covered
- Alternative outcomes: Covered where applicable

Each use case has test cases that verify:
1. Successful completion of main flow
2. Handling of all error conditions (extensions)
3. Edge cases and boundary conditions
4. System reliability and error recovery
