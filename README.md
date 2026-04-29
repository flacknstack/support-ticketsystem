# Support Ticket System
This plugin extends the forum with a structured support ticket system, specifically tailored for forums where a separate topic is created for every support inquiry or issue.<br>
<br>
In the Administration Control Panel (ACP), custom prefixes can be defined for the support section, allowing topics to be clearly categorized upon creation. These prefixes might cover areas such as Design, Technical Issues, Lore, or Organizational Matters. A clear and descriptive name is assigned to each prefix, which subsequently appears in the selection menu when creating a new topic. Additionally, the visual presentation of these prefixes can be customized—ranging from plain text to HTML-formatted styles. Furthermore, for each prefix, specific team members can be designated as responsible for handling the corresponding inquiries. This allows for either the selection of specific individuals or the assignment of responsibility to the entire team.<br>
<br>
When creating a new topic within the support section, selecting an appropriate prefix is ​​mandatory. Once a topic has been created, all designated team members receive a notification banner on the forum index page. Via this banner, a team member can directly claim the inquiry. Once claimed, the notification disappears for all other team members. Within the topic itself and in the forum topic list, the name of the assigned team member is displayed, making it clear who is responsible for that specific topic. If the MyAlerts extension is installed, the topic's original author will also receive a notification informing them which team member has claimed their inquiry.<br>
<br>
The notification regarding an open support topic remains visible to the assigned team member until the topic is marked as resolved or is moved out of the designated support forum—for instance, by being moved to an archive. Topics can be marked as resolved by either team members or the original author themselves.<br>
<br>
Additionally, it is possible at any time to release an inquiry that has already been claimed. This can be done directly via a dedicated link located within the notification banner. In this case, the notification is displayed again for all responsible team members, allowing the request to be redistributed.

# Prerequisites
- The ACP module <a href="https://github.com/little-evil-genius/rpgstuff_modul" target="_blank">RPG Stuff</a> <b>must</b> be present.
- The <a href="https://doylecc.altervista.org/bb/downloads.php?dlid=26&cat=2" target="_blank">Accountswitcher</a> by doylecc <b>must</b> be installed.

# Recommended
- <a href="https://github.com/MyBBStuff/MyAlerts\" target="_blank">MyAlerts</a> by EuanT

# Database Changes
Added table:
- ticketsystem<br>
<br>
Added columns to `threads` table:
- ticketsystem_prefix
- ticketsystem_teammember
- ticketsystem_solved

# New Language Files
- deutsch_du/admin/ticketsystem.lang.php
- deutsch_du/ticketsystem.lang.php

# Settings<br>
- Team Groups
- Nickname
- Support Section<br>
<br>
<b>NOTE:</b><br>
The plugin is compatible with MyBB's classic profile fields and/or the <a href="https://github.com/katjalennartz/application_ucp">Profile Sheet Plugin by Risuena</a>.

# New Template Group within the Theme Templates
- Support Ticket System

# New Templates (not global!)
- ticketsystem_banner
- ticketsystem_forumdisplay
- ticketsystem_newthread
- ticketsystem_showthread
- ticketsystem_showthread_button<br>
<br>
<b>NOTE:</b><br>
The layout has been adapted to the default MyBB theme. # New Variables
- header: {$ticketsystem_banner}
- newthread: {$newthread_ticketsystem}
- showthread: {$ticketsystem_button} + {$ticketsystem_prefix} + {$ticketsystem_teammember}
- forumdisplay_thread: {$ticketsystem_prefix} + {$ticketsystem_teammember}

# Setting User Group Permissions
To ensure that all Admin accounts have access to manage Ticket System prefixes within the ACP, permissions must be configured once under the tab *Users & Groups* » *Administrator Permissions* » *User Group Permissions*. The permissions for the Ticket System are located within the 'RPG Extensions' tab.

# Links
### ACP
index.php?module=rpgstuff-rpgstuff-ticketsystem

# Demo
## ACP
<img src="https://stormborn.at/plugins/ticketsystem_acp.png">
<img src="https://stormborn.at/plugins/ticketsystem_add.png">

## Forum
<img src="https://stormborn.at/plugins/ticketsystem_newthread.png">
<img src="https://stormborn.at/plugins/ticketsystem_forumdisplay.png">
<img src="https://stormborn.at/plugins/ticketsystem_showthread.png">
<img src="https://stormborn.at/plugins/ticketsystem_banner.png">
