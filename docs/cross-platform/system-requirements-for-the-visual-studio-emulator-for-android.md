---
title: "Systémové požadavky pro emulátor sady Visual Studio pro Android | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35e766ad-269f-41e4-ba23-74a556c315f3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 469a8298122abdc96c69f13ed96a893b02575fc9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="system-requirements-for-the-visual-studio-emulator-for-android"></a>Systémové požadavky pro emulátor sady Visual Studio pro Android
Visual Studio Emulator for Android běží jako virtuální počítač s technologií Hyper-V, technologie virtualizace pro Windows 8 a novější verze. Pokud chcete spustit v emulátoru, počítač musí splňovat požadavky na spuštění technologie Hyper-V, jak je popsáno v tomto tématu.  
  
 Instalační program se pokusí bezobslužně konfigurovat tyto požadavky pro vás při instalaci emulátor. Pokud instalační program úspěšně konfiguruje požadavky, emulátoru jednoduše funguje podle očekávání. V opačném případě budete muset ručně povolit tyto požadavky. Pokud budete muset ručně konfigurovat požadavky, kroky a nástrojů se o tytéž kroky popsané [sem](https://msdn.microsoft.com/en-us/library/windows/apps/jj863509\(v=vs.105\).aspx) pro emulátor Windows Phone.  
  
> [!IMPORTANT]
>  Instalační program pro emulátor zkontroluje požadavky pro spuštění Visual Studio Emulator for Android. Pokud požadavky nejsou k dispozici, ale nevyžaduje je zobrazí upozornění.  
  
 Toto téma obsahuje následující části.  
  
-   [Rychlé kontrolní seznam](#Checklist)  
  
-   [Požadavky na systém](#System)  
  
-   [Požadavky sítě](#Network)  
  
-   [Požadavky technologie Hyper-V](#HyperV)  
  
-   [Spuštění emulátor ze spouštěcí virtuální pevný disk není podporováno](#BootableVHD)  
  
-   [Technologie Hyper-V vyžaduje nešifrované a nekomprimované soubory](#Files)  
  
##  <a name="Checklist"></a>Rychlé kontrolní seznam  
 Zde je rychlé kontrolní seznam požadavky na spuštění emulátor sady Visual Studio pro Android. Podrobnější informace najdete v tématu v dalších částech tohoto tématu.  
  
 Požadavky na systém  
  
-   Podpora technologie Hyper-V (viz níže uvedené požadavky technologie Hyper-V)  
  
-   6 GB nebo více paměti RAM.  
  
-   64bitová verze Pro verzi systému Windows 8, Windows 8.1, Windows10 nebo vyšší  
  
-   Procesor, který podporuje SSSE3 nebo novější.  
  
 Požadavky sítě  
  
-   DHCP  
  
-   Automaticky konfigurované DNS a nastavení brány  
  
 Požadavky technologie Hyper-V  
  
-   V systému BIOS musí být podporovány následující funkce:  
  
    -   Hardwarovou podporu virtualizace  
  
    -   Druhý překlad adres úrovně (SLAT)  
  
    -   Zabránění spuštění dat založené na hardwaru (DEP)  
  
-   V systému Windows technologie Hyper-V musí být povolené a spuštěné.  
  
-   Musíte být členem místní skupiny Správci Hyper-V.  
  
##  <a name="System"></a>Požadavky na systém  
 Počítač musí splňovat následující požadavky:  
  
-   Podpora technologie Hyper-V (viz [požadavky technologie Hyper-V](#HyperV))  
  
-   6 GB nebo více paměti RAM.  
  
-   64bitové verze Pro verzi systému Windows 8, Windows 8.1, Windows10 nebo vyšší.  
  
 Zkontrolujte požadavky pro paměti RAM a systému Windows v Ovládacích panelech, zvolte systém a zabezpečení a potom zvolte systému.  
  
 ![Ověřte požadavky na systém](../cross-platform/media/android_emu_system_requirements.png "Android_Emu_System_Requirements")  
  
##  <a name="Network"></a>Požadavky sítě  
 Musí vaše síť splňovat následující požadavky:  
  
-   DHCP  
  
     Emulátor vyžaduje DHCP, protože se konfiguruje jako samostatné zařízení v síti s vlastní IP adresu.  
  
-   Automaticky konfigurované DNS a nastavení brány  
  
     Není možné nakonfigurovat nastavení DNS a brány pro emulátor serveru ručně.  
  
 Chcete-li problémů se sítí v emulátoru, najdete v následujících tématech:  
  
-   [Řešení potíží s emulátor sady Visual Studio pro Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)  
  
##  <a name="HyperV"></a>Požadavky technologie Hyper-V  
 Požadavky technologie Hyper-V v systému BIOS  
  
 Systém BIOS počítače musí podporovat následující požadavky, a musí být povolena:  
  
-   Hardwarovou podporu virtualizace  
  
-   Druhý překlad adres úrovně (SLAT)  
  
-   Zabránění spuštění dat založené na hardwaru (DEP)  
  
 Požadavky technologie Hyper-V v systému Windows  
  
 Pokud vaše počítače a nastavení systému BIOS jsou již nakonfigurována pro podporu technologie Hyper-V, instalační program povolí a spustí technologie Hyper-V. V opačném případě budete muset ručně povolit tyto požadavky.  
  
|Požadavek|Jak zkontrolovat a povolit tento požadavek|  
|-----------------|----------------------------------------------|  
|Musí být nainstalována technologie Hyper-V|Postupujte podle stejných pokynů používá k [povolení technologie Hyper-V pro Windows Phone emulátor](https://msdn.microsoft.com/en-us/library/windows/apps/jj863509\(v=vs.105\).aspx).<br /><br /> Zkontrolujte stav **technologie Hyper-V Virtual Machine Management** službu v modulu snap-in služby.|  
|Technologie Hyper-V musí být spuštěna.|Další informace o správě služeb naleznete v následujících tématech:<br /><br /> -   [Spustit, zastavit, pozastavit, obnovit nebo restartovat službu](https://technet.microsoft.com/library/cc736564\(v=WS.10\).aspx)<br />-   [Konfigurace spuštění služby](https://technet.microsoft.com/%20library/cc739213\(v=ws.10\))|  
  
 Musíte být členem místní skupiny Správci Hyper-V.  
  
 Pokud chcete spustit emulátor sady Visual Studio pro Android bez opakování výzva ke zvýšení oprávnění vaše práva, musíte být členem místní skupiny Správci Hyper-V. Pokud jste již oprávnění místního správce na počítači při instalaci sady SDK, instalační program sady SDK je přidá do skupiny Administrators technologie Hyper-V. V opačném případě budete muset ručně povolit tento požadavek.  
  
 Když spustíte emulátoru, pokud jste ještě nejsou členem skupiny Správci Hyper-V, budete vyzváni k zapojení do skupiny (dialogové okno odkazuje na emulátoru Windows Phone). Připojení skupiny vyžaduje oprávnění správce.  
  
> [!IMPORTANT]
>  Po připojení k skupině, odhlášení nebo počítač restartovat, aby se změna projeví.  
  
 ![Připojení technologie Hyper & č. 45; Skupiny zabezpečení Správci V](../cross-platform/media/android_emu_hyperv_admin.png "Android_Emu_HyperV_Admin")  
  
 Chcete-li sami ručně přidat do skupiny, otevřete místní uživatelé a skupiny modulu snap-in. Další informace najdete v tématu [přidání uživatelského účtu do skupiny](http://windows.microsoft.com/en-us/windows/add-user-account-to-group#1TC=windows-7). (V tomto tématu Windows 7 platí i pro Windows 8.)  
  
##  <a name="BootableVHD"></a>Spuštění emulátor ze spouštěcí virtuální pevný disk není podporováno  
 Pokud se pokusíte spustit aplikaci na emulátor sady Visual Studio pro Android, při spuštění systému Windows ze spouštěcího disku VHD, emulátoru obvykle trvá několik minut, spustit nebo nepodaří spustit. Když na emulátoru se nepodaří spustit, zobrazí se následující zpráva: nasazení aplikace se nezdařilo. Zkuste to prosím znovu.  
  
 Tato konfigurace není podporována. Informace o problémech souvisejících s najdete v tématu [řešení potíží s Visual Studio Emulator for Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md).  
  
##  <a name="Files"></a>Technologie Hyper-V vyžaduje nešifrované a nekomprimované soubory  
 Na pevném disku nakonfigurovaný pomocí systému souborů NTFS musí být nekomprimovaným soubory virtuálního pevného disku, používá technologie Hyper-V a bez šifrování. Ujistěte se, že nejsou komprimované nebo zašifrované následující adresáře:  
  
-   %localappdata%\Microsoft\XDE  
  
-   Správce emulátorů \Microsoft soubory (x86) C:\Program  
  
-   C:\Program soubory (x86) \Microsoft Visual Studio Emulator pro Android  
  
-   %localappdata%\Microsoft\VisualStudioEmulator  
  
 V systému souborů ReFS nesmí mít soubory virtuálního pevného disku sadu integrity bitů.  
  
## <a name="hardware-graphics-forwarding-opengl-es-support-requirements"></a>Požadavky na hardware grafiky předávání (podpora OpenGL ES)  
 V pořadí pro emulátor emulovat volání na grafický procesor, jako jsou ty používané OpenGL ES musí mít váš počítač DirectX kompatibilním grafickým Procesorem s odpovídající ovladače DirectX, které jsou nainstalované.  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s emulátor sady Visual Studio pro Android](../cross-platform/troubleshooting-the-visual-studio-emulator-for-android.md)