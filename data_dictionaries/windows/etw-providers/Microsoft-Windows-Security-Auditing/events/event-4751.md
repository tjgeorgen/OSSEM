# Event ID 4751: A member was added to a security-disabled global group

## Description
This event generates every time a new member was added to a security-disabled (distribution) global group. This event generates only on domain controllers. For every added member you will get separate 4751 event. You will typically see "4750: A security-disabled global group was changed." event without any changes in it prior to 4751 event.

## Data Dictionary
|Standard Name|Field Name|Type|Description|Sample Value|
|---|---|---|---|---|
|target_user_name|MemberName|UnicodeString|distinguished name of account that was added to the group. For example: "CN=Auditor,CN=Users,DC=contoso,DC=local". For some well-known security principals, such as LOCAL SERVICE or ANONYMOUS LOGON, the value of this field is "-".|`CN=Auditor,CN=Users,DC=contoso,DC=local`|
|target_user_sig|MemberSid|SID|SID of account that was added to the group. Event Viewer automatically tries to resolve SIDs and show the group name.|`S-1-5-21-3457937927-2839227994-823803824-2104`|
|group_name|TargetUserName|UnicodeString|the name of the group to which new member was added. For example: ServiceDesk|`ServiceDeskSecond`|
|group_domain|TargetDomainName|UnicodeString|domain name of the group to which new member was added.|`CONTOSO`|
|group_sid|TargetSid|SID|SID of the group to which new member was added. Event Viewer automatically tries to resolve SIDs and show the group name.|`S-1-5-21-3457937927-2839227994-823803824-6119`|
|user_sid|SubjectUserSid|SID|SID of account that requested the "add member to the group" operation. Event Viewer automatically tries to resolve SIDs and show the account name.|`S-1-5-21-3457937927-2839227994-823803824-1104`|
|user_name|SubjectUserName|UnicodeString|the name of the account that requested the "add member to the group" operation.|`dadmin`|
|user_domain|SubjectDomainName|UnicodeString|subject's domain name.|`CONTOSO`|
|user_logon_id|SubjectLogonId|HexInt64|hexadecimal value that can help you correlate this event with recent events that might contain the same Logon ID, for example, "4624: An account was successfully logged on."|`0x3007b`|
|user_privilege_list|PrivilegeList|UnicodeString|the list of user privileges which were used during the operation, for example, SeBackupPrivilege. This parameter might not be captured in the event, and in that case appears as "-".|`-`|

## References
* [MS Source](https://github.com/MicrosoftDocs/windows-itpro-docs/blob/master/windows/security/threat-protection/auditing/event-4751.md)
* [MS Security Auditing Category - Account Management](https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/advanced-security-audit-policy-settings#account-management)
* [MS Security Auditing Sub-category - Audit Distribution Group Management](https://github.com/MicrosoftDocs/windows-itpro-docs/tree/master/windows/security/threat-protection/auditing/audit-distribution-group-management.md)

## Tags
* etw_level_Informational
* etw_task_task_0
* Account Management
* Audit Distribution Group Management