# Test Cases — JIL Validation

## TC01 — Syntax Error (Failure)
- **Input:** Error_QA.txt with `update_job` on non-existent job
- **Tool:** JILIN validator
- **Result:** VALIDATION FAILURE email received
- **Error:** "This job does NOT exist within QA5. 
  You cannot attempt to update."
- **Fix:** Change `update_job` to `insert_job`

## TC02 — Successful Validation
- **DEV:** DEV_DA.txt → Instance DA5 → SUCCESSFUL
- **UAT:** UAT_QA.txt → Instance QA5 → SUCCESSFUL  
- **PROD:** PROD_PA.txt → Instance PA5 → SUCCESSFUL
- **Result:** All JILs deployed through full pipeline