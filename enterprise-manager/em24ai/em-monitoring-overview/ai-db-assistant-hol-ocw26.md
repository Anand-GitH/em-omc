# Oracle Enterprise Manager 24ai: Powered by GenAI
## Introduction
Oracle Enterprise Manager 24ai is designed to help DBAs monitor and manage Oracle Database environments. In this hands-on lab, try the Oracle AI Database Assistant, Enterprise Manager’s agentic AI chatbot for conversational operations. Configure it to use EM’s LLM or your own LLM, manage user access, and ask natural-language questions about the health of your database fleet. You’ll also use Event Compression to reduce alert fatigue and incident volume, explore Dynamic Runbooks with auto-run data collection before incident triage, and try the new AI-based runbook generator that converts existing runbooks into executable triage steps in Enterprise Manager. 

### Objectives
The objective of this lab is to become familiar with the new modernized Enterprise Manager 24ai platform.

### Prerequisites
This lab assumes you have:

- A Free Tier, Paid or LiveLabs Oracle Cloud account

*Estimated Time*: 70 minutes
 

## Task 1A: Oracle AI Database Assistant - Monitoring 

Oracle AI Database Assistant combines Enterprise Manager telemetry with Large Language Models (LLMs) to provide an intuitive conversational experience for monitoring and operational investigations.
Instead of manually searching through Enterprise Manager pages, administrators can ask questions such as:
    •	Show open incidents
    •	Show job executions in the last 24 hours
    •	Show target availability status
    •	Show critical alerts for production databases
The assistant can return rich widgets, tables, and visualizations directly within the chat experience, helping users quickly understand and act on operational information.
 

1. Log into Enterprise Manager using the credentials **emadmin/welcome1**. 

    ![Enterprise Manager login](ask-em-images/em24-login.png " ")

2. In the upper right corner click on the **Oracle AI Database Assistant** to start it

    ![Enterprise Manager menu icon](ai-db-assistant-images/ai-db-assistant-monitoring/ai-db-assistant.png " ")

3. The Oracle AI Database Assistant should appear with a welcome message and out-of-box questions to get you started.

    ![AI Dataabse Assistant Welcome page](ai-db-assistant-images/ai-db-assistant-monitoring/ai-db-assistant-welcome.png " ")

4. In the chat window Click on question **Show status summary for all my targets**.

    ![AI DB Assistant OOB Question](ai-db-assistant-images/ai-db-assistant-monitoring/ai-db-assistant-oob-question.png " ")

5. In the widget click on **3 dots** and choose **Maximize Widget**.

    ![Target summary maximize widget](ai-db-assistant-images/ai-db-assistant-monitoring/target-summary-maximize.png " ")

6. Click on the **Down** pie slice and review the targets that are down and click on **Close**.

    ![Down pie widget](ai-db-assistant-images/ai-db-assistant-monitoring/down-target-summary-widget.png " ")

7. Click on **minimize** icon on the upper right corner of the widget.

    ![Minimize Widget](ai-db-assistant-images/ai-db-assistant-monitoring/target-summary-minimize.png " ")

8. In the chat window click on **Show list of open incidents**.

    ![Open Incidents](ai-db-assistant-images/ai-db-assistant-monitoring/list-open-incidents.png " ")

9. In the widget click on **3 dots** and choose **Maximize Widget** and review the incidents. 

    ![Maximize Incidents](ai-db-assistant-images/ai-db-assistant-monitoring/maximize-incidents.png " ")

10. For the first incident in the list click the **3 dots** and choose **Acknowledge**. 

    ![Incident Acknowledgement](ai-db-assistant-images/ai-db-assistant-monitoring/incident-ack.png " ")

11. In the confirmation dialog click **Acknowledge**.

    ![Acknowledge](ai-db-assistant-images/ai-db-assistant-monitoring/acknowledgement-incident.png " ")

    After doing the acknowledgment table should show current user **EMADMIN** is the owner of the incident.

    ![Emadmin inci owner](ai-db-assistant-images/ai-db-assistant-monitoring/emadmin-incident-owner.png " ")

12. Click on **+** button on the upper right corner of the widget and choose **Target Property** 

    ![Incident Target Property](ai-db-assistant-images/ai-db-assistant-monitoring/incident-target-property.png " ")

13. Click on Target Property filter and select **Production**. Table of incidents is filtered to show incidents from production targets.

    ![Production Incidents](ai-db-assistant-images/ai-db-assistant-monitoring/production-incident.png " ")

14. Click on the **3 dots** for the first incident and choose **Add Comment**

    ![Add comment](ai-db-assistant-images/ai-db-assistant-monitoring/add-comments-incident.png " ")

15. Add this comment **Will look at this later** and click on **Save**.

    ![Add comment will look later](ai-db-assistant-images/ai-db-assistant-monitoring/will-look-later.png " ")

16. Click on **minimize** icon on the upper right corner of the widget:

    ![Minimize incident list](ai-db-assistant-images/ai-db-assistant-monitoring/minimize-incidents.png " ")

17. Enter the question **Do I have any escalated incidents?** in the chat window and hit `<`enter`>`:

    ![Escalated Incidents](ai-db-assistant-images/ai-db-assistant-monitoring/any-escalated-incidents.png " ")


18. In the widget click on **3 dots** and choose **Maximize Widget**: 

    ![Maximize Escalated Incidents](ai-db-assistant-images/ai-db-assistant-monitoring/max-escalated-incidents.png " ")

19. Review the list of escalated incidents and click on **minimize icon** on the upper right corner of the widget.

    ![Minimize Escalated Incidents](ai-db-assistant-images/ai-db-assistant-monitoring/mini-escalated-incidents.png " ")

20. Scroll up to the top of the chat window and click on **Show list of Oracle Databases with highest average active sessions** prompt:

    ![DB Active Sessions](ai-db-assistant-images/ai-db-assistant-monitoring/db-aas-question.png " ")

21. In the widget click on **3 dots** and choose **Maximize Widget** and review the database performance metrics:

    ![Maximize DB Perf widget](ai-db-assistant-images/ai-db-assistant-monitoring/max-db-performance-widget.png " ")
    
22. Click on **+** button on the upper right corner of the widget and choose **Show label** and **Key Aggregation**:

    ![Add Filters to Widget](ai-db-assistant-images/ai-db-assistant-monitoring/add-filters-db-perf-widget.png " ")

23. In the Metric Column filter change **Average Active Sessions** to **CPU Utilization (%)** and review the CPU Utilization.

    ![CPU Utilization](ai-db-assistant-images/ai-db-assistant-monitoring/cpu-util-widget.png " ")

24. In the widget change the value of these filters:

    Metric Name to **Tablespaces Full**

    ![Tablespace full](ai-db-assistant-images/ai-db-assistant-monitoring/tbspace-full-metric.png " ")

    Metric Column to **Tablespace Space Used (%)**

    ![Tablespace used](ai-db-assistant-images/ai-db-assistant-monitoring/tbspace-used-widget.png " ")

    Key Aggregation to **Max**. The table shows the highest usage of tablespaces for each database.   Review the values shown:

    ![Key Agg Max](ai-db-assistant-images/ai-db-assistant-monitoring/key-agg-max.png " ")

25. In the table click on the highest number in value under the **Value** column. This should open a new browser tab showing the All Metrics page showing the tablespace with that high usage value.

    ![Tablespace full value Click](ai-db-assistant-images/ai-db-assistant-monitoring/tb-full-metric-value-click.png " ")

    ![All Metrics Page](ai-db-assistant-images/ai-db-assistant-monitoring/all-metrics-page.png " ")

26. Go back to the browser tab with AI Assistant. Click on **minimize icon** on the upper right corner of the widget.

    ![Minimize DB Perf Metric](ai-db-assistant-images/ai-db-assistant-monitoring/mini-db-perf-metric.png " ")

## Task 1B: Oracle AI Database Assistant - Database Patching and Compliance

Oracle AI Database Assistant combines Enterprise Manager telemetry with Large Language Models (LLMs) to provide an intuitive conversational experience for monitoring and operational investigations. Instead of manually searching through Enterprise Manager pages, administrators can ask questions related to database patching and compliance to understand the security posture at fleet level. 


1. In the Oracle AI Database Assistant chat window enter **Show configuration drift results by target type** and hit `<`enter`>`:
    ```
    <copy>
    Show configuration drift results by target type
    </copy>
    ```

    Before the patch window, assess whether targets have drifted from their approved configuration baselines. Resolve or document exceptions so patching begins from a known state.
   
    ![Configuration Drift Question](ai-db-assistant-images/ai-db-assistant-dblm/configuration-drift-question.png " ")
    ![Configuration Drift Results](ai-db-assistant-images/ai-db-assistant-dblm/configuration-drift-results.png " ")

2. Enter the prompt **Display the distribution of databases that are subscribed or not subscribed to an image for patching purpose** in the chat window and hit `<`enter`>`: 

    ```
    <copy>
    Display the distribution of databases that are subscribed or not subscribed to an image for patching purpose
    </copy>
    ```

    Next, confirm patching readiness. Databases not subscribed to a patching image need to be enrolled before they can participate in the standardized fleet maintenance patch process.

    ![Database subscriptions to the image question](ai-db-assistant-images/ai-db-assistant-dblm/db-subcription-question.png " ")
    ![Database subscriptions to the image result](ai-db-assistant-images/ai-db-assistant-dblm/db-subcription-result.png " ")

3. Enter the prompt **Display the distribution of database images that are up-to-date or have patch recommendations** in the chat window and hit `<`enter`>`:

    ```
    <copy>
    Display the distribution of database images that are up-to-date or have patch recommendations
    </copy>
    ```

    Review the database images and identify those requiring recommended patches. Update or approve the appropriate image for patching cycle.

    ![Database images question](ai-db-assistant-images/ai-db-assistant-dblm/dbimage-question.png " ")
    ![Database images that are latest](ai-db-assistant-images/ai-db-assistant-dblm/dbimage-result.png " ")

4. Enter the prompt **Display the distribution of databases that are compliant** in the chat window and hit `<`enter`>`

    ```
    <copy>
    Display the distribution of databases that are compliant
    </copy>
    ```

    After patching completes, evaluate the database fleet patch compliance.
    ![Databases with latest patches](ai-db-assistant-images/ai-db-assistant-dblm/db-patchcomplianceqns.png " ")
    ![Databases with latest patches](ai-db-assistant-images/ai-db-assistant-dblm/db-patchcomplianceresp.png " ")

5. Enter the prompt **How many critical compliance violations exist?** in the chat window and hit `<`enter`>`:

    ```
    <copy>
    How many critical compliance violations exist?
    </copy>
    ```

    Investigate any remaining violations to identify databases and security controls requiring remediation or approved exceptions.

     ![Compliance violations question](ai-db-assistant-images/ai-db-assistant-dblm/db-compliance-question.png " ")
     ![Compliance violations results](ai-db-assistant-images/ai-db-assistant-dblm/db-compliance-results.png " ")

## Learn More

  - [Oracle Enterprise Manager](https://www.oracle.com/enterprise-manager/)
  - [Enterprise Manager 24ai Documentation Library](https://docs.oracle.com/en/enterprise-manager/cloud-control/enterprise-manager-cloud-control/24.1/index.html)
  - [Enterprise Manager 24ai Tech Forum Video Playlist](https://www.youtube.com/playlist?list=PLiuPvpy8QsiXvGYMP_N3WA6bddXvUH-Y0)

## Acknowledgements
- **Author** - Sumesh Balakrishnan, Oracle Enterprise Manager Product Management
- **Contributing Author** - Ana McCollum, Anand Prabhu, Oracle Enterprise Manager Product Management