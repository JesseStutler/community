---
name: Governance Documentation Review for CNCF Graduation
about: Review and improve Volcano governance documentation against CNCF Graduation requirements
title: "[Governance] Governance Documentation Review - CNCF Graduation Preparation"
labels: governance, cncf-graduation
---

# Volcano Governance Documentation Review for CNCF Graduation

This issue tracks Volcano's compliance with the **Governance and Maintainers** requirements from the [CNCF Graduation Application Template](https://github.com/cncf/toc/blob/main/.github/ISSUE_TEMPLATE/template-graduation-application.md).

Each requirement is marked as:
- ✅ **Met** - Already satisfied with evidence
- ⚠️ **Partially Met** - Needs improvement or clarification
- ❌ **Not Met** - Requires new documentation or changes

---

## Governance and Maintainers - Required Criteria

### ✅ 1. Clear and discoverable project governance documentation

**CNCF Requirement:**
> Clear and discoverable project governance documentation.

**Status:** ✅ **Met**

**Evidence:**
- File: [`GOVERNANCE.md`](https://github.com/volcano-sh/community/blob/master/GOVERNANCE.md). Content includes: Principles, Maintainer expectations, Decision-making process, Changes in Maintainership, CNCF relationship, Code of Conduct reference, etc.

**No action needed.**

---

### ⚠️ 2. Governance is up to date with actual project activities

**CNCF Requirement:**
> Governance is up to date with actual project activities, including any meetings, elections, leadership, or approval processes.

**Status:** ⚠️ **Partially Met** - Needs documentation updates

**What's Missing:**

#### 2.1 Document Meeting Practices
- **Current State:** `GOVERNANCE.md` doesn't document the project's meeting practices
- **Reality:** No regular scheduled meetings; maintainers coordinate asynchronously as needed

**Action:**
- [ ] Add a brief section to `GOVERNANCE.md`:

```markdown
## Meetings

Volcano does not hold regular scheduled meetings. Maintainers coordinate asynchronously through GitHub issues and pull requests to accommodate different time zones and work schedules. Ad-hoc meetings can be proposed by any maintainer via GitHub issue when synchronous discussion is beneficial. Meeting notes are documented in the relevant issue.
```

#### 2.2 Document Leadership Selection and Approval Process
- **Current State:** 
  - `community-membership.md` lists requirements but lacks operational details
  - Owner role doesn't exist in practice and should be removed
  - Maintainer promotion process not accurately documented
  
- **Reality:**
  - **Member/Reviewer/Approver:** Submit via `.github/ISSUE_TEMPLATE/membership.yaml`, sponsors vote in issue
  - **Maintainer:** Nominated by existing Maintainer → other Maintainers vote → majority (>50%) required
  - **Owner:** This role does not exist and should be removed from documentation

**Actions for `community-membership.md`:**

- [ ] **Task A:** Update the roles summary table:
  - Remove the Owner row entirely from the table
  - Add a note after the table:
    ```markdown
    **Note:** For detailed role promotion process, please see [Role Promotion Process](#role-promotion-process).
    ```

- [ ] **Task B:** Update Maintainer section - Replace the Requirements subsection with:

```markdown
### Requirements
- Approver for at least 2 months
- Nominated by an existing Maintainer via GitHub issue
- Demonstrates good technical judgement in feature design/development
- Approved by majority (>50%) of active Maintainers through voting
```

- [ ] **Task C:** Remove Owner section completely

- [ ] **Task D:** Add new "Role Promotion Process" section to `community-membership.md`:
  
  ```markdown
  ## Role Promotion Process
  
  ### For Member, Reviewer, and Approver
  
  1. **Application:** Submit Organization Membership Request via 
     [membership.yaml issue template](https://github.com/volcano-sh/community/issues/new?template=membership.yaml)
  
  2. **Sponsor Requirements:**
     - Member: 2 Approvers must sponsor
     - Reviewer: 2 Maintainers must sponsor
     - Approver: 2 Maintainers must sponsor
  
  3. **Voting:** Sponsors express support by commenting in the issue 
     (e.g., "+1, thanks for your contribution", "LGTM", or similar endorsement)
  
  4. **Approval:** Once required number of valid sponsor votes received, 
     membership is approved
  
  5. **Onboarding:** 
     - Add to appropriate OWNERS files（For reviewer/approver)
     - Grant GitHub organization membership (For member)
  
  ### For Maintainer
  
  1. **Nomination:** Any existing Maintainer creates a GitHub issue proposing the 
     candidate with nomination rationale (qualifications, contribution history, etc.)
  
  2. **Voting:** 
     All active Maintainers vote in the nomination issue. Vote formats could be: +1 (approve), 0 (abstain), -1 (object with reasoning)
  
  3. **Approval Criteria:**
     Majority (>50%) of active Maintainers must vote +1
  
  4. **Public Notice Period:**
     Once voting passes, open for community feedback for 1 week. Community members can raise concerns during this period
  
  5. **Onboarding:**
     Add to MAINTAINERS.md via PR
  
  ### Notes
  - All promotion discussions and votes happen in public GitHub issues for transparency
  - Candidates should not vote for themselves
  - Sponsors/voters from diverse organizations are preferred
  ```

**Files to Update:** `GOVERNANCE.md`, `community-membership.md`

---

### ⚠️ 3. Governance clearly documents vendor-neutrality

**CNCF Requirement:**
> Governance clearly documents vendor-neutrality of project direction.

**Status:** ⚠️ **Partially Met** - Needs explicit statement

**Current State:** 
- GOVERNANCE.md mentions Merit principle (technical merit over affiliation)
- But doesn't explicitly use "vendor-neutrality" terminology
- No dedicated section explaining neutrality mechanisms

**Why This Matters:**
Vendor neutrality is a core CNCF value that ensures no single organization controls the project direction. See [CNCF Vendor Neutrality Guidelines](https://contribute.cncf.io/projects/best-practices/community/vendor-neutrality/).

**Action:**
- [ ] Add explicit vendor neutrality section to `GOVERNANCE.md`:

```markdown
## Vendor Neutrality

Volcano is an independent open source project committed to vendor neutrality as defined by the CNCF. Project direction is determined by the community and maintainers based on technical merit, not by any single vendor or organization.

**Key Principles:**
- **No single organization controls the project**: No vendor has unilateral decision-making authority over project direction, features, or governance
- **Multi-organization maintainer base**: Maintainers represent multiple organizations (current affiliations listed in MAINTAINERS.md)
- **Merit-based decisions**: Technical decisions are based on merit, alignment with project goals, and design principles, not organizational affiliation
- **Equal contributor rights**: All contributors have equal rights regardless of employer; contributions are evaluated on technical merit
- **Open path to leadership**: Any contributor can become a maintainer through demonstrated contribution and community trust, as documented in community-membership.md
- **Consensus-based governance**: Major decisions require consensus among maintainers from different organizations
- **Transparent processes**: All governance processes, decisions, and discussions happen publicly on GitHub

For more details on CNCF's vendor neutrality principles, see the [CNCF Vendor Neutrality Guidelines](https://contribute.cncf.io/projects/best-practices/community/vendor-neutrality/).
```

**File to Update:** `GOVERNANCE.md`

---

### ⚠️ 4. Document decision-making for key areas

**CNCF Requirement:**
> Document how the project makes decisions on leadership roles, contribution acceptance, requests to the CNCF, and changes to governance or project goals.

**Status:** ⚠️ **Partially Met** - Needs completion

**Current State:**
- ✅ Leadership roles: Documented in `community-membership.md`
- ✅ Contribution acceptance: Documented in GOVERNANCE.md (consensus-based)
- ❌ Requests to CNCF: Not documented
- ❌ Governance changes: Not documented

**Action:**
- [ ] Add decision-making processes to `GOVERNANCE.md`:

```markdown
## Decision Making

### Requests to CNCF

For formal requests to the CNCF (such as graduation applications, budget requests, or trademark usage), any maintainer can propose the request via a GitHub issue. Other maintainers review and discuss the proposal. The request proceeds when maintainers reach consensus, and the submission is coordinated by one of the maintainers.

### Modifying Governance

Changes to governance documents (GOVERNANCE.md, community-membership.md, etc.) are proposed via Pull Request with clear rationale and follow the standard PR review process. Changes are merged when approved by maintainers.
```

**File to Update:** `GOVERNANCE.md`

---

### ⚠️ 5. Document sub-teams (Security Response Committee, etc.)

**CNCF Requirement:**
> Document how role, function-based members, or sub-teams are assigned, onboarded, and removed for specific teams (example: Security Response Committee).

**Status:** 🔄 **In Progress** - Being addressed in [PR #97](https://github.com/volcano-sh/community/pull/97)

**Current State:**
- ⚠️ Current `PST.md` is too simple and incomplete
- 🔄 PR #97 is adding comprehensive security-team structure (similar to [Karmada](https://github.com/karmada-io/community/tree/main/security-team) and [KubeEdge](https://github.com/kubeedge/community/blob/master/team-security))
- ❌ Missing detailed documentation on how members are assigned, onboarded, and removed

**Action:**
- [ ] Complete PR #97 to include:
  - Team member assignment process
  - Onboarding process 
  - Offboarding/removal process
  - Clear responsibilities
  - Response procedures

**Files to Update:** Complete the security-team structure in PR #97

---

### ✅ 6. Document complete maintainer lifecycle

**CNCF Requirement:**
> Document a complete maintainer lifecycle process (including roles, onboarding, offboarding, and emeritus status).

**Status:** ✅ **Met**

**Evidence:**
- File: [`community-membership.md`](https://github.com/volcano-sh/community/blob/master/community-membership.md)
- Roles documented: Member, Reviewer, Approver, Maintainer, Owner
- Onboarding requirements: Sponsorship, contribution requirements, time requirements
- Offboarding: Referenced in GOVERNANCE.md ("Changes in Maintainership")
- Emeritus status: Documented in MAINTAINERS.md

**No action needed** 

---

### ⚠️ 7. Demonstrate maintainer lifecycle usage

**CNCF Requirement:**
> Demonstrate usage of the maintainer lifecycle with outcomes, either through the addition or replacement of maintainers as project events have required.

**What This Means:**
CNCF wants to see evidence that your documented maintainer lifecycle (onboarding/offboarding processes in community-membership.md) actually works in practice, not just on paper. They want to verify that maintainers do join and leave the project according to your documented processes.

**Status:** ⚠️ **Partially Met** - Needs simple timeline

**Current State:**
- ✅ Emeritus list exists (proves lifecycle works - people have moved to Emeritus status)
- ✅ Current active maintainer list shows the lifecycle is functioning
- ❌ No timeline showing when maintainers joined or moved to Emeritus

**Action:**
- [ ] Add "Maintainer Changes" section to `MAINTAINERS.md`:

```markdown
## Maintainer Changes

This section tracks maintainer lifecycle events to demonstrate the governance process in action.

### Recent Changes
- 2024: [Name] joined as Maintainer
- [Year]: [Name] moved to Emeritus status

_Note: Future maintainer changes will be documented here when they occur._
```

**Note:** Volcano doesn't "remove" maintainers - they move to Emeritus status, which is the healthy way to handle lifecycle transitions.

**File to Update:** `MAINTAINERS.md`

---

### ⚠️ 8. Document complete maintainer information

**CNCF Requirement:**
> Document complete list of current maintainers, including names, contact information, domain of responsibility, and affiliation.

**Status:** ⚠️ **Partially Met** - Missing contact info; domain clarification needed

**Current State:**
- ✅ Names listed
- ✅ GitHub IDs listed
- ✅ Affiliations listed
- ❌ Contact information (email) missing
- ⚠️ Domain of responsibility: Volcano maintainers are generalists who work across all areas

**Actions:**

- [ ] **Add Contact Information:** Update `MAINTAINERS.md` table to include email column:

```markdown
| Maintainer    | GitHub ID     | Email                      | Affiliation |
| ------------- | ------------- | -------------------------- | ----------- |
| Klaus Ma      | k82cn         | klaus@nvidia.com           | NVIDIA      |
| Kevin Wang    | kevin-wangzefeng | wangzefeng@huawei.com   | Huawei      |
```

- [ ] **Document Domain of Responsibility:** Since Volcano maintainers don't have specific domain assignments, add a clarifying note to `MAINTAINERS.md`:

```markdown
**Domain of Responsibility:** Volcano maintainers do not have designated responsibility for specific technical domains. All maintainers can participate in reviewing and maintaining all aspects of the project.
```

**File to Update:** `MAINTAINERS.md`

---

### ✅ 9. Appropriate number of active maintainers

**CNCF Requirement:**
> A number of active maintainers which is appropriate to the size and scope of the project.

**Status:** ✅ **Met**

**Evidence:**
- Current active maintainers: 7 (listed in MAINTAINERS.md)
- For a CNCF Incubating project focused on Kubernetes batch scheduling, this is appropriate
- Multiple maintainers can handle the review load and ensure continuity

**No action needed.**

---

### ✅ 10. Maintainers from multiple organizations

**CNCF Requirement:**
> Project maintainers from at least 2 organizations that demonstrates survivability.

**Status:** ✅ **Met**

**Evidence:**
- NVIDIA: 2 maintainers (Klaus Ma, William-wang)
- Huawei: 3 maintainers (Kevin Wang, Zhonghu Xu, Xavier Chang)
- Hjmicro: 1 maintainer (Thor-wl)
- Baidu: 1 maintainer (Liang Tang)

**Total: 4 organizations represented**, demonstrating strong survivability.

**No action needed.**

---

### ⚠️ 11. Code/doc ownership matches governance roles

**CNCF Requirement:**
> Code and Doc ownership in Github and elsewhere matches documented governance roles.

**What This Means:**
"Ownership" here refers to who has actual control/permissions over code and documentation:
- **OWNERS files**: Who can approve/LGTM pull requests
- **GitHub permissions**: Who has write/maintain/admin access to repositories
- **Branch protections**: Who can merge to main branch
- **Other access controls**: Documentation site editing, CI/CD access, etc.

These actual permissions should match the roles documented in MAINTAINERS.md and GOVERNANCE.md. In other words: the people who **can** make decisions should be the same people that your governance docs **say** can make decisions.

**Status:** ⚠️ **Partially Met** - Needs Emeritus permission policy documentation

**What CNCF Actually Checks:**
- **Maintainers** (governance-level): Do permissions match MAINTAINERS.md?
- **Reviewers/Approvers** (contributor-level): Is there a documented process? (community-membership.md ✅ + membership issues as records ✅)

**Volcano's Current Status:**
- ✅ Active maintainers have appropriate permissions
- ⚠️ Emeritus maintainer (`animeshsingh`) retains permissions in OWNERS files - this is intentional but not documented
- ✅ Reviewer/Approver governance: Process documented in community-membership.md, records exist in membership issues (no centralized list needed)

**Actions:**

- [ ] **Action 1:** Document Emeritus permission policy in `MAINTAINERS.md`:

```markdown
**Permissions:** Emeritus Maintainers retain their code review and approval permissions in OWNERS files. This allows them to continue participating at their discretion and return to active status easily. They are not expected to fulfill regular maintainer duties.
```

- [ ] **Action 2:** Add role tracking clarification to `community-membership.md` (at the end of the document):

```markdown
## Role Assignment Records

### Maintainers
Current active Maintainers are listed in [MAINTAINERS.md](https://github.com/volcano-sh/community/blob/master/MAINTAINERS.md) in the main community repository. The "Maintainer Changes" section in that file tracks when maintainers join or move to Emeritus status.

### Members, Reviewers, and Approvers
Volcano does not maintain a centralized registry of all Members, Reviewers, and Approvers. However, each role assignment has a verifiable approval record:
- **Process documentation**: This file (community-membership.md) defines the requirements and processes
- **Approval records**: Each Member/Reviewer/Approver request is submitted and approved through GitHub issues using the membership.yaml template, with sponsor votes documented in the issue
- **Permission tracking**: Repository-level permissions are reflected in OWNERS files within each repository

This distributed approach allows different repositories to have different sets of reviewers and approvers based on active contributors in those areas, while maintaining accountability through documented approval processes.
```

**Files to Update:** `MAINTAINERS.md`, `community-membership.md`

---

### ✅ 12. CNCF Code of Conduct adoption

**CNCF Requirement:**
> Document adoption and adherence to the CNCF Code of Conduct or the project's CoC which is based off the CNCF CoC and not in conflict with it.

**Status:** 🔄 **Being Improved** - Already met, enhancement in progress via [PR #106](https://github.com/volcano-sh/community/pull/106)

**Current State:**
- ✅ Code of Conduct exists and is based on Contributor Covenant (aligned with CNCF)
- ✅ GOVERNANCE.md references alignment with CNCF CoC
- 🔄 PR #106 is enhancing this by:
  - Directly referencing CNCF CoC instead of maintaining a copy
  - Adding violation reporting email address (cncf-volcano-maintainers@lists.cncf.io)
  - Renaming to `CODE_OF_CONDUCT.md` (following community convention)

**Action:** Once PR #106 is merged, this requirement will be fully satisfied with best practices. No additional action needed beyond merging that PR.

---

### ⚠️ 13. CoC cross-linked from governance documents

**CNCF Requirement:**
> CNCF Code of Conduct is cross-linked from other governance documents.

**Status:** ⚠️ **Needs Update** - Links need to be updated after PR #106 merge

**Current State:**
- ✅ GOVERNANCE.md references CoC in multiple places
- ⚠️ PR #106 renames `code_of_conduct.md` → `CODE_OF_CONDUCT.md`, which will break existing links

**Action:**
- [ ] After PR #106 is merged, update all CoC references:
  - `GOVERNANCE.md`: Update links from `code_of_conduct.md` to `CODE_OF_CONDUCT.md`
  - `community-membership.md`: Update CoC link if needed
  - Any other files that link to the CoC file

**Files to Update:** `GOVERNANCE.md`, `community-membership.md`, and any other files linking to CoC

---

### ⚠️ 14 & 15. Subproject documentation

**CNCF Requirements:**
> 14. All subprojects, if any, are listed.
> 15. If the project has subprojects: subproject leadership, contribution, maturity status documented, including add/remove process.

**Status:** ⚠️ **Needs Consolidation** - Merge subproject-creation.md into comprehensive SUBPROJECTS.md

**Current State:**
- ✅ `subproject-creation.md` documents creation process
- ✅ GOVERNANCE.md describes acceptance criteria
- ❌ No centralized document listing current repositories
- ❌ No removal/archival process documented
- ⚠️ Leadership: Volcano maintainers collectively manage all repositories (no dedicated subproject maintainers needed)

**Action:**
- [ ] Create comprehensive `SUBPROJECTS.md` file:

```markdown
# Volcano Repositories and Subproject Governance

## Current Repositories

| Repository | Purpose |
|------------|---------|
| [volcano-sh/volcano](https://github.com/volcano-sh/volcano) | Main project - Kubernetes batch scheduling system |
| [volcano-sh/website](https://github.com/volcano-sh/website) | Project documentation and website |
| [volcano-sh/community](https://github.com/volcano-sh/community) | Community governance and processes |
| [volcano-sh/devices](https://github.com/volcano-sh/devices) | Device plugin support |
| other subprojects... | |

**Maintenance:** All repositories are maintained collectively by [Volcano maintainers](https://github.com/volcano-sh/community/blob/master/MAINTAINERS.md). There are no dedicated subproject-specific maintainers.

## Proposing New Subprojects

[Copy the relevant sections from subproject-creation.md here, including:
- Proposal process
- Requirements
- Review and approval process]

## Subproject Archival

A repository may be archived under the following conditions:
- No significant activity for 6+ months
- No longer aligned with Volcano's mission
- Superseded by another solution

**Archival Process:**
1. Any maintainer proposes archival via GitHub issue
2. Community discussion for 2 weeks
3. Decision by maintainer consensus
4. Repository marked as archived on GitHub
5. README updated with archival notice

Archived repositories can be reactivated if new maintainers emerge.
```

- [ ] After creating SUBPROJECTS.md:
  - Update GOVERNANCE.md to reference SUBPROJECTS.md instead of subproject-creation.md
  - Consider deprecating subproject-creation.md (or keep as historical reference)

**File to Create:** `SUBPROJECTS.md`

---

## Summary of Actions Required

Below is a consolidated task list for easy tracking and sub-issue creation. Each task corresponds to a Required item detailed above.

### GOVERNANCE.md
- [ ] **Req 2.1** Add Communication and Meetings section (document async-first approach)
- [ ] **Req 3** Add Vendor Neutrality section
- [ ] **Req 4** Add Decision Making section (Requests to CNCF + Modifying Governance processes)

### community-membership.md  
- [ ] **Req 2.2** Remove "Owner" role
- [ ] **Req 2.2** Update Maintainer requirements (nomination + majority vote)
- [ ] **Req 2.2** Add Role Promotion Process section
- [ ] **Req 11** Add Role Assignment Records section (explain distributed tracking)

### MAINTAINERS.md
- [ ] **Req 7** Add Maintainer Changes section (track lifecycle events)
- [ ] **Req 8** Add Email column to maintainer table
- [ ] **Req 8** Add note about generalist maintainer model (no domain assignments)
- [ ] **Req 11** Add Emeritus Permissions policy under Emeritus section

### PST.md (via PR #97)
- [ ] **Req 5** Complete PR #97: Add member assignments, onboarding/offboarding processes

### SUBPROJECTS.md (new file)
- [ ] **Req 14 & 15** Create comprehensive SUBPROJECTS.md with:
  - Repository inventory table
  - Collective maintenance explanation
  - Subproject creation process (from subproject-creation.md)
  - Subproject archival process

### Code of Conduct
- [ ] **Req 12 & 13** Merge PR #106, then update all CoC links in GOVERNANCE.md and community-membership.md

---

## Reference Materials

- [CNCF Graduation Application Template](https://github.com/cncf/toc/blob/main/.github/ISSUE_TEMPLATE/template-graduation-application.md)
- [CNCF Vendor Neutrality Guide](https://contribute.cncf.io/maintainers/community/vendor-neutrality/)

---

## Task Assignment

Please comment below to claim tasks or discuss implementation approaches.

