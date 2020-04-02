Retrieve the members in a LDAP security group

usage:
check_ldap_group WARNING CRITICAL HOST PORT LDAP_USER_CN LDAP_PASS GROUP_CN GROUP_NAME MAXRANGE

Where:
[WARNING] = Warning Value (MEMBERS > WARNING)
[CRITICAL] = Critical Value (MEMBERS > CRITICAL)
[HOST] = LDAP IP
[PORT] = LDAP PORT
[LDAP_USER_CN] = LDAP validate user's complete DistingishedName
[LDAP_PASS] = LDAP validate user's password
[GROUP_CN] = LDAP complete DistingishedName group to check 
[GROUP_NAME] = LDAP Name group to check 
[MAXRANGE] = 1000 for Windows 2000 LDAP servers, 1500 for Windows 2003 LDAP servers or 5000 for Windows 2008> LDAP servers

For example the command:
./check_ldap_group 100 200 1.2.3.4 389 "CN=LDAPUSER,OU=USER,DC=DOMAIN,DC=LOCAL" LDAPUSER_PASS "CN=LDAP_GROUP,OU=GROUPS,DC=DOMAIN,DC=LOCAL" "LDAP_GROUP" 1500
Will check group LDAP_GROUP on 1.2.3.4:389 LDAP SERVER, validating with LDAPUSER/LDAPUSER_PASS with a warning=100 and critical=200 values

requires ldap-utils
install with: sudo apt install ldap-utils

