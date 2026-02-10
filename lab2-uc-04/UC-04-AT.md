## Use Case UC-04: Submit Manuscript

### Test Case TC-04-01: Main Success Scenario - Complete Manuscript Submission
**Objective**: Verify author can successfully submit paper with all valid information.

**Preconditions**: 
- Author is logged in
- Valid paper file exists (PDF, <7MB)

**Test Steps**:
1. Author navigates to "Submit Paper"
2. Author enters all author names, affiliations, contact emails
3. Author enters abstract
4. Author enters keywords
5. Author selects main source
6. Author uploads valid PDF file (<7MB)
7. Author clicks submit button

**Expected Result**: 
- All fields validated as complete
- Email addresses validated as valid format
- File format validated as PDF/Word/LaTeX
- File size validated as <7MB
- Paper information and file stored in database
- Success message displayed with submission ID
- Author redirected to home page

**Flow Coverage**: Main Success Scenario

---

### Test Case TC-04-02: Extension 5a - Missing Required Fields
**Objective**: Verify system rejects submission with missing required fields.

**Test Steps**:
1. Author navigates to submission page
2. Author fills some fields but leaves abstract and keywords blank
3. Author uploads valid file
4. Author clicks submit

**Expected Result**: 
- System validates all fields and finds abstract and keywords missing
- Missing fields are highlighted
- Error message displayed: "Please fill in all required fields"
- Submission is not completed

**Flow Coverage**: Extension 5a

---

### Test Case TC-04-03: Extension 5b - Invalid File Format
**Objective**: Verify system rejects files not in PDF/Word/LaTeX format.

**Test Steps**:
1. Author navigates to submission page
2. Author fills all required fields
3. Author uploads file in unsupported format (e.g., .txt, .jpg)
4. Author clicks submit

**Expected Result**: 
- System validates file format and detects unsupported type
- Error message displayed: "Invalid file format. Please upload PDF, Word, or LaTeX"
- Submission is not completed

**Flow Coverage**: Extension 5b

---

### Test Case TC-04-04: Extension 5c - File Size Exceeds Limit
**Objective**: Verify system rejects files larger than 7MB.

**Test Steps**:
1. Author navigates to submission page
2. Author fills all required fields
3. Author uploads file that is 8.5MB (exceeds 7MB limit)
4. Author clicks submit

**Expected Result**: 
- System validates file size and detects it exceeds limit
- Error message displayed: "File size exceeds maximum of 7MB"
- Submission is not completed

**Flow Coverage**: Extension 5c

---

