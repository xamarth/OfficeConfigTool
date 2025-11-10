# Office Config Tool

## Intro

* A mostly automated script(s) to install Office Click-to-Run from an offline source without using Office Deployment Tool (setup.exe), which allow bypassing ODT restrictions

* Support installing Product Suites or Single Apps individually

* Support installing multiple languages separately or together

* Support configuration options like the ones available with ODT, including:  
- Source Path  
- Excluding Apps  
- Update Channel  
- Miscellaneous Options (Display Level, Updates Enabled, Eula, Pin Icons, App Shutdown, Auto Activate)

* Includes a proper workaround with working updates to install Office 2021/2019 on Windows 8.1 or Office 2019 on Windows 7

* There are two flavors available of the scripts:

- YAOCTRI - Volume  
install volume products for Office 2024/2021/2019, in addition to Microsoft 365 Enterprise (O365ProPlus) and Office Mondo 2016

- YAOCTRIR - Retail  
install retail products for Microsoft 365 or Office 2024/2021/2019/2016 Suites, in addition to Office 2024/2021/2019 Single Apps

* Each flavor consist of two command scripts:

- Configurator.cmd  
the main script which is used to select products and installation options  
it also creates configuration ini files, with the ability to start the installation at the end  

- Installer.cmd  
the secondary script which is only used to execute the installation, depending on the already created the configuration ini file

* Office LTSC is a branding for the volume licensing of Office 2024/2021

* Project and Visio products are not available for the following languages by design:  
bg-BG, et-EE, hr-HR, lt-LT, lv-LV, sr-Latn-RS, th-TH, hi-IN, id-ID, kk-KZ, MS-MY, vi-VN, en-GB, es-MX, fr-CA

* Office C2R source files are universal, and contain all possible products, any SKU can be installed from the same source  
https://learn.microsoft.com/microsoft-365/troubleshoot/installation/product-ids-supported-office-deployment-click-to-run

* If you are using Office C2R for the first time or you are confused with the different products, the most recommended choices are:  
Product: Microsoft 365 Enterprise  
Channel: Current / Monthly

______________________________

## How To

* Run YAOCTRI_Configurator.cmd or YAOCTRIR_Configurator.cmd as administrator and follow the prompts

- For each menu, press the corresponding number or letter beside an option to change its state or proceed

- To exit at any menu press X (Version/Arch/Lang/Type menus have no return option, only proceed or exit)

- At first, enter the path for Office offline source

either the drive, directory or network share that contain "Office" folder (not Office folder path itself)

Configurator.cmd will auto detect the path for the drive letter of Office .img file (virtual mounted / dvd / usb)

if Configurator.cmd is placed inside "Office" folder, the path will be auto-detected

if Configurator.cmd is placed next to "Office" folder, the path will be auto-detected

- If multiple versions are detected in the source, you will be prompted to choose one

- If the current OS is x64, and multi-architecture Office 64-bit/32-bit is detected, you will be prompted to choose one

- If multiple languages are detected in the specified version, you will be prompted to choose one, or all

- If you chose all languages, you will be prompted to choose the primary language  
(which determines the setup and Office Shell UI culture, including shortcuts, right-click context menus, and tooltips)

- Select the installation type: complete product suites, or single apps separately

- If you selected a product suite, you will get a menu to exclude (turn OFF) unneeded apps

- Select the desired Update Channel

- Change the Miscellaneous Options to your needs

- In the end, you will have three options:

1. Install Now  
start normal installation now with the selected options (Config ini will be created too)

2. Create setup configuration (Normal Install)  
create Config ini file, to be used later with Installer.cmd

3. Create setup configuration (Auto Install)  
create Config ini file with the unattended option, which allow Installer.cmd to start the installation immediately


SKU ID                 | Old Name                  | New Name  
---------------------- | ------------------------- | -------------------------------  
O365ProPlusRetail      | Office 365 ProPlus        | Microsoft 365 Enterprise  
O365BusinessRetail     | Office 365 Business       | Microsoft 365 Business  
O365SmallBusPremRetail | Office 365 Small Business | Microsoft 365 Small Business  
O365HomePremRetail     | Office 365 Home           | Microsoft 365 Family  
O365EduCloudRetail     | Office 365 Education      | Microsoft 365 Education

---