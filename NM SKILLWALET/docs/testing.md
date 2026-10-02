# Testing Document

## Test Case 1 – High Impact Mandatory Control

**Steps**
1. Open `Incident → Create New`.
2. Set Impact to `High`.
3. Leave Assignment group empty.
4. Observe the form.

**Expected Result**
- Assignment group becomes mandatory.

**Status:** Pass / Fail

---

## Test Case 2 – Urgency Read-only

**Steps**
1. Open an Incident.
2. Set Impact to High.
3. Try to edit Urgency.

**Expected Result**
- Urgency remains visible but cannot be changed manually.

**Status:** Pass / Fail

---

## Test Case 3 – Automatic Urgency

**Steps**
1. Open an Incident.
2. Change Impact to High.

**Expected Result**
- Urgency is automatically set to High.
- Informational message is displayed.

**Status:** Pass / Fail

---

## Test Case 4 – Prevent Save When Assigned To Is Empty

**Steps**
1. Set Impact to High.
2. Leave Assigned To empty.
3. Click Submit.

**Expected Result**
- Incident is not saved.
- Error appears on Assigned To.

**Status:** Pass / Fail

---

## Test Case 5 – Block State List Editing

**Steps**
1. Navigate to `Incident → All`.
2. Try to edit State directly in the list.

**Expected Result**
- Alert message appears.
- State remains unchanged.

**Status:** Pass / Fail

---

## Test Case 6 – Form-Based State Update

**Steps**
1. Open an Incident.
2. Change State from the Incident form.
3. Click Update.

**Expected Result**
- State change is saved successfully.

**Status:** Pass / Fail

---

## Test Case 7 – Reverse Condition

**Steps**
1. Open an Incident where Impact is High.
2. Change Impact to Medium.
3. Check Assignment group and Urgency behavior.

**Expected Result**
- Assignment group is no longer mandatory due to the UI Policy condition becoming false.
- Urgency becomes editable again.

**Status:** Pass / Fail

## Evidence to Capture

Take screenshots of:
1. UI Policy configuration.
2. Assignment group mandatory behavior.
3. Urgency read-only behavior.
4. onChange script configuration.
5. Automatic urgency result.
6. onSubmit script configuration.
7. Validation error.
8. onCellEdit script configuration.
9. List edit blocking alert.
10. Successful form-based State update.
