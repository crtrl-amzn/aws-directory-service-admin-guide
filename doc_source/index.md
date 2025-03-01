# AWS Directory Service Administration Guide

-----
*****Copyright &copy; Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in 
     connection with any product or service that is not Amazon's, 
     in any manner that is likely to cause confusion among customers, 
     or in any manner that disparages or discredits Amazon. All other 
     trademarks not owned by Amazon are the property of their respective
     owners, who may or may not be affiliated with, connected to, or 
     sponsored by Amazon.

-----
## Contents
+ [What is AWS Directory Service?](what_is.md)
+ [Setting up AWS Directory Service](setting_up.md)
   + [Sign up for an AWS account](setting_up_aws_account.md)
   + [Create an IAM user](setting_up_create_iam_user.md)
+ [AWS Managed Microsoft AD](directory_microsoft_ad.md)
   + [Getting started with AWS Managed Microsoft AD](ms_ad_getting_started.md)
      + [AWS Managed Microsoft AD prerequisites](ms_ad_getting_started_prereqs.md)
      + [Create your AWS Managed Microsoft AD directory](ms_ad_getting_started_create_directory.md)
      + [What gets created](ms_ad_getting_started_what_gets_created.md)
      + [Admin account](ms_ad_getting_started_admin_account.md)
   + [Key concepts for AWS Managed Microsoft AD](ms_ad_key_concepts.md)
      + [Active Directory schema](ms_ad_key_concepts_schema.md)
      + [Patching and maintenance for AWS Managed Microsoft AD](ms_ad_key_concepts_maintenance.md)
      + [Group Managed Service Accounts](ms_ad_key_concepts_gmsa.md)
      + [Kerberos constrained delegation](ms_ad_key_concepts_kerberos.md)
   + [Use cases for AWS Managed Microsoft AD](ms_ad_use_cases.md)
      + [Use Case 1: Sign in to AWS applications and services with AD credentials](usecase1.md)
      + [Use Case 2: Manage Amazon EC2 instances](usecase2.md)
      + [Use Case 3: Provide directory services to your AD-aware workloads](usecase3.md)
      + [Use Case 4: SSO to Office 365 and other cloud applications](usecase4.md)
      + [Use Case 5: Extend your on-premises AD to the AWS Cloud](usecase5.md)
      + [Use Case 6: Share your directory to seamlessly join Amazon EC2 instances to a domain across AWS accounts](usecase6.md)
   + [How to administer AWS Managed Microsoft AD](ms_ad_how_to.md)
      + [Secure your AWS Managed Microsoft AD directory](ms_ad_security.md)
         + [Manage password policies for AWS Managed Microsoft AD](ms_ad_password_policies.md)
            + [Supported policy settings](supportedpolicysettings.md)
            + [Delegate who can manage your password policies](delegatepasswordpolicies.md)
            + [Assign password policies to your users](assignpasswordpolicies.md)
         + [Enable multi-factor authentication for AWS Managed Microsoft AD](ms_ad_mfa.md)
         + [Enable secure LDAP (LDAPS)](ms_ad_ldap.md)
            + [Enable server-side LDAPS using AWS Managed Microsoft AD](ms_ad_ldap_server_side.md)
            + [Enable client-side LDAPS using AWS Managed Microsoft AD](ms_ad_ldap_client_side.md)
         + [Manage compliance for AWS Managed Microsoft AD](ms_ad_compliance.md)
         + [Enhance your AWS Managed Microsoft AD network security configuration](ms_ad_network_security.md)
      + [Monitor your AWS Managed Microsoft AD](ms_ad_monitor.md)
         + [Understanding your directory status](ms_ad_directory_status.md)
         + [Configure directory status notifications](ms_ad_enable_notifications.md)
         + [Review your AWS Managed Microsoft AD directory logs](ms_ad_directory_logs.md)
         + [Enable log forwarding](ms_ad_enable_log_forwarding.md)
      + [Multi-Region replication](ms_ad_configure_multi_region_replication.md)
         + [Global vs Regional features](multi-region-global-region-features.md)
         + [Primary vs additional Regions](multi-region-global-primary-additional.md)
         + [How multi-Region replication works](multi-region-how-it-works.md)
         + [Add a replicated Region](multi-region-add-region.md)
         + [Delete a replicated Region](multi-region-delete-region.md)
      + [Share your directory](ms_ad_directory_sharing.md)
         + [Key directory sharing concepts](ms_ad_directory_sharing_key_concepts.md)
         + [Tutorial: Sharing your AWS Managed Microsoft AD directory for seamless EC2 domain-join](ms_ad_tutorial_directory_sharing.md)
            + [Step 1: Set up your networking environment](step1_setup_networking.md)
            + [Step 2: Share your directory](step2_share_directory.md)
            + [Step 3: Accept shared directory invite (optional)](step3_accept_invite.md)
            + [Step 4: Test seamlessly joining an EC2 instance for Windows Server to a domain](step4_test_ec2_access.md)
         + [Unshare your directory](ms_ad_directory_sharing_unshare.md)
      + [Join an EC2 instance to your AWS Managed Microsoft AD directory](ms_ad_join_instance.md)
         + [Seamlessly join a Windows EC2 instance](launching_instance.md)
         + [Manually join a Windows instance](join_windows_instance.md)
         + [Seamlessly join a Linux EC2 instance to your AWS Managed Microsoft AD directory](seamlessly_join_linux_instance.md)
         + [Manually join a Linux instance](join_linux_instance.md)
         + [Manually join a Linux instance using Winbind](join_linux_instance_winbind.md)
         + [Delegate directory join privileges for AWS Managed Microsoft AD](directory_join_privileges.md)
         + [Create a DHCP options set](dhcp_options_set.md)
      + [Manage users and groups in AWS Managed Microsoft AD](ms_ad_manage_users_groups.md)
         + [Installing the Active Directory administration tools](ms_ad_install_ad_tools.md)
         + [Create a user](ms_ad_manage_users_groups_create_user.md)
         + [Reset a user password](ms_ad_manage_users_groups_reset_password.md)
         + [Create a group](ms_ad_manage_users_groups_create_group.md)
         + [Add a user to a group](ms_ad_manage_users_groups_add_user_to_group.md)
      + [Connect to your existing AD infrastructure](ms_ad_connect_existing_infrastructure.md)
         + [Creating a trust relationship](ms_ad_setup_trust.md)
         + [Adding IP routes when using public IP addresses](ms_ad_adding_routes.md)
         + [Tutorial: Create a trust relationship between your AWS Managed Microsoft AD and your self-managed Active Directory domain](ms_ad_tutorial_setup_trust.md)
            + [Prerequisites](before_you_start.md)
            + [Step 1: Prepare your self-managed AD Domain](ms_ad_tutorial_setup_trust_prepare_onprem.md)
            + [Step 2: Prepare your AWS Managed Microsoft AD](ms_ad_tutorial_setup_trust_prepare_mad.md)
            + [Step 3: Create the trust relationship](ms_ad_tutorial_setup_trust_create.md)
         + [Tutorial: Create a trust relationship between two AWS Managed Microsoft AD domains](ms_ad_tutorial_setup_trust_between_2_managed_ad_domains.md)
            + [Step 1: Prepare your AWS Managed Microsoft AD](ms_ad_tutorial_setup_trust_prepare_mad_between_2_managed_ad_domains.md)
            + [Step 2: Create the trust relationship with another AWS Managed Microsoft AD domain](ms_ad_tutorial_setup_trust_create_between_2_managed_ad_domains.md)
      + [Extend your schema](ms_ad_schema_extensions.md)
         + [When to extend your AWS Managed Microsoft AD schema](ms_ad_schema_when_to_extend.md)
         + [Tutorial: Extending your AWS Managed Microsoft AD schema](ms_ad_tutorial_extend_schema.md)
            + [Step 1: Create your LDIF file](create.md)
            + [Step 2: Import your LDIF file](import.md)
            + [Step 3: Verify if the schema extension was successful](verify.md)
            + [(Optional) Add a value to the new attribute](addvalue.md)
            + [Related resources](additional.md)
      + [Maintain your AWS Managed Microsoft AD directory](ms_ad_maintain.md)
         + [Add alternate UPN suffixes](ms_ad_upn_suffixes.md)
         + [Delete your directory](ms_ad_delete.md)
         + [Rename your directory's site name](ms_ad_rename_site.md)
         + [Snapshot or restore your directory](ms_ad_snapshots.md)
         + [View directory information](ms_ad_view_directory_info.md)
      + [Grant users and groups access to AWS resources](ms_ad_manage_roles.md)
         + [Creating a new role](create_role.md)
         + [Editing the trust relationship for an existing role](edit_trust.md)
         + [Assigning users or groups to an existing role](assign_role.md)
         + [Viewing users and groups assigned to a role](view_role_details.md)
         + [Removing a user or group from a role](remove_role_users.md)
         + [Using AWS managed policies with AWS Directory Service](ms_ad_managed_policies.md)
      + [Enable access to AWS applications and services](ms_ad_manage_apps_services.md)
         + [Creating an access URL](ms_ad_create_access_url.md)
         + [Single sign-on](ms_ad_single_sign_on.md)
      + [Enable access to the AWS Management Console with AD credentials](ms_ad_management_console_access.md)
      + [Deploy additional domain controllers](ms_ad_deploy_additional_dcs.md)
      + [Migrate users from Active Directory to AWS Managed Microsoft AD](ms_ad_migrate_users.md)
   + [Best practices for AWS Managed Microsoft AD](ms_ad_best_practices.md)
   + [AWS Managed Microsoft AD quotas](ms_ad_limits.md)
   + [Application compatibility policy for AWS Managed Microsoft AD](ms_ad_app_compatibility.md)
   + [AWS Managed Microsoft AD test lab tutorials](ms_ad_tutorial_test_lab.md)
      + [Tutorial: Setting up your base AWS Managed Microsoft AD test lab in AWS](ms_ad_tutorial_test_lab_base.md)
         + [Prerequisites](microsoftadbaseprereq.md)
         + [Step 1: Set up your AWS environment for AWS Managed Microsoft AD](microsoftadbasestep1.md)
         + [Step 2: Create your AWS Managed Microsoft AD directory in AWS](microsoftadbasestep2.md)
         + [Step 3: Deploy an EC2 instance to manage your AWS Managed Microsoft AD](microsoftadbasestep3.md)
         + [Step 4: Verify that the base test lab is operational](microsoftadbasestep4.md)
      + [Tutorial: Creating a trust from AWS Managed Microsoft AD to a self-managed Active Directory installation on Amazon EC2](ms_ad_tutorial_test_lab_trust.md)
         + [Step 1: Set up your environment for trusts](microsoftadtruststep1.md)
         + [Step 2: Create the trusts](microsoftadtruststep2.md)
         + [Step 3: Verify the trust](microsoftadtruststep3.md)
   + [Troubleshooting AWS Managed Microsoft AD](ms_ad_troubleshooting.md)
      + [DNS troubleshooting](ms_ad_troubleshooting_dns.md)
      + [Linux domain join errors](ms_ad_troubleshooting_join_linux.md)
      + [Active Directory low available storage space](ms_ad_troubleshooting_low_storage_space.md)
      + [Schema extension errors](ms_ad_troubleshooting_schema.md)
      + [Trust creation status reasons](ms_ad_troubleshooting_trusts.md)
+ [Active Directory Connector](directory_ad_connector.md)
   + [Getting started with AD Connector](ad_connector_getting_started.md)
      + [AD Connector prerequisites](prereq_connector.md)
      + [Create an AD Connector](create_ad_connector.md)
      + [What gets created](create_details_ad_connector.md)
   + [How to administer AD Connector](ad_connector_how_to.md)
      + [Secure your AD Connector directory](ad_connector_security.md)
         + [Update your AD Connector service account credentials in AWS Directory Service](ad_connector_update_creds.md)
         + [Enable multi-factor authentication for AD Connector](ad_connector_mfa.md)
         + [Enable client-side LDAPS using AD Connector](ad_connector_ldap_client_side.md)
            + [Prerequisites](prereqs-ldap-client-side.md)
            + [Enable client-side LDAPS](enable-ldap-client-side.md)
            + [Manage client-side LDAPS](manage-ldap-client-side.md)
         + [Enable mTLS authentication in AD Connector for use with smart cards](ad_connector_clientauth.md)
            + [Prerequisites](prereqs-clientauth.md)
            + [Enable smart card authentication](enable-clientauth.md)
            + [Manage smart card authentication settings](manage-clientauth.md)
      + [Monitor your AD Connector directory](ad_connector_monitor.md)
         + [Understanding your directory status](ad_connector_directory_status.md)
         + [Configure directory status notifications](ad_connector_enable_notifications.md)
      + [Join an EC2 instance to your AD Connector directory](ad_connector_join_instance.md)
         + [Seamlessly join a Windows EC2 instance](ad_connector_launching_instance.md)
         + [Seamlessly join a Linux EC2 instance to your AD Connector directory](ad_connector_seamlessly_join_linux_instance.md)
      + [Maintain your AD Connector directory](ad_connector_maintain.md)
         + [Delete your directory](ad_connector_delete.md)
         + [View directory information](ad_connector_view_directory_info.md)
      + [Update the DNS address for your AD Connector](ad_connector_update_dns.md)
   + [Best practices for AD Connector](ad_connector_best_practices.md)
   + [AD Connector quotas](ad_connector_limits.md)
   + [Application compatibility policy for AD Connector](ad_connector_app_compatibility.md)
   + [Troubleshooting AD Connector](ad_connector_troubleshooting.md)
+ [Simple Active Directory](directory_simple_ad.md)
   + [Getting started with Simple AD](simple_ad_getting_started.md)
      + [Simple AD prerequisites](prereq_simple.md)
      + [Create a Simple AD directory](how_to_create_simple_ad.md)
      + [What gets created](create_details_simple.md)
      + [Configure DNS](simple_ad_dns.md)
   + [How to administer Simple AD](simple_ad_how_to.md)
      + [Manage users and groups in Simple AD](simple_ad_manage_users_groups.md)
         + [Installing the Active Directory administration tools](simple_ad_install_ad_tools.md)
         + [Create a user](simple_ad_manage_users_groups_create_user.md)
         + [Reset a user password](simple_ad_manage_users_groups_reset_password.md)
         + [Create a group](simple_ad_manage_users_groups_create_group.md)
         + [Add a user to a group](simple_ad_manage_users_groups_add_user_to_group.md)
      + [Monitor your Simple AD directory](simple_ad_monitor.md)
         + [Understanding your directory status](simple_ad_directory_status.md)
         + [Configure directory status notifications](simple_ad_enable_notifications.md)
      + [Join an EC2 instance to your Simple AD directory](simple_ad_join_instance.md)
         + [Seamlessly join a Windows EC2 instance](simple_ad_launching_instance.md)
         + [Manually join a Windows instance](simple_ad_join_windows_instance.md)
         + [Seamlessly join a Linux EC2 instance to your Simple AD directory](simple_ad_seamlessly_join_linux_instance.md)
         + [Manually join a Linux instance](simple_ad_join_linux_instance.md)
         + [Delegate directory join privileges for Simple AD](simple_ad_directory_join_privileges.md)
         + [Create a DHCP options set](simple_ad_dhcp_options_set.md)
      + [Maintain your Simple AD directory](simple_ad_maintain.md)
         + [Delete your directory](simple_ad_delete.md)
         + [Snapshot or restore your directory](simple_ad_snapshots.md)
         + [View directory information](simple_ad_view_directory_info.md)
      + [Enable access to AWS applications and services](simple_ad_manage_apps_services.md)
         + [Creating an access URL](simple_ad_create_access_url.md)
         + [Single sign-on](simple_ad_single_sign_on.md)
      + [Enable access to the AWS Management Console with AD credentials](simple_ad_management_console_access.md)
   + [Tutorial: Create a Simple AD directory](simple_ad_tutorial_create.md)
      + [Prerequisites](gsg_prereqs.md)
      + [Step 1: Create and configure your VPC](gsg_create_vpc.md)
      + [Step 2: Create your Simple AD directory](gsg_create_directory.md)
   + [Best practices for Simple AD](simple_ad_best_practices.md)
   + [Simple AD quotas](simple_ad_limits.md)
   + [Application compatibility policy for Simple AD](simple_ad_app_compatibility.md)
   + [Troubleshooting Simple AD](simple_ad_troubleshooting.md)
      + [Simple AD directory status reasons](simple_ad_troubleshooting_reasons.md)
+ [Security in AWS Directory Service](security.md)
   + [Identity and access management for AWS Directory Service](iam_auth_access.md)
      + [Overview of managing access permissions to your AWS Directory Service resources](IAM_Auth_Access_Overview.md)
      + [Using identity-based policies (IAM policies) for AWS Directory Service](IAM_Auth_Access_IdentityBased.md)
      + [AWS Directory Service API permissions: Actions, resources, and conditions reference](UsingWithDS_IAM_ResourcePermissions.md)
   + [Logging and monitoring in AWS Directory Service](incident-response.md)
   + [Compliance validation for AWS Directory Service](ds-compliance.md)
   + [Resilience in AWS Directory Service](disaster-recovery-resiliency.md)
   + [Infrastructure security in AWS Directory Service](infrastructure-security.md)
   + [Cross-service confused deputy prevention](cross-service-confused-deputy-prevention.md)
+ [Service level agreement for AWS Directory Service](sla.md)
+ [Region availability for AWS Directory Service](regions.md)
+ [Browser compatibility](compatibility.md)
+ [Document history](document_history.md)