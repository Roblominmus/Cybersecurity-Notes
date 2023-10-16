
![[Red Team Header.png]]

- INTRODUCTION AND BREIFING
- RULES of ENGAGEMENT (RoE)
- CAMPAIGN PLANNING
- CONOPS
- RESOURCE PLAN
- OPERATIONS PLAN
- MISSION PLAN



This note is about Red Teaming Engagements and how they are run.
Check [[Introduction To Red Teaming]] to better understand this note.
To have a successful engagement (not just red teaming) there must me smooth communication and interaction between the parties involved.

There are fundamentally three was a Red Team Engagement is run, they include;
- **Full Engagement:** Simulate an attacker's full workflow, from initial compromise until final goals have been achieved.
- **Assumed Breach:** Start by assuming the attacker has already gained control over some assets, and try to achieve the goals from there. As an example, the red team could receive access to some user's credentials or even a workstation in the internal network.
- **Table-top Exercise:**  An over the table simulation where scenarios are discussed between the red and blue teams to evaluate how they would theoretically respond to certain threats. Ideal for situations where doing live simulations might be complicated.
--------------
Engagements can be very complex and bureaucratic. The key to a successful engagement is clearly defined client objectives or goals. Client objectives should be discussed between the client and red team to create a mutual understanding between both parties of what is expected and provided. Set objectives are the basis for the rest of the engagement documentation and planning.

Without clear and concrete objectives and expectations, you are preparing for a very unstructured and unplanned campaign. Objectives set the tone for the rest of the engagement.

When assessing a client's objectives and planning the engagement details, you will often need to decide how focused the assessment is.

-----------------------------------------------------
The next keystone to a precise and transparent engagement is a well-defined scope. The scope of an engagement will vary by organization and what their infrastructure and posture look like. A client's scope will typically define what you  cannot do or target; it can also include what you _can_ do or target. While client objectives can be discussed and determined along with the providing team, a scope should only be set by the client. In some cases the red team may discuss a grievance of the scope if it affects an engagement. They should have a clear understanding of their network and the implications of an assessment. The specifics of the scope and the wording will always look different, below is an example of what verbiage may look like within a client's scope.

- No exfiltration of data.
- Production servers are off-limits.
- 10.0.3.8/18 is out of scope.
- 10.0.0.8/20 is in scope.
- System downtime is not permitted under any circumstances.
- Exfiltration of PII is prohibited.

---

When analyzing a client's objectives or scopes from a red team perspective, it is essential to understand the more profound meaning and implications. When analyzing, you should always have a dynamic understanding of how your team would approach the problems/objectives. If needed, you should write your engagement plans or start them from only a bare reading of the client objectives and scope.

For example; Below is an example of the client objectives of a mature organization with a strong security posture.

**Objectives:**

1. Identify system misconfigurations and network weaknesses.
    1. Focus on exterior systems.
2. Determine the effectiveness of endpoint detection and response systems.
3. Evaluate overall security posture and response.
    1. SIEM and detection measures.
    2. Remediation.
    3. Segmentation of DMZ and internal servers.
4. Use of white cards is permitted depending on downtime and length.
5. Evaluate the impact of data exposure and exfiltration.

**Scope:**

1. System downtime is not permitted under any circumstances.
    1. Any form of DDoS or DoS is prohibited.
    2. Use of any harmful malware is prohibited; this includes ransomware and other variations.
2. Exfiltration of PII is prohibited. Use arbitrary exfiltration data.
3. Attacks against systems within 10.0.4.0/22 are permitted.
4. Attacks against systems within 10.0.12.0/22 are prohibited.
5. Bean Enterprises will closely monitor interactions with the DMZ and critical/production systems.
    1. Any interaction with "*.bethechange.xyz" is prohibited.
    2. All interaction with "*.globalenterprises.thm" is permitted.


-----
Rules Of Engagement (RoE)

Rules of Engagement (RoE) are a legally binding outline of the client objectives and scope with further details of engagement expectations between both parties. This is the first "official" document in the engagement planning process and requires proper authorization between the client and the red team. This document often acts as the general contract between the two parties; an external contract or other NDAs (**N**on-**D**isclosure **A**greement) can also be used.

Each RoE structure will be determined by the client and red team and can vary in content length and overall sections. Below is a brief table of standard sections you may see contained in the RoE.

|   |   |
|---|---|
|**Section Name**|**Section Details**|
|Executive Summary|Overarching summary of all contents and authorization within RoE document|
|Purpose|Defines why the RoE document is used|
|References|Any references used throughout the RoE document (HIPAA, ISO, etc.)|
|Scope|Statement of the agreement to restrictions and guidelines|
|Definitions|Definitions of technical terms used throughout the RoE document|
|Rules of Engagement and Support Agreement|Defines obligations of both parties and general technical expectations of engagement conduct|
|Provisions|Define exceptions and additional information from the Rules of Engagement|
|Requirements, Restrictions, and Authority|Define specific expectations of the red team cell|
|Ground Rules|Define limitations of the red team cell's interactions|
|Resolution of Issues/Points of Contact|Contains all essential personnel involved in an engagement|
|Authorization|Statement of authorization for the engagement|
|Approval|Signatures from both parties approving all subsections of the preceding document|
|Appendix|Any further information from preceding subsections|

When analyzing the document, it is important to remember that it is only a summary, and its purpose is to be a legal document. Future and more in-depth planning are required to expand upon the RoE and client objectives.

-------------
Campaign planning uses the information acquired and planned from the client objectives and RoE and applies it to various plans and documents to identify how and what the red team will do.

Each internal red team will have its methodology and documentation for campaign planning. We will be showing one in-depth set of plans that allows for precise communication and detailed documentation. The campaign summary we will be using consists of four different plans varying in-depth and coverage adapted from military operations documents. Each plan can be found in the table below with a brief explanation.

|   |   |   |
|---|---|---|
|**Type of Plan**|**Explanation of Plan**|**Plan Contents**|
|Engagement Plan|An overarching description of technical requirements of the red team.|CONOPS, Resource and Personnel Requirements, Timelines|
|Operations Plan|An expansion of the Engagement Plan. Goes further into specifics of each detail.|Operators, Known Information, Responsibilities, etc.|
|Mission Plan|The exact commands to run and execution time of the engagement.|Commands to run, Time Objectives, Responsible Operator, etc.|
|Remediation Plan|Defines how the engagement will proceed after the campaign is finished.|Report, Remediation consultation, etc.|

Another example of a campaign plan is the [[Red Team Engagement Checklist]].

------
CONOPS (Concept Of Operations)

The [[CONOPS]] is a high-level plan for an engagement, such as a penetration test or security assessment. It tells you what the engagement is for, what it will cover, and how it will be done. It also includes information about the risks involved and how they will be managed.

The [[CONOPS]] is important because it helps to ensure that the engagement is well-planned and executed, and that the results are useful to the client. It is also a valuable tool for communicating the goals and objectives of the engagement to all stakeholders.

Here is an analogy:

Imagine that you are planning a road trip. The CONOPS would be like the itinerary for your trip. It would tell you where you are going, what route you will take, and what you will see along the way. It would also include information about the risks involved, such as traffic conditions and weather forecasts.

The [[CONOPS]] is an important part of planning any engagement, just like an itinerary is an important part of planning a road trip.

---
Resource Plan

The resource plan is a document that details the people, tools, and other resources that are needed for a red team engagement. It is based on the Concept of Operation (CONOPS), but it includes more specific information, such as dates and knowledge required.

The resource plan should be written in a clear and concise manner, and it should be easy for both business and technical stakeholders to understand. It should also be reviewed and approved by all stakeholders prior to the start of the engagement.

Here is an example of a  resource plan outline

**Resource Plan**

- **Engagement Dates**
    - Reconnaissance
    - Initial Compromise
    - Post-Exploitation and Persistence
- **Resource Requirements**
    - Personnel
    - Hardware
    - Cloud
    - Other

The key to writing a good resource plan is to be specific and realistic. You should identify all of the resources that you will need, and you should provide an accurate estimate of the time and cost associated with each resource.

Here are some tips for writing a good resource plan:

- Be specific. Don't just say that you need a "team of experienced red teamers." Instead, list the specific skills and experience that you need.
- Be realistic. Don't underestimate the time and cost of the engagement.
- Be flexible. Things don't always go according to plan, so it's important to be prepared to adjust your resource plan as needed.


- ---
Operations Plan

The [[Operations plan]] is a flexible document(s) that provides specific details of the engagement and actions occurring. The plan expands upon the current CONOPS and should include a majority of specific engagement information; the ROE can also be placed here depending on the depth and structure of the ROE.

The operations plan should follow a similar writing scheme to the resource plan, using bulleted lists and small sub-sections. As with the other red team documents, there is no standard set of operation plan templates or documents; below is an outline of example subsections within the operations plan.

- Header
    - Personnel writing
    - Dates
    - Customer
- Halting/stopping conditions (can be placed in ROE depending on depth)
- Required/assigned personnel
- Specific TTPs and attacks planned
- Communications plan
- Rules of Engagement (optional)

The most notable addition to this document is the communications plan. The communications plan should summarize how the red cell will communicate with other cells and the client overall. Each team will have its preferred method to communicate with clients. Below is a list of possible options a team will choose to communicate.

- [vectr.io](http://vectr.io/)
- Email
- Slack


---
Mission Plan

The mission plan is a cell-specific document that details the exact actions to be completed by operators. The document uses information from previous plans and assigns actions to them.

How the document is written and detailed will depend on the team; as this is an internally used document, the structure and detail have less impact. As with all the documents outlined in this room, presentation can vary; this plan can be as simple as emailing all operators. Below is a list of the minimum detail that cells should include within the plan.

- Objectives
- Operators
- Exploits/Attacks
- Targets (users/machines/objectives)
- Execution plan variations

The two plans can be thought of similarly; the operations plan should be considered from a business and client perspective, and the mission plan should be thought of from an operator and red cell perspective.

---
