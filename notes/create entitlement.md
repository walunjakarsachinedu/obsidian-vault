### Entitlement
Entitlements are permissions or rights that grant users access to specific resources such as applications, databases, and files..

#### Line item
Line items typically refer to the specific access entitlements that are assigned to individual users or groups.

### Step to create entitlements (steps)
1. create entitlement 
2. go to snow approve all entitlements  
	1. approve all entitlement which match entitlement name or id
3. Run CAG action performer in Sailpoint  
	1. go to setup > task
	2. search task: "42 8082 Action Performer pz"
	3. (make use case field empty) 
	4. press "save & execute"
4. check for created entitlement in Sailpoint Applications
	1. Applications > Application definition 
	2. In application filter enter "unix platform permission set"
	3. select accounts tab
	4. enter name of your entitlement
	6. it will show status of entitlement

### entitlement states 
	1. Sumitted For Approval
	2. request approved pending submission
	3. request approved forward for approval
	4. request closed (Active)

### For Running CAG in Sailpoint:
1. Sailpoint
2. Setup
3. Tasks
4. Name of CAG (428082 CAG Action Performer Pz)
5. detect CAG
6. save & execute (remember Usecase field must be blank)
7. done



	 
 
 
 
 
 