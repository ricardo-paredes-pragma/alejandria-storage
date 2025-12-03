---
title: Alejandria Development Home
description: home page
published: true
date: 2025-12-03T04:08:06.661Z
tags: 
editor: markdown
dateCreated: 2025-11-28T13:55:22.843Z
---

# Alejandría Development Page	
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

title Container Diagram - Academia Pragma

Person(user, "User", "Student, Instructor, or Administrator")

System_Boundary(c1, "Academia Pragma Ecosystem") {
    Container(web_portal, "Web Portal", "Web Application", "The main interface for users to interact with the system.")
    Container(lms, "LMS", "Learning Management System", "Core engine for course management and tracking.")
    Container(cms, "CMS", "Content Management System", "Stores and manages educational resources.")
}

System_Ext(slack, "Slack", "Communication Tool", "Used for notifications and community interaction.")
System_Ext(idp, "IDP", "Identity Provider", "Handles user authentication and authorization.")
System_Ext(git_repo, "GIT Repo", "Version Control System", "Stores code and versioned assignments.")

Rel(user, web_portal, "Uses", "HTTPS")
Rel(web_portal, idp, "Authenticates users using", "OIDC / SAML")
Rel(web_portal, lms, "Delegates learning tasks to", "API")
Rel(web_portal, cms, "Retrieves content from", "API")
Rel(web_portal, slack, "Sends notifications to", "Webhooks")
Rel(web_portal, git_repo, "Interacts with", "Git / API")

@enduml
```