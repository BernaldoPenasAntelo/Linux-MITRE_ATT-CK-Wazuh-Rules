# Linux-MITRE_ATT-CK-Wazuh-Rules

This repository it's a set of configurations and rules for Wazuh in an attemp to create or map the CIS benchmark from the CIS (Center Of Internet Security):

https://www.cisecurity.org/cis-benchmarks/


### USAGE

1.- Install Auditd and use **CIS_recomendations.rules** as the configuration file (/etc/audit/audit.rules)

3.- Move the files in decoders folder to /var/ossec/etc/decoders

4.- Move the **CIS_auditd_recommendation.xml**, **audit_common_rules.xml** and **Auditd_rules.xml** to **/var/ossec/etc/rules**

    a.- CIS_auditd_recommendation.xml - rules related with CIS recommendations.
    b.- audit_common_rules.xml -This file was modified from original wazuh audit rules to adapt to new decoder fields to be ECS (Elastick common schema) compliance.
    c.- Auditd_rules.xml - new rules based on auditd configurations not included in CIS recommendations.
     
5.-  Reconfiguration of /var/ossec/etc/ossce.conf must be done excluding wazuh decoders for audit with parameter:

 ```
  <decoder_exclude>ruleset/decoders/0040-auditd_decoders.xml</decoder_exclude>
```  
  
