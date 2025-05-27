# Assumptions

**Assumptions**
- Carriers will decide which OS will connect to which towers.
- An equipment on Towers will detect the devices, and report App usage. 
- Two types of data is being sent a) real time app usage updates b) from the carriers about tower metadata (like which tower supports which carrier, new tower added etc)
- the decision to allow or deny from the policy service is sent back to tower
- remediation policies will be defined by the enterprises
- policy service connects to elastic search db prior validating against any rules - to make sure the device is valid and has not already received X number of denials in the last X hours.   
