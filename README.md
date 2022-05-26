# htc_cponline_ie_setting_help

通过上古 ie only的 hta 技术来快速设置 电子申请网需求的设置选项

## 使用到的技术

[hta](https://docs.microsoft.com/zh-cn/previous-versions/ms536496(v=vs.85)) 

[~~vconsole~~](https://github.com/Tencent/vConsole "fetcch 不兼容ie系列")


## hta 兼容性


## 参考资料
[Internet Explorer高级用户的安全区域注册表项](https://docs.microsoft.com/zh-CN/troubleshoot/developer/browsers/security-privacy/ie-security-zones-registry-entries)

Value  Setting
----------------------------------------------------------------------------------
1001   ActiveX controls and plug-ins: Download signed ActiveX controls
1004   ActiveX controls and plug-ins: Download unsigned ActiveX controls
1200   ActiveX controls and plug-ins: Run ActiveX controls and plug-ins
1201   ActiveX controls and plug-ins: Initialize and script ActiveX controls not marked as safe for scripting
1206   Miscellaneous: Allow scripting of Internet Explorer Web browser control ^
1207   Reserved #
1208   ActiveX controls and plug-ins: Allow previously unused ActiveX controls to run without prompt ^
1209   ActiveX controls and plug-ins: Allow Scriptlets
120A   ActiveX controls and plug-ins: ActiveX controls and plug-ins: Override Per-Site (domain-based) ActiveX restrictions
120B   ActiveX controls and plug-ins: Override Per-Site (domain-based) ActiveX restrict ions
1400   Scripting: Active scripting
1402   Scripting: Scripting of Java applets
1405   ActiveX controls and plug-ins: Script ActiveX controls marked as safe for scripting
1406   Miscellaneous: Access data sources across domains
1407   Scripting: Allow Programmatic clipboard access
1408   Reserved #
1409   Scripting: Enable XSS Filter
1601   Miscellaneous: Submit non-encrypted form data
1604   Downloads: Font download
1605   Run Java #
1606   Miscellaneous: Userdata persistence ^
1607   Miscellaneous: Navigate sub-frames across different domains
1608   Miscellaneous: Allow META REFRESH * ^
1609   Miscellaneous: Display mixed content *
160A   Miscellaneous: Include local directory path when uploading files to a server ^
1800   Miscellaneous: Installation of desktop items
1802   Miscellaneous: Drag and drop or copy and paste files
1803   Downloads: File Download ^
1804   Miscellaneous: Launching programs and files in an IFRAME
1805   Launching programs and files in webview #
1806   Miscellaneous: Launching applications and unsafe files
1807   Reserved ** #
1808   Reserved ** #
1809   Miscellaneous: Use Pop-up Blocker ** ^
180A   Reserved #
180B   Reserved #
180C   Reserved #
180D   Reserved #
180E   Allow OpenSearch queries in Windows Explorer #
180F   Allow previewing and custom thumbnails of OpenSearch query results in Windows Explorer #
1A00   User Authentication: Logon
1A02   Allow persistent cookies that are stored on your computer #
1A03   Allow per-session cookies (not stored) #
1A04   Miscellaneous: Don't prompt for client certificate selection when no certificates or only one certificate exists * ^
1A05   Allow 3rd party persistent cookies *
1A06   Allow 3rd party session cookies *
1A10   Privacy Settings *
1C00   Java permissions #
1E05   Miscellaneous: Software channel permissions
1F00   Reserved ** #
2000   ActiveX controls and plug-ins: Binary and script behaviors
2001   .NET Framework-reliant components: Run components signed with Authenticode
2004   .NET Framework-reliant components: Run components not signed with Authenticode
2007   .NET Framework-Reliant Components: Permissions for Components with Manifests
2100   Miscellaneous: Open files based on content, not file extension ** ^
2101   Miscellaneous: Web sites in less privileged web content zone can navigate into this zone **
2102   Miscellaneous: Allow script initiated windows without size or position constraints ** ^
2103   Scripting: Allow status bar updates via script ^
2104   Miscellaneous: Allow websites to open windows without address or status bars ^
2105   Scripting: Allow websites to prompt for information using scripted windows ^
2200   Downloads: Automatic prompting for file downloads ** ^
2201   ActiveX controls and plug-ins: Automatic prompting for ActiveX controls ** ^
2300   Miscellaneous: Allow web pages to use restricted protocols for active content **
2301   Miscellaneous: Use Phishing Filter ^
2400   .NET Framework: XAML browser applications
2401   .NET Framework: XPS documents
2402   .NET Framework: Loose XAML
2500   Turn on Protected Mode [Vista only setting] #
2600   Enable .NET Framework setup ^
2702   ActiveX controls and plug-ins: Allow ActiveX Filtering
2708   Miscellaneous: Allow dragging of content between domains into the same window
2709   Miscellaneous: Allow dragging of content between domains into separate windows
270B   Miscellaneous: Render legacy filters
270C   ActiveX Controls and plug-ins: Run Antimalware software on ActiveX controls

       {AEBA21FA-782A-4A90-978D-B72164C80120} First Party Cookie *
       {A8A88C49-5EB2-4990-A1A2-0876022C854F} Third Party Cookie *

* indicates an Internet Explorer 6 or later setting
** indicates a Windows XP Service Pack 2 or later setting
# indicates a setting that is not displayed in the user interface in Internet Explorer
^ indicates a setting that only has two options, enabled or disabled


[面向高级用户的 Windows 注册表信息](https://docs.microsoft.com/zh-cn/troubleshoot/windows-server/performance/windows-registry-advanced-users)

### 明细
- 受信任的站点 添加 www.baidu.com

[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap\Domains\baidu.com]

[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap\Domains\baidu.com\www]
"*"=dword:00000002

- 禁用弹出警告
WshShell.RegWrite("HKCU//Software//Microsoft//Internet Explorer//New Windows//PopupMgr","no");

- 兼容性视图

Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\BrowserEmulation\ClearableListData]
"UserFilter"=hex:41,1f,00,00,53,08,ad,ba,01,00,00,00,36,00,00,00,01,00,00,00,\
  01,00,00,00,0c,00,00,00,e6,b3,ad,56,14,70,d8,01,01,00,00,00,0c,00,63,00,6e,\
  00,69,00,70,00,61,00,2e,00,67,00,6f,00,76,00,2e,00,63,00,6e,00

