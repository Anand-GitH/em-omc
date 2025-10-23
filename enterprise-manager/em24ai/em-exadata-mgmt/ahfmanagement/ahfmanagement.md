# Autonomous Health Framework Administration
## Introduction
Autonomous Health Framework (AHF) is Oracle’s diagnostic and health management framework for Exadata and Recovery Appliance systems. It helps administrators monitor system health, run compliance checks, and keep diagnostic tools up to date.

**Key Features:**
- Fleet-wide Monitoring: View AHF installation details, upgrade status, service status, auto-run configuration, and Exachk run history across multiple systems.

- Fleet-wide Management: Upgrade AHF across multiple Exadata hosts on demand or via scheduled auto-upgrades, configure and update AHF upgrade settings across clusters.

- Compliance & Commands: Schedule or run Exachk compliance checks across systems.

- Execute AHF-related commands (ahfctl, tfactl, exachk) on multiple hosts at once.

### Objectives

- Learn how to monitor AHF across the fleet 
- Explore how to manage AHF across the fleet
- Learn how to run Exachk compliance checks across systems

*Estimated Time*: 15 minutes

## Task 1: Execute AHF Command at Fleet Level

1. Log into Enterprise Manager

    ![Enterprise Manager login](images/enterprisemanagerlogin.png " ")

    ![Landing Page](images/landingpage.png " ")

2. Navigate to **Targets > Exadata**.

    ![Enterprise Manager menu icon](images/navigation.png " ")

3. Click on **Actions > Engineered System Autonomous Health Framework Administration**

    ![Enterprise Manager menu icon](images/ahfnavigation.png " ")

    Opens a new tab with AHF Administration page. 

4. Explore **Engineered Systems Tab** in the AHF Administration page. 

    Engineered Systems tab presents an overview that can be used to determine whether AHF is configured on Engineered System targets according to Oracle-recommended standards.

    - **Total Engineered Systems** – Number of monitored systems, with breakdown of management pack enabled/disabled.
    - **AHF Upgrade Status** – Current upgrade status across all systems.
    - **AHF Service Status** – Enablement status of TFA and Exachk services.
    - **AHF Configurations** – Count of systems with auto-upgrade and autorun turned on or off.

    ![AHF Overview](images/ahfoverview.png " ")

    Expand the **DB Machine exa03.rsthybrid.oracle.com** and check the status of AHF, AHF version, Exachk and TFA service status for its nodes.

    ![Expand the view](images/expandview.png " ")

5. Now select a cluster node to **execute AHF Commands**

    **DB Machine exa03.rsthybrid.oracle.com** contains a total of 12 clusters and is a shared environment. Please identify the cluster assigned to you during this hands-on session and use it to execute the AHF command.

    Here we are showing the flow using the cluster **ex03-Cluster-c6**

    Select the cluster **ex03-Cluster-c6** & click on **Actions**
    ![Select the cluster](images/actionsbutton.png " ")

     Enterprise Manager provides the below actions to manage AHF. 
    - Upgrade AHF 
    - Execute AHF Commands
    - Upgrade Configuration
    - Schedule Exachk Autorun
    - Enable AHF Metrics

    ![Check actions available](images/actions.png " ")

6. Click on **Execute AHF Commands**

    ![Execute AHF](images/executeahf.png " ")

7. Select command **ahfctl** and **Other**

    Enterprise Manager allows to run these command types
    - ahfctl : command-line interface to manage AHF
    - exachk : configuration and best-practice validation tool for Engineered Systems
    - tfctl  : automates collection and analysis of diagnostic logs & trace files

    ![Execute AHF](images/ahfctlcommand.png " ")

8. Copy the **ahfctl command** provided and paste it in **Command to Execute** field

    ```
    <copy>
    ahfctl statusahf -tfa -json
    </copy>
    ```

    ![Execute AHF command](images/ahfctlexecute.png " ")

9. Select the named credential **EXA\_HOST\_ROOT** and click **OK**

    ![Open Credential Selector](images/credselector.png " ")
    ![Select the named credential](images/credselected.png " ")
    ![Selected the named credential](images/credselectedok.png " ")


10. Click **Submit** to submit the command execution procedure
    ![Click on Submit](images/submit.png " ")

11. Copy the **Job Id** & Click on **Close** 
    ![Job submitted](images/jobsubmitted.png " ")

## Task 2: Analyze AHF Command Execution Job Status

1. Click on **AHF Management Jobs** tab

    AHF Management Jobs provides a summary of all the Oracle Enterprise Manager AHF management jobs run across all Engineered System hosts.

    - Ring charts shows total Engineered Systems, job Status & job type
    - Table view provides very detailed view of each job that have been run

    ![Job Status](images/ahfjobs.png " ")

2. Filter the jobs based on the job id

    Click on **filter** icon

    ![Job filters](images/jobfilters.png " ")

    Paste the **Job ID** copied from Task 1 in the field of Job ID.

    ![Job ID Filter](images/jobidfilter.png " ")

    Scroll down & click on **Apply**

    ![Apply Job filter](images/filterapply.png " ")

    Shows jobs that matches the Job ID provided.

    ![Show filtered data](images/filteredjobs.png " ")

3. Click on the job that is filtered using the job id to view the job submitted to execute the **AHF Command**

    ![Click on Job Id](images/clickonjobid.png " ")

    A procedure activity opens in a new tab.

4. Click on the **Expand All**  to view all the steps performed in the job execution

    ![Expand all steps](images/expandall.png " ")

5. Select **Summary** to review the job execution summary and status

    In the cluster **ex03-Cluster-c6** selected we have two nodes and the AHF command has been executed on both.
    This feature helps running ahf commands at scale and analyzing its output within Enterprise Manager. 

    ![Job Summary](images/jobsummary.png " ")

6. Select **Run Command** under one of the node to review command output

    ![Command Output](images/commandoutput.png " ")


## Learn More

  - [Autonomous Health Framework Administration](https://docs.oracle.com/en/enterprise-manager/cloud-control/enterprise-manager-cloud-control/24.1/emxad/engineered-system-autonomous-health-framework-administration.html)
  - [Engineered Systems Packs](https://docs.oracle.com/en/enterprise-manager/cloud-control/enterprise-manager-cloud-control/24.1/emxad/preface.html)
  - [Enterprise Manager 24ai Documentation Library](https://docs.oracle.com/en/enterprise-manager/cloud-control/enterprise-manager-cloud-control/24.1/index.html)
  - [Enterprise Manager 24ai Tech Forum Video Playlist](https://www.youtube.com/playlist?list=PLiuPvpy8QsiXvGYMP_N3WA6bddXvUH-Y0)

## Acknowledgements
- **Author** - Anand Prabhu, Principal Member of Technical Staff, Enterprise Manager
- **Contributors** - Swapnil Sinvhal, Bjorn Bolltoft, Mahesh Sharma - Enterprise Manager Team, Michael Reed, Maury Edmonds, Geoffrey Grandstaff - Oracle Solution Center
- **Last Updated By/Date** - Anand Prabhu, Principal Member of Technical Staff, Enterprise Manager September 2025