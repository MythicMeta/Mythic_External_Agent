# Mythic External Agent

This repo defines the folder structure for an external Mythic agent that can be remotely "installed" into a Mythic instance. This process allows users to create their own Mythic agents and host them on their own GitHub repositories while also allowing an easy process to install agents.

## Folder Structure

### Payload_Type

This folder should contain exactly what you have in your `Payload_Types` folder for Mythic. Specifically, it should contain one folder with the same name as your agent. 

Example: https://github.com/its-a-feature/Mythic/tree/master/Payload_Types

### C2_Profiles

This folder should contain exactly what you have in your `C2_Profiles` folder if you added a new C2 Profile for your agent. Specifically, it should containe a folder with the name of the C2 Profile for every C2 Profile you added. If you have no additional C2 Profiles, leave this folder empty.

Example: https://github.com/its-a-feature/Mythic/tree/master/C2_Profiles

### documentation-c2

This folder contains all of the contents for the documentation-docker container that petains to your new C2 profiles (if any). If you have no extra documentation, then leave this folder empty.

Example: https://github.com/its-a-feature/Mythic/tree/master/documentation-docker/content/C2%20Profiles

### documentation-payload

This folde contains all of the contents for the documentation-docker container that pertains to your new payload type. If you have no documentation (you reall should though), then leave this folder empty.

Example: https://github.com/its-a-feature/Mythic/tree/master/documentation-docker/content/Agents 

## Config.json

This file configures which components to ignore on the install process.

### exclude_payload_type

Setting this value to `true` means that after cloning down the remote repository, the installer program will _NOT_ copy the contents of the `Payload_Type` folder into the local `Payload_Types` folder. This is helpful for when an agent's Payload Type contents needs to be installed on a specific computer/VM and _not_ used as part of a Docker deployment.

### exclude_c2_profiles

Setting this value to `true` means that after cloning down the remote repository, the installer program wil _NOT_ copy the contents of the `C2_Profiles` folder into the local `C2_Profiles` folder. This is helpful for when an agent's C2 Profiles might need to run on a different Computer/VM and _not_ used as part of a Docker deployment locally to Mythic.

### exclude_documentation_payload

Setting this value to `true` will prevent Mythic from copying the contents into the documentation-docker's agent folders.

### exclude_documentation_c2

Setting this value to `true` will prevent Mythic from copying the vontents into the documentation-docker's c2 folders.
