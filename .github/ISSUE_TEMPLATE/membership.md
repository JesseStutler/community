name: Organization Membership Request
description: Request membership in Volcano Org
labels: [ "area/github-membership" ]
title: "REQUEST: New membership for <your-GH-handle>"
body:
- id: github
  type: input
  attributes:
    label: GitHub Username
    placeholder: e.g. @example_user
  validations:
    required: true
- id: requirements
  type: checkboxes
  attributes:
    label: Requirements
    options:
      - label: I have reviewed the [community membership guidelines](https://github.com/volcano-sh/community/blob/master/community-membership.md)
        required: true
      - label: I have [enabled 2FA on my GitHub account](https://github.com/settings/security)
        required: true
      - label: I have subscribed to the [Volcano Mailing List](https://groups.google.com/forum/#!forum/volcano-sh)
        required: true
      - label: I am actively contributing to 1 or more Volcano subprojects
        required: true
      - label: I have two sponsors that meet the sponsor requirements listed in the community membership guidelines
        required: true
      - label: I have spoken to my sponsors ahead of this application, and they have agreed to sponsor my application
        required: true
      - label: I have verified that my sponsors are a reviewer or an approver in at least one OWNERS file within one of the Volcano GitHub organizations
        required: true
- id: sponsor_guidance
  type: markdown
  attributes:
    value: |
      **Sponsor Guidelines:**
      - It is highly recommended that your two sponsors come from different member companies to ensure diversity
- id: sponsor_1
  type: input
  attributes:
    label: "Sponsor 1"
    description: GitHub handle of your sponsor
    placeholder: e.g. @sponsor-1
  validations:
    required: true
- id: sponsor_2
  type: input
  attributes:
    label: "Sponsor 2"
    description: GitHub handle of your sponsor
    placeholder: e.g. @sponsor-2
  validations:
    required: true
- id: contributions
  type: textarea
  attributes:
    label: List of contributions to the Volcano project
    placeholder: |
    - PRs reviewed / authored
    - Issues authored
    - Issues responded to
  validations:
    required: true