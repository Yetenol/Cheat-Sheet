# [⌂](../README.md) › [Windows](../README.md#windows) › GUID shortcuts
- shortcuts to special OS folders
- referenced using a [**CLSID keys**](https://docs.microsoft.com/de-de/windows/win32/com/clsid-key-hklm?redirectedfrom=MSDN) 
    - globally unique identifier that identifies a COM class object

## Open a shortcut

- run one of the following:
```powershell
explorer shell:::{088e3905-0323-4b02-9826-5d99428e115f}
```

```powershell
explorer /e,::{088e3905-0323-4b02-9826-5d99428e115f}
```

## Resolve a shortcut

- return the location as a string:

```powershell
(New-Object -ComObject Shell.Application).NameSpace('shell:::{088e3905-0323-4b02-9826-5d99428e115f}').Self.Path
```


| Target                                                                 | GUID shortcut                                                                                                   |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| 3D Objects (folder)                                                    | `shell:::{0DB7E03F-FC29-4DC6-9020-FF41B59E513A}`                                                                |
| Add Network Location                                                   | `shell:::{D4480A50-BA28-11d1-8E75-00C04FA31A86}`                                                                |
| Administrative Tools                                                   | `shell:::{D20EA4E1-3957-11d2-A40B-0C5020524153}`                                                                |
| Applications                                                           | `shell:::{4234d49b-0245-4df3-b780-3893943456e1}`                                                                |
| **`AutoPlay`**                                                         | `shell:::{9C60DE1E-E5FC-40f4-A487-460851A8D915}`                                                                |
| Backup and Restore (Windows 7)                                         | `shell:::{B98A2BEA-7D42-4558-8BD1-832F41BAC6FD}`                                                                |
| BitLocker Drive Encryption                                             | `shell:::{D9EF8727-CAC2-4e60-809E-86F80A666C91}`                                                                |
| Bluetooth Devices                                                      | `shell:::{28803F59-3A75-4058-995F-4EE5503B023C}`                                                                |
| Color Management                                                       | `shell:::{B2C761C6-29BC-4f19-9251-E6195265BAF1}`                                                                |
| Command Folder                                                         | `shell:::{437ff9c0-a07f-4fa0-af80-84b6c6440a16}`                                                                |
| Common Places FS Folder                                                | `shell:::{d34a6ca6-62c2-4c34-8a7c-14709c1ad938}`                                                                |
| Control Panel                                                          | `shell:::{5399E694-6CE5-4D6C-8FCE-1D8870FDCBA0}`                                                                |
| **`Control Panel (All Tasks)`**                                        | `shell:::{ED7BA470-8E54-465E-825C-99712043E01C}`                                                                |
| Control Panel (Always Icons view)                                      | `shell:::{21EC2020-3AEA-1069-A2DD-08002B30309D}`                                                                |
| Control Panel (Always Category view)                                   | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}`                                                                |
| ⠀⮱ Appearance and Personalization                                      | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\1`                                                              |
| ⠀⮱ Clock and Region                                                    | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\6`                                                              |
| ⠀⮱ Ease of Access                                                      | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\7`                                                              |
| ⠀⮱ Hardware and Sound                                                  | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\2`                                                              |
| ⠀⮱ Network and Internet                                                | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\3`                                                              |
| ⠀⮱ Programs                                                            | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\8`                                                              |
| ⠀⮱ System and Security                                                 | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\5`<br>or<br>`shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\10` |
| ⠀⮱ User Accounts                                                       | `shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\9`                                                              |
| Credential Manager                                                     | `shell:::{1206F5F1-0569-412C-8FEC-3204630DFB70}`                                                                |
| Date and Time                                                          | `shell:::{E2E7934B-DCE5-43C4-9576-7FE4F75E7480}`                                                                |
| Default Programs                                                       | `shell:::{17cd9488-1228-4b2f-88ce-4298e93e0966}`                                                                |
| ⠀⮱ `Default Apps` page in Settings                                     | `shell:::{17cd9488-1228-4b2f-88ce-4298e93e0966}\pageDefaultProgram`                                             |
| ⠀⮱ `Default Apps` page in Settings                                     | `shell:::{17cd9488-1228-4b2f-88ce-4298e93e0966}\pageFileAssoc`                                                  |
| delegate folder that appears in Computer                               | `shell:::{b155bdf8-02f0-451e-9a26-ae317cfd7779}`                                                                |
| Desktop (folder)                                                       | `shell:::{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}`                                                                |
| Device Manager                                                         | `shell:::{74246bfc-4c96-11d0-abef-0020af6b0b7a}`                                                                |
| Devices and Printers                                                   | `shell:::{A8A91A66-3A7D-4424-8D24-04E180695C7A}`                                                                |
| Documents (folder)                                                     | `shell:::{A8CDFF1C-4878-43be-B5FD-F8091C1C60D0}`<br>or<br>`shell:::{d3162b92-9365-467a-956b-92703aca08af}`      |
| Downloads (folder)                                                     | `shell:::{088e3905-0323-4b02-9826-5d99428e115f}`<br>or<br>`shell:::{374DE290-123F-4565-9164-39C4925E467B}`      |
| Ease of Access Center                                                  | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}`                                                                |
| ⠀⮱ Use the computer without a display                                  | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageNoVisual`                                                   |
| ⠀⮱ Make the computer easier to see                                     | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageEasierToSee`                                                |
| ⠀⮱ Use the computer without a mouse or keyboard                        | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageNoMouseOrKeyboard`                                          |
| ⠀⮱ Make the mouse easier to use                                        | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageEasierToClick`                                              |
| ⠀⠀⠀⮱ Set up Mouse Keys                                                 | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageMouseKeysSettings`                                          |
| ⠀⮱ Make the keyboard easier to use                                     | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageKeyboardEasierToUse`                                        |
| ⠀⮱ Use text or visual alternatives for sounds                          | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageEasierWithSounds`                                           |
| ⠀⮱ Make it easier to focus on tasks                                    | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageEasierToReadAndWrite`                                       |
| ⠀⮱ Set up Filter Keys                                                  | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageFilterKeysSettings`                                         |
| ⠀⠀⠀⮱ Set up Sticky Keys                                                | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageStickyKeysSettings`                                         |
| ⠀⮱ Get recommendations to make your computer easier to use (cognitive) | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageQuestionsCognitive`                                         |
| ⠀⮱ Get recommendations to make your computer easier to use (eyesight)  | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageQuestionsEyesight`                                          |
| ⠀⮱ Set up Repeat and Slow Keys                                         | `shell:::{D555645E-D4F8-4c29-A827-D93C859C4F2A}\pageRepeatRateSlowKeysSettings`                                 |
| **`E-mail (default e-mail program)`**                                  | `shell:::{2559a1f5-21d7-11d4-bdaf-00c04f60b9f0}`                                                                |
| Favorites                                                              | `shell:::{323CA680-C24D-4099-B94D-446DD2D7249E}`                                                                |
| File Explorer Options                                                  | `shell:::{6DFD7C5C-2451-11d3-A299-00C04F8EF6AF}`                                                                |
| File History                                                           | `shell:::{F6B6E965-E9B2-444B-9286-10C9152EDBC5}`                                                                |
| Folder Options                                                         | `shell:::{6DFD7C5C-2451-11d3-A299-00C04F8EF6AF}`                                                                |
| Font Settings                                                          | `shell:::{93412589-74D4-4E4E-AD0E-E0CB621440FD}`                                                                |
| Fonts (folder)                                                         | `shell:::{BD84B380-8CA2-1069-AB1D-08000948F534}`                                                                |
| Frequent folders                                                       | `shell:::{3936E9E4-D92C-4EEE-A85A-BC16D5EA0819}`                                                                |
| Games Explorer                                                         | `shell:::{ED228FDF-9EA8-4870-83b1-96b02CFE0D52}`                                                                |
| Get Programs                                                           | `shell:::{15eae92e-f17a-4431-9f28-805e482dafd4}`                                                                |
| Help and Support                                                       | `shell:::{2559a1f1-21d7-11d4-bdaf-00c04f60b9f0}`                                                                |
| Hyper-V Remote File Browsing                                           | `shell:::{0907616E-F5E6-48D8-9D61-A91C3D28106D}`                                                                |
| **`Indexing Options`**                                                 | `shell:::{87D66A43-7B11-4A28-9811-C86EE395ACF7}`                                                                |
| Infared (if installed)                                                 | `shell:::{A0275511-0E86-4ECA-97C2-ECD8F1221D08}`                                                                |
| Installed Updates                                                      | `shell:::{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd}`                                                                |
| Intel Rapid Storage Technology (if installed)                          | `shell:::{E342F0FE-FF1C-4c41-BE37-A0271FC90396}`                                                                |
| Internet Options (Internet Explorer)                                   | `shell:::{A3DD4F92-658A-410F-84FD-6FBBBEF2FFFE}`                                                                |
| Keyboard Properties                                                    | `shell:::{725BE8F7-668E-4C7B-8F90-46BDB0936430}`                                                                |
| Libraries                                                              | `shell:::{031E4825-7B94-4dc3-B131-E946B44C8DD5}`                                                                |
| Location Information (Phone and Modem Control Panel)                   | `shell:::{40419485-C444-4567-851A-2DD7BFA1684D}`                                                                |
| Location Settings                                                      | `shell:::{E9950154-C418-419e-A90A-20C5287AE24B}`                                                                |
| Media Servers                                                          | `shell:::{289AF617-1CC3-42A6-926C-E6A863F0E3BA}`                                                                |
| **`Mouse Properties`**                                                 | `shell:::{6C8EEC18-8D75-41B2-A177-8831D59D2D50}`                                                                |
| Music (folder)                                                         | `shell:::{1CF1260C-4DD0-4ebb-811F-33C572699FDE}`<br>or<br>`shell:::{3dfdf296-dbec-4fb4-81d1-6a3438bcf4de}`      |
| My Documents                                                           | `shell:::{450D8FBA-AD25-11D0-98A8-0800361B1103}`                                                                |
| **`User Accounts (netplwiz)`**                                         | `shell:::{7A9D77BD-5403-11d2-8785-2E0420524153}`                                                                |
| Network                                                                | `shell:::{F02C1A0D-BE21-4350-88B0-7367FC96EF3C}`                                                                |
| Network and Sharing Center                                             | `shell:::{8E908FC9-BECC-40f6-915B-F4CA0E70D03D}`                                                                |
| ⠀⮱ Advanced sharing settings                                           | `shell:::{8E908FC9-BECC-40f6-915B-F4CA0E70D03D}\Advanced`                                                       |
| ⠀⮱ Media streaming options                                             | `shell:::{8E908FC9-BECC-40f6-915B-F4CA0E70D03D}\ShareMedia`                                                     |
| **`Network Connections (adapters)`**                                   | `shell:::{7007ACC7-3202-11D1-AAD2-00805FC1270E}`<br>or<br>`shell:::{992CFFA0-F557-101A-88EC-00DD010CCC48}`      |
| Network (WorkGroup)                                                    | `shell:::{208D2C60-3AEA-1069-A2D7-08002B30309D}`                                                                |
| Notification Area Icons                                                | `shell:::{05d7b0f4-2121-4eff-bf6b-ed3f69b894d9}`                                                                |
| NVIDIA Control Panel (if installed)                                    | `shell:::{0bbca823-e77d-419e-9a44-5adec2c8eeb0}`                                                                |
| Offline Files Folder                                                   | `shell:::{AFDB1F70-2A4C-11d2-9039-00C04F8EEB3E}`                                                                |
| **`OneDrive`**                                                         | `shell:::{018D5C66-4533-4307-9B53-224DE2ED1FE6}`                                                                |
| Pen and Touch                                                          | `shell:::{F82DF8F7-8B9F-442E-A48C-818EA735FF9B}`                                                                |
| Personalization                                                        | `shell:::{ED834ED6-4B5A-4bfe-8F11-A626DCB6A921}`                                                                |
| ⠀⮱ Color and Appearance                                                | `shell:::{ED834ED6-4B5A-4bfe-8F11-A626DCB6A921}\pageColorization`                                               |
| ⠀⮱ **`Desktop Background`**                                            | `shell:::{ED834ED6-4B5A-4bfe-8F11-A626DCB6A921}\pageWallpaper`                                                  |
| Pictures (folder)                                                      | `shell:::{24ad3ad4-a569-4530-98e1-ab02f9417aa8}`<br>or<br>`shell:::{3ADD1653-EB32-4cb0-BBD7-DFA0ABB5ACCA}`      |
| Portable Devices                                                       | `shell:::{35786D3C-B075-49b9-88DD-029876E11C01}`                                                                |
| Power Options                                                          | `shell:::{025A5937-A6BE-4686-A844-36FE4BEC8B6D}`                                                                |
| ⠀⮱ Create a power plan                                                 | `shell:::{025A5937-A6BE-4686-A844-36FE4BEC8B6D}\pageCreateNewPlan`                                              |
| ⠀⮱ Edit Plan Settings                                                  | `shell:::{025A5937-A6BE-4686-A844-36FE4BEC8B6D}\pagePlanSettings`                                               |
| ⠀⮱ System Settings                                                     | `shell:::{025A5937-A6BE-4686-A844-36FE4BEC8B6D}\pageGlobalSettings`                                             |
| Previous Versions Results Folder                                       | `shell:::{f8c2ab3b-17bc-41da-9758-339d7dbf2d88}`                                                                |
| printhood delegate folder                                              | `shell:::{ed50fc29-b964-48a9-afb3-15ebb9b97f36}`                                                                |
| Printers                                                               | `shell:::{2227A280-3AEA-1069-A2DE-08002B30309D}`<br>or<br>`shell:::{863aa9fd-42df-457b-8e4d-0de1b8015c60}`      |
| Problem Reporting Settings                                             | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageSettings`                                                   |
| Programs and Features                                                  | `shell:::{7b81be6a-ce2b-4676-a29e-eb907a5126c5}`                                                                |
| Public (folder)                                                        | `shell:::{4336a54d-038b-4685-ab02-99bb52d3fb8b}`                                                                |
| Quick access                                                           | `shell:::{679f85cb-0220-4080-b29b-5540cc05aab6}`                                                                |
| Recent folders                                                         | `shell:::{22877a6d-37a1-461a-91b0-dbda5aaebc99}`                                                                |
| Recent Items Instance Folder                                           | `shell:::{4564b25e-30cd-4787-82ba-39e73a750b14}`                                                                |
| Recovery                                                               | `shell:::{9FE63AFD-59CF-4419-9775-ABCC3849F861}`                                                                |
| **`Recycle Bin`**                                                      | `shell:::{645FF040-5081-101B-9F08-00AA002F954E}`                                                                |
| Region                                                                 | `shell:::{62D8ED13-C9D0-4CE8-A914-47DD628FB1B0}`                                                                |
| Reliability Monitor                                                    | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageReliabilityView`                                            |
| Remote Assistance                                                      | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\raPage`                                                         |
| RemoteApp and Desktop Connections                                      | `shell:::{241D7C96-F8BF-4F85-B01F-E2B043341A4B}`                                                                |
| ⠀⮱ Connection Properties                                               | `shell:::{241D7C96-F8BF-4F85-B01F-E2B043341A4B}\PropertiesPage`                                                 |
| Remote Printers                                                        | `shell:::{863aa9fd-42df-457b-8e4d-0de1b8015c60}`                                                                |
| Removable Drives                                                       | `shell:::{F5FB2C77-0E2F-4A16-A381-3E560C68BC83}`                                                                |
| Removable Storage Devices                                              | `shell:::{a6482830-08eb-41e2-84c1-73920c2badb9}`                                                                |
| Results Folder                                                         | `shell:::{2965e715-eb66-4719-b53f-1672673bbefa}`                                                                |
| Run                                                                    | `shell:::{2559a1f3-21d7-11d4-bdaf-00c04f60b9f0}`                                                                |
| Search (File Explorer)                                                 | `shell:::{9343812e-1c37-4a49-a12e-4b2d810d956b}`                                                                |
| Search (Windows)                                                       | `shell:::{2559a1f8-21d7-11d4-bdaf-00c04f60b9f0}`                                                                |
| Security and Maintenance                                               | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}`                                                                |
| ⠀⮱ Advanced Problem Reporting Settings                                 | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageAdvSettings`                                                |
| ⠀⮱ Change Security and Maintenance settings                            | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\Settings`                                                       |
| ⠀⮱ Problem Details                                                     | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageReportDetails`                                              |
| ⠀⮱ Problem Reporting Settings                                          | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageSettings`                                                   |
| ⠀⮱ Problem Reports                                                     | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageProblems`                                                   |
| ⠀⮱ Reliability Monitor                                                 | `shell:::{BB64F8A7-BEE7-4E1A-AB8D-7D8273F7FDB6}\pageReliabilityView`                                            |
| Set Program Access and Computer Defaults                               | `shell:::{2559a1f7-21d7-11d4-bdaf-00c04f60b9f0}`                                                                |
| **`Show Desktop`**                                                     | `shell:::{3080F90D-D7AD-11D9-BD98-0000947B0257}`                                                                |
| **`Sound`**                                                            | `shell:::{F2DDFC82-8F12-4CDD-B7DC-D4FE1425AA4D}`                                                                |
| Speech Recognition                                                     | `shell:::{58E3C745-D971-4081-9034-86E34B30836A}`                                                                |
| Storage Spaces                                                         | `shell:::{F942C606-0914-47AB-BE56-1321B8035096}`                                                                |
| Sync Center                                                            | `shell:::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}`                                                                |
| ⠀⮱ Sync Setup                                                          | `shell:::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}\::{F1390A9A-A3F4-4E5D-9C5F-98F3BD8D935C}`                       |
| ⠀⮱ Sync Setup Folder                                                   | `shell:::{2E9E59C0-B437-4981-A647-9C34B9B90891}`                                                                |
| System                                                                 | `shell:::{BB06C0E4-D293-4f75-8A90-CB05B6477EEE}`                                                                |
| System Icons                                                           | `shell:::{05d7b0f4-2121-4eff-bf6b-ed3f69b894d9}\SystemIcons`                                                    |
| System Restore                                                         | `shell:::{3f6bc534-dfa1-4ab4-ae54-ef25a74e0107}`                                                                |
| Tablet PC Settings                                                     | `shell:::{80F3F1D5-FECA-45F3-BC32-752C152E456E}`                                                                |
| **`Task View`**                                                        | `shell:::{3080F90E-D7AD-11D9-BD98-0000947B0257}`                                                                |
| **`Taskbar - User Pinned`**                                            | `shell:::{1f3427c8-5c10-4210-aa03-2ee45287d668}`                                                                |
| Taskbar and Navigation properties                                      | `shell:::{0DF44EAA-FF21-4412-828E-260A8728E7F1}`                                                                |
| `Taskbar page` in Settings                                             | `shell:::{0DF44EAA-FF21-4412-828E-260A8728E7F1}`                                                                |
| Text to Speech                                                         | `shell:::{D17D1D6D-CC3F-4815-8FE3-607E7D5D10B3}`                                                                |
| This Device                                                            | `shell:::{5b934b42-522b-4c34-bbfe-37a3ef7b9c90}`                                                                |
| This PC                                                                | `shell:::{20D04FE0-3AEA-1069-A2D8-08002B30309D}`                                                                |
| Troubleshooting                                                        | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}`                                                                |
| ⠀⮱ Additional Information                                              | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\resultPage`                                                     |
| ⠀⮱ All Categories                                                      | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\listAllPage`                                                    |
| ⠀⮱ Change Settings                                                     | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\settingPage`                                                    |
| ⠀⮱ History                                                             | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\historyPage`                                                    |
| ⠀⮱ Search Troubleshooting                                              | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\searchPage`                                                     |
| ⠀⮱ Troubleshoot problems - Hardware and Sound                          | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\devices`                                                        |
| ⠀⮱ Troubleshoot problems - Network and Internet                        | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\network`                                                        |
| ⠀⮱ Troubleshoot problems - Programs                                    | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\applications`                                                   |
| ⠀⮱ Troubleshoot problems - System and Security                         | `shell:::{C58C4893-3BE0-4B45-ABB5-A63E4B8C8651}\system`                                                         |
| User Accounts                                                          | `shell:::{60632754-c523-4b62-b45c-4172da012619}`                                                                |
| ⠀⮱ Change Your Name                                                    | `shell:::{60632754-c523-4b62-b45c-4172da012619}\pageRenameMyAccount`                                            |
| ⠀⮱ Manage Accounts                                                     | `shell:::{60632754-c523-4b62-b45c-4172da012619}\pageAdminTasks`                                                 |
| **`User Accounts (netplwiz)`**                                         | `shell:::{7A9D77BD-5403-11d2-8785-2E0420524153}`                                                                |
| %UserProfile%                                                          | `shell:::{59031a47-3f72-44a7-89c5-5595fe6b30ee}`                                                                |
| Videos (folder)                                                        | `shell:::{A0953C92-50DC-43bf-BE83-3742FED03C9C}`<br>or<br>`shell:::{f86fa3ab-70d2-4fc7-9c99-fcbf05467f3a}`      |
| Web browser (default)                                                  | `shell:::{871C5380-42A0-1069-A2EA-08002B30309D}`                                                                |
| Windows Defender Firewall                                              | `shell:::{4026492F-2F69-46B8-B9BF-5654FC07E423}`                                                                |
| ⠀⮱ Allowed apps                                                        | `shell:::{4026492F-2F69-46B8-B9BF-5654FC07E423}\pageConfigureApps`                                              |
| ⠀⮱ Customize Settings                                                  | `shell:::{4026492F-2F69-46B8-B9BF-5654FC07E423}\PageConfigureSettings`                                          |
| ⠀⮱ Restore defaults                                                    | `shell:::{4026492F-2F69-46B8-B9BF-5654FC07E423}\PageRestoreDefaults`                                            |
| Windows Mobility Center                                                | `shell:::{5ea4f148-308c-46d7-98a9-49041b1dd468}`                                                                |
| Windows Features                                                       | `shell:::{67718415-c450-4f3c-bf8a-b487642dc39b}`                                                                |
| Windows To Go                                                          | `shell:::{8E0C279D-0BD1-43C3-9EBD-31C3DC5B8A77}`                                                                |
| Work Folders                                                           | `shell:::{ECDB0924-4208-451E-8EE0-373C0956DE16}`                                                                |

## More entries

| Description              | GUID                                     | Default location                                                                      |
| ------------------------ | ---------------------------------------- | ------------------------------------------------------------------------------------- |
| 3D Objects               | `{31C0DD25-9439-4F12-BF41-7FF4EDA38722}` | `%USERPROFILE%\3D Objects`                                                            |
| Account Pictures         | `{008CA0B1-55B4-4C56-B8A8-4DE4B299D3BE}` | `%APPDATA%\Microsoft\Windows\AccountPictures`                                         |
| Administrative Tools     | `{724EF170-A42D-4FEF-9F26-B60E846FBA4F}` | `%APPDATA%\Microsoft\Windows\Start Menu\Programs\Administrative Tools`                |
| Administrative Tools     | `{D0384E7D-BAC3-4797-8F14-CBA229B392B5}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools`        |
| AppDataDesktop           | `{B2C5E279-7ADD-439F-B28C-C41FE1BBF672}` | `%LOCALAPPDATA%\Desktop`                                                              |
| AppDataDocuments         | `{7BE16610-1F7F-44AC-BFF0-83E15F2FFCA1}` | `%LOCALAPPDATA%\Documents`                                                            |
| AppDataFavorites         | `{7CFBEFBC-DE1F-45AA-B843-A542AC536CC9}` | `%LOCALAPPDATA%\Favorites`                                                            |
| AppDataProgramData       | `{559D40A3-A036-40FA-AF61-84CB430A4D34}` | `%LOCALAPPDATA%\ProgramData`                                                          |
| Application Shortcuts    | `{A3918781-E5F2-4890-B3D9-A7E54332328C}` | `%LOCALAPPDATA%\Microsoft\Windows\Application Shortcuts`                              |
| Applications             | `{1E87508D-89C2-42F0-8A7E-645A0F50CA58}` | `Virtual folder`                                                                      |
| Camera Roll              | `{767E6811-49CB-4273-87C2-20F355E1085B}` | `%USERPROFILE%\OneDrive\Pictures\Camera Roll`                                         |
| Camera Roll              | `{AB5FB87B-7CE2-4F83-915D-550846C9537B}` | `%USERPROFILE%\Pictures\Camera Roll`                                                  |
| Common Files             | `{6365D5A7-0F0D-45E5-87F6-0DA56B6A4F7D}` | `%ProgramFiles%\Common Files`                                                         |
| Common Files             | `{DE974D24-D9C6-4D3E-BF91-F4455120B917}` | `%ProgramFiles%\Common Files`                                                         |
| Common Files             | `{F7F1ED05-9F6D-47A2-AAAE-29D317C6F066}` | `%ProgramFiles%\Common Files`                                                         |
| Computer                 | `{0AC0837C-BBF8-452A-850D-79D08E667CA7}` | `virtual folder`                                                                      |
| Conflicts                | `{4BFEFB45-347D-4006-A5BE-AC0CB0567192}` | `virtual folder`                                                                      |
| Contacts                 | `{56784854-C6CB-462B-8169-88E350ACB882}` | `%USERPROFILE%\Contacts`                                                              |
| Control Panel            | `{82A74AEB-AEB4-465C-A014-D097EE346D63}` | `virtual folder`                                                                      |
| Cookies                  | `{2B0F765D-C0E9-4171-908E-08A611B84FF6}` | `%APPDATA%\Microsoft\Windows\Cookies`                                                 |
| Desktop                  | `{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}` | `%USERPROFILE%\Desktop`                                                               |
| DeviceMetadataStore      | `{5CE4A5E9-E4EB-479D-B89F-130C02886155}` | `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore`                             |
| Documents                | `{24D89E24-2F19-4534-9DDE-6A6671FBB8FE}` | `%USERPROFILE%\OneDrive\Documents`                                                    |
| Documents                | `{7B0DB17D-9CD2-4A93-9733-46CC89022E7C}` | `%APPDATA%\Microsoft\Windows\Libraries\Documents.library-ms`                          |
| Documents                | `{FDD39AD0-238F-46AF-ADB4-6C85480369C7}` | `%USERPROFILE%\Documents`                                                             |
| Downloads                | `{374DE290-123F-4565-9164-39C4925E467B}` | `%USERPROFILE%\Downloads or %HOMEDRIVE%%HOMEPATH%\Downloads`                          |
| Favorites                | `{1777F761-68AD-4D8A-87BD-30B759FA33DD}` | `%USERPROFILE%\Favorites`                                                             |
| Fonts                    | `{FD228CB7-AE11-4AE3-864C-16F3910AB8FE}` | `%windir%\Fonts`                                                                      |
| Gadgets                  | `{7B396E54-9EC5-4300-BE0A-2482EBAE1A26}` | `%ProgramFiles%\Windows Sidebar\Gadgets`                                              |
| Gadgets                  | `{A75D362E-50FC-4FB7-AC2C-A8BEAA314493}` | `%LOCALAPPDATA%\Microsoft\Windows Sidebar\Gadgets`                                    |
| GameExplorer             | `{054FAE61-4DD8-4787-80B6-090220C4B700}` | `%LOCALAPPDATA%\Microsoft\Windows\GameExplorer`                                       |
| GameExplorer             | `{DEBF2536-E1A8-4C59-B6A2-414586476AEA}` | `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer`                                    |
| Games                    | `{CAC52C1A-B53D-4EDC-92D7-6B2E8AC19434}` | `virtual folder`                                                                      |
| Get Programs             | `{DE61D971-5EBC-4F02-A3A9-6C82895E5C04}` | `Virtual folder`                                                                      |
| History                  | `{0D4C3DB6-03A3-462F-A0E6-08924C41B5D4}` | `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\History`                            |
| History                  | `{D9DC8A3B-B784-432E-A781-5A1130A75963}` | `%LOCALAPPDATA%\Microsoft\Windows\History`                                            |
| Homegroup                | `{52528A6B-B9E3-4ADD-B60D-588C2DBA842D}` | `virtual folder`                                                                      |
| ImplicitAppShortcuts     | `{BCB5256F-79F6-4CEE-B725-DC34E402FD46}` | `%APPDATA%\Microsoft\Internet Explorer\Quick Launch\User Pinned\ImplicitAppShortcuts` |
| Installed Updates        | `{A305CE99-F527-492B-8B1A-7E76FA98D6E4}` | `Virtual folder`                                                                      |
| Libraries                | `{1B3EA5DC-B587-4786-B4EF-BD1DC332AEAE}` | `%APPDATA%\Microsoft\Windows\Libraries`                                               |
| Libraries                | `{48DAF80B-E6CF-4F4E-B800-0E69D84EE384}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Libraries`                                       |
| Libraries                | `{A302545D-DEFF-464B-ABE8-61C8648D939B}` | `virtual folder`                                                                      |
| Links                    | `{BFB9D5E0-C6A9-404C-B2B2-AE6DB6AF4968}` | `%USERPROFILE%\Links`                                                                 |
| Local                    | `{F1B32785-6FBA-4FCF-9D55-7B8E7F157091}` | `%LOCALAPPDATA% (%USERPROFILE%\AppData\Local`)                                        |
| LocalLow                 | `{A520A1A4-1780-4FF6-BD18-167343C5AF16}` | `%USERPROFILE%\AppData\LocalLow`                                                      |
| Microsoft Office Outlook | `{98EC0E18-2098-4D44-8644-66979315A281}` | `virtual folder`                                                                      |
| Music                    | `{2112AB0A-C86A-4FFE-A368-0DE96E47012E}` | `%APPDATA%\Microsoft\Windows\Libraries\Music.library-ms`                              |
| Music                    | `{4BD8D571-6D19-48D3-BE97-422220080E43}` | `%USERPROFILE%\Music`                                                                 |
| Network                  | `{D20BEEC4-5CA8-4905-AE3B-BF251EA09B53}` | `virtual folder`                                                                      |
| Network Connections      | `{6F0CD92B-2E97-45D1-88FF-B0D186B8DEDD}` | `virtual folder`                                                                      |
| Network Shortcuts        | `{C5ABBF53-E17F-4121-8900-86626FC2C973}` | `%APPDATA%\Microsoft\Windows\Network Shortcuts`                                       |
| None                     | `{2A00375E-224C-49DE-B8D1-440DF7EF3DDC}` | `%windir%\resources\0409 (code page`)                                                 |
| OEM Links                | `{C1BAE2D0-10DF-4334-BEDD-7AA20B227A9D}` | `%ALLUSERSPROFILE%\OEM Links`                                                         |
| Offline Files            | `{EE32E446-31CA-4ABA-814F-A5EBD2FD6D5E}` | `virtual folder`                                                                      |
| OneDrive                 | `{A52BBA46-E9E1-435F-B3D9-28DAA648C0F6}` | `%USERPROFILE%\OneDrive`                                                              |
| Original Images          | `{2C36C0AA-5812-4B87-BFD0-4CD0DFB19B39}` | `%LOCALAPPDATA%\Microsoft\Windows Photo Gallery\Original Images`                      |
| Pictures                 | `{339719B5-8C47-4894-94C2-D8F77ADD44A6}` | `%USERPROFILE%\OneDrive\Pictures`                                                     |
| Pictures                 | `{33E28130-4E1E-4676-835A-98395C3BC3BB}` | `%USERPROFILE%\Pictures`                                                              |
| Pictures                 | `{A990AE9F-A03B-4E80-94BC-9912D7504104}` | `%APPDATA%\Microsoft\Windows\Libraries\Pictures.library-ms`                           |
| Playlists                | `{DE92C1C7-837F-4F69-A3BB-86E631204A23}` | `%USERPROFILE%\Music\Playlists`                                                       |
| Printer Shortcuts        | `{9274BD8D-CFD1-41C3-B35E-B13F55A758F4}` | `%APPDATA%\Microsoft\Windows\Printer Shortcuts`                                       |
| Printers                 | `{76FC4E2D-D6AD-4519-A663-37BD56068185}` | `virtual folder`                                                                      |
| Program Files            | `{6D809377-6AF0-444B-8957-A3773F02200E}` | `%ProgramFiles% (%SystemDrive%\Program Files`)                                        |
| Program Files            | `{7C5A40EF-A0FB-4BFC-874A-C0F2E0B9FA8E}` | `%ProgramFiles% (%SystemDrive%\Program Files`)                                        |
| Program Files            | `{905E63B6-C1BF-494E-B29C-65B732D3D21A}` | `%ProgramFiles% (%SystemDrive%\Program Files`)                                        |
| ProgramData              | `{62AB5D82-FDC1-4DC3-A9DD-070D1D495D97}` | `%ALLUSERSPROFILE% (%ProgramData%, %SystemDrive%\ProgramData`)                        |
| Programs                 | `{0139D44E-6AFE-49F2-8690-3DAFCAE6FFB8}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs`                             |
| Programs                 | `{5CD7AEE2-2219-4A67-B85D-6C9CE15660CB}` | `%LOCALAPPDATA%\Programs`                                                             |
| Programs                 | `{A77F5D77-2E2B-44C3-A6A2-ABA601054A51}` | `%APPDATA%\Microsoft\Windows\Start Menu\Programs`                                     |
| Programs                 | `{BCBD3057-CA5C-4622-B42D-BC56DB0AE516}` | `%LOCALAPPDATA%\Programs\Common`                                                      |
| Programs and Features    | `{DF7266AC-9274-4867-8D55-3BD661DE872D}` | `Virtual folder`                                                                      |
| Public                   | `{DFDF76A2-C82A-4D63-906A-5644AC457385}` | `%PUBLIC% (%SystemDrive%\Users\Public`)                                               |
| Public Account Pictures  | `{0482AF6C-08F1-4C34-8C90-E17EC98B1E17}` | `%PUBLIC%\AccountPictures`                                                            |
| Public Desktop           | `{C4AA340D-F20F-4863-AFEF-F87EF2E6BA25}` | `%PUBLIC%\Desktop`                                                                    |
| Public Documents         | `{ED4824AF-DCE4-45A8-81E2-FC7965083634}` | `%PUBLIC%\Documents`                                                                  |
| Public Downloads         | `{3D644C9B-1FB8-4F30-9B45-F670235F79C0}` | `%PUBLIC%\Downloads`                                                                  |
| Public Music             | `{3214FAB5-9757-4298-BB61-92A9DEAA44FF}` | `%PUBLIC%\Music`                                                                      |
| Public Pictures          | `{B6EBFB86-6907-413C-9AF7-4FC2ABF07CC5}` | `%PUBLIC%\Pictures`                                                                   |
| Public Videos            | `{2400183A-6185-49FB-A2D8-4A392A602BA3}` | `%PUBLIC%\Videos`                                                                     |
| Quick Launch             | `{52A4F021-7B75-48A9-9F6B-4B87A210BC8F}` | `%APPDATA%\Microsoft\Internet Explorer\Quick Launch`                                  |
| Recent Items             | `{AE50C081-EBD2-438A-8655-8A092E34987A}` | `%APPDATA%\Microsoft\Windows\Recent`                                                  |
| Recorded TV              | `{1A6FDBA2-F42D-4358-A798-B74D745926C5}` | `%PUBLIC%\RecordedTV.library-ms`                                                      |
| Recycle Bin              | `{B7534046-3ECB-4C18-BE4E-64CD4CB7D6AC}` | `virtual folder`                                                                      |
| Resources                | `{8AD10C31-2ADB-4296-A8F7-E4701232C972}` | `%windir%\Resources`                                                                  |
| Ringtones                | `{C870044B-F49E-4126-A9C3-B52A1FF411E8}` | `%LOCALAPPDATA%\Microsoft\Windows\Ringtones`                                          |
| Ringtones                | `{E555AB60-153B-4D17-9F04-A5FE99FC15EC}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones`                                       |
| RoamedTileImages         | `{AAA8D5A5-F1D6-4259-BAA8-78E7EF60835E}` | `%LOCALAPPDATA%\Microsoft\Windows\RoamedTileImages`                                   |
| Roaming                  | `{3EB685DB-65F9-4CF6-A03A-E3EF65729F3D}` | `%APPDATA% (%USERPROFILE%\AppData\Roaming`)                                           |
| RoamingTiles             | `{00BCFC5A-ED94-4E48-96A1-3F6217F21990}` | `%LOCALAPPDATA%\Microsoft\Windows\RoamingTiles`                                       |
| Sample Music             | `{B250C668-F57D-4EE1-A63C-290EE7D1AA1F}` | `%PUBLIC%\Music\Sample Music`                                                         |
| Sample Pictures          | `{C4900540-2379-4C75-844B-64E6FAF8716B}` | `%PUBLIC%\Pictures\Sample Pictures`                                                   |
| Sample Playlists         | `{15CA69B3-30EE-49C1-ACE1-6B5EC372AFB5}` | `%PUBLIC%\Music\Sample Playlists`                                                     |
| Sample Videos            | `{859EAD94-2E85-48AD-A71A-0969CB56A6CD}` | `%PUBLIC%\Videos\Sample Videos`                                                       |
| Saved Games              | `{4C5C32FF-BB9D-43B0-B5B4-2D72E54EAAA4}` | `%USERPROFILE%\Saved Games`                                                           |
| Saved Pictures           | `{3B193882-D3AD-4EAB-965A-69829D1FB59F}` | `%USERPROFILE%\Pictures\Saved Pictures`                                               |
| Saved Pictures Library   | `{E25B5812-BE88-4BD9-94B0-29233477B6C3}` | `%APPDATE%\Microsoft\Windows\Libraries\SavedPictures.library-ms`                      |
| Screenshots              | `{B7BEDE81-DF94-4682-A7D8-57A52620B86F}` | `%USERPROFILE%\Pictures\Screenshots`                                                  |
| Search Results           | `{190337D1-B8CA-4121-A639-6D472D16972A}` | `virtual folder`                                                                      |
| Searches                 | `{7D1D3A04-DEBB-4115-95CF-2F29DA2920DA}` | `%USERPROFILE%\Searches`                                                              |
| SendTo                   | `{8983036C-27C0-404B-8F08-102D10DCFD74}` | `%APPDATA%\Microsoft\Windows\SendTo`                                                  |
| Slide Shows              | `{69D2CF90-FC33-4FB7-9A0C-EBB0F0FCB43C}` | `%USERPROFILE%\Pictures\Slide Shows`                                                  |
| Start Menu               | `{625B53C3-AB48-4EC1-BA1F-A1EF4146FC19}` | `%APPDATA%\Microsoft\Windows\Start Menu`                                              |
| Start Menu               | `{A4115719-D62E-491D-AA7C-E74B8BE3B067}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu`                                      |
| Startup                  | `{82A5EA35-D9CD-47C5-9629-E15D2F714E6E}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp`                     |
| Startup                  | `{B97D20BB-F46A-4C97-BA10-5E3608430854}` | `%APPDATA%\Microsoft\Windows\Start Menu\Programs\StartUp`                             |
| Sync Center              | `{43668BF8-C14E-49B2-97C9-747784D784B7}` | `virtual folder`                                                                      |
| Sync Results             | `{289A9A43-BE44-4057-A41B-587A76D7E7F9}` | `virtual folder`                                                                      |
| Sync Setup               | `{0F214138-B1D3-4A90-BBA9-27CBC0C5389A}` | `virtual folder`                                                                      |
| System32                 | `{1AC14E77-02E7-4E5D-B744-2EB1AE5198B7}` | `%windir%\system32`                                                                   |
| System32                 | `{D65231B0-B2F1-4857-A4CE-A8E7C6EA7D27}` | `%windir%\system32`                                                                   |
| Templates                | `{7E636BFE-DFA9-4D5E-B456-D7B39851D8A9}` | `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates`                          |
| Templates                | `{A63293E8-664E-48DB-A079-DF759E0509F7}` | `%APPDATA%\Microsoft\Windows\Templates`                                               |
| Templates                | `{B94237E7-57AC-4347-9151-B08C6C32D1F7}` | `%ALLUSERSPROFILE%\Microsoft\Windows\Templates`                                       |
| Temporary Burn Folder    | `{9E52AB10-F80D-49DF-ACB8-4330F5687855}` | `%LOCALAPPDATA%\Microsoft\Windows\Burn\Burn (?)`                                      |
| Temporary Internet Files | `{352481E8-33BE-4251-BA85-6007CAEDCF9D}` | `%LOCALAPPDATA%\Microsoft\Windows\Temporary Internet Files`                           |
| The Internet             | `{4D9F7874-4E0C-4904-967B-40B0D20C3E4B}` | `virtual folder`                                                                      |
| The user's full name     | `{F3CE0F7C-4901-4ACC-8648-D5D44B04EF8F}` | `virtual folder`                                                                      |
| User Pinned              | `{9E3995AB-1F9C-4F13-B827-48B24B6C7174}` | `%APPDATA%\Microsoft\Internet Explorer\Quick Launch\User Pinned`                      |
| Users                    | `{0762D272-C50A-4BB0-A382-697DCD729B80}` | `%SystemDrive%\Users`                                                                 |
| Videos                   | `{18989B1D-99B5-455B-841C-AB7C74E4DDFC}` | `%USERPROFILE%\Videos`                                                                |
| Videos                   | `{491E922F-5643-4AF4-A7EB-4E7A138D8174}` | `%APPDATA%\Microsoft\Windows\Libraries\Videos.library-ms`                             |
| Windows                  | `{F38BF404-1D43-42F2-9305-67DE0B28FC23}` | `%windir%`                                                                            |
| %USERNAME%               | `{5E6C858F-0E22-4760-9AFE-EA3317B67173}` | `%USERPROFILE% (%SystemDrive%\Users\%USERNAME%)`                                      |
| %USERNAME%               | `{9B74B6A3-0DFD-4F11-9E78-5F7800F2E772}` | `virtual folder`                                                                      |

## Sources

- 2021-08-13: [CLSID Key (GUID) Shortcuts List for Windows 10 - Tutorials](https://www.tenforums.com/tutorials/3123-clsid-key-guid-shortcuts-list-windows-10-a.html)
- 2021-08-13: [Windows 10 User Shell Folders Restore Default Paths - Winhelponline](https://www.winhelponline.com/blog/windows-10-shell-folders-paths-defaults-restore/)
- 2022-04-23: [Windows- known folders](https://renenyffenegger.ch/notes/Windows/dirs/_known-folders)