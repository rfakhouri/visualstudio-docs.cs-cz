---
title: "Správa přidružení souboru vedle sebe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- verbs, setting default
ms.assetid: 9b6df3bc-d15c-4a5d-9015-948a806193b7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7d0a6f8ec88a49b785b771aef51dc25b5646ffda
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="managing-side-by-side-file-associations"></a>Správa přidružení souboru vedle sebe
Pokud vaše VSPackage poskytuje přidružení souborů, musíte rozhodnout, jak zpracovat souběžně sdílená zařízení, ve které konkrétní verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] by měla být volána k otevření souboru. Formáty souborů nekompatibilní složené problém.  
  
 Uživatelé očekávají, že novou verzi produktu, aby byl kompatibilní s předchozími verzemi tak, aby existující soubory mohou být načteny v nové verzi, bez ztráty dat. V ideálním případě by vaše VSPackage můžete načíst i uložit formáty souborů starších verzí. Pokud není hodnota true, má nabízejí pro upgrade na novou verzi vaší VSPackage formát souboru. Nevýhodou tohoto přístupu je, že upgradovaný soubor nelze otevřít ve starší verzi.  
  
 K tomuto problému vyhnout, můžete změnit rozšíření, kdy k nekompatibilní formáty souborů. Například verze 1 vaší VSPackage může používat rozšíření, .mypkg10 a verze 2 může používat rozšíření, .mypkg20. Tento rozdíl identifikuje VSPackage, který se otevírá určitý soubor. Pokud přidáte do seznamu programů, které jsou přidružené původní příponě novější VSPackages, uživatelé pravým tlačítkem na soubor a vyberte jej otevřete v novější VSPackage. V tomto okamžiku můžete nabídnout soubor upgradovat na nový formát nebo otevřete soubor a zachování kompatibility s předchozími verzemi VSPackage vaší VSPackage.  
  
> [!NOTE]
>  Tato řešení můžete kombinovat. Můžete například nabízejí zpětnou kompatibilitu s načítání starší souboru a nabízejí upgradovat formát souboru, když uživatel uloží ho.  
  
## <a name="facing-the-problem"></a>Setkávají problém  
 Pokud chcete, aby více vedle sebe VSPackages použití stejné rozšíření, musíte zvolit verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je spojeno s příponou. Zde jsou dvě alternativy:  
  
-   Otevřete soubor v nejnovější verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nainstalovaný na počítači uživatele.  
  
     V tento přístup je zodpovědná za určení nejnovější verzi instalačním programem vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a který včetně položky registru, které jsou napsané pro přidružení souboru. V balíčku Instalační služby systému Windows, můžete zahrnout vlastní akce nastavit vlastnost, která určuje nejnovější verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
    > [!NOTE]
    >  V tomto kontextu "posledního" znamená "nejnovější podporovanou verzi." Tyto položky Instalační program automaticky nerozpozná následné verze služby [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Položky v [zjišťování požadavky na systém](../extensibility/internals/detecting-system-requirements.md) a v [příkazy, musí být spustit po instalaci](../extensibility/internals/commands-that-must-be-run-after-installation.md) jsou podobné těm, které jsou uvedeny v tomto tématu a jsou nezbytné k podpoře další verze nástroje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Nastavte následující řádky v tabulce CustomAction DEVENV_EXE_LATEST vlastnost, která má být vlastnost, která nastavuje AppSearch a RegLocator tabulky popisovaný v [příkazy, musí být spustit po instalaci](../extensibility/internals/commands-that-must-be-run-after-installation.md). Řádky v tabulce InstallExecuteSequence naplánovat vlastní akce již v rané fázi v pořadí spouštění. Hodnoty ve sloupci zkontrolujte podmínku logiku fungovat:  
  
    -   Visual Studio .NET 2002 je na nejnovější verzi, pokud se jedná pouze aktuální verze.  
  
    -   Visual Studio .NET 2003 je na nejnovější verzi, pouze pokud je k dispozici a [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] není k dispozici.  
  
    -   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Pokud se jedná pouze aktuální verze, je na nejnovější verzi.  
  
     Net výsledkem je, že DEVENV_EXE_LATEST obsahuje cestu nejnovější verzi devenv.exe.  
  
    ### <a name="customaction-table-rows-that-determine-the-latest-version-of-visual-studio"></a>CustomAction řádky tabulky, které určují nejnovější verze sady Visual Studio  
  
    |Akce|Typ|Zdroj|cíl|  
    |------------|----------|------------|------------|  
    |CA_SetDevenvLatest_2002|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2002]|  
    |CA_SetDevenvLatest_2003|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2003]|  
    |CA_SetDevenvLatest_2005|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2005]|  
  
    ### <a name="installexecutesequence-table-rows-that-determine-the-latest-version-of-visual-studio"></a>InstallExecuteSequence řádky tabulky, které určují nejnovější verze sady Visual Studio  
  
    |Akce|Podmínka|Pořadí|  
    |------------|---------------|--------------|  
    |CA_SetDevenvLatest_2002|DEVENV_EXE_2002 A NENÍ (DEVENV_EXE_2003 NEBO DEVENV_EXE_2005)|410|  
    |CA_SetDevenvLatest_2003|DEVENV_EXE_2003 A NENÍ DEVENV_EXE_2005|420|  
    |CA_SetDevenvLatest_2005|DEVENV_EXE_2005|430|  
  
     Můžete použít vlastnost DEVENV_EXE_LATEST v tabulce registru balíčku Instalační služby systému Windows k zápisu HKEY_CLASSES_ROOT*ProgId*ShellOpenCommand klíč výchozí hodnota [DEVENV_EXE_LATEST] "%1"  
  
-   Spusťte sdílené Spouštěče program, který nejlepší volbou z dostupných VSPackage verzí.  
  
     Vývojáři [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zvolili tento postup pro zpracování komplexní požadavky více formátů řešení a projektů, které jsou výsledkem mnoha verzí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. V tomto přístupu registraci programu Spouštěče jako obslužná rutina rozšíření. Spouštěč prozkoumá soubor a rozhodne, kterou verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a vaše VSPackage může zpracovávat tento konkrétní soubor. Například pokud uživatel otevře soubor, který byl naposledy uložen v konkrétní verzi vaší VSPackage, Spouštěč spustit tento VSPackage v odpovídající verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Kromě toho může uživatel nakonfigurovat Spouštěče vždy spouštět na nejnovější verzi. Spouštěče také může vyzvat uživatele k upgradu formát souboru. Pokud formát souboru obsahuje číslem verze, Spouštěč může informovat uživatele, pokud formát souboru je z na verzi, která je novější než jeden nebo více nainstalované VSPackages.  
  
     Spouštěč by měl být v komponentě Instalační služby systému Windows, která je sdílena s všechny verze vaší VSPackage. Tento proces zajišťuje, že nejnovější verze je vždy nainstalován a neodebere, dokud se všechny verze vaší VSPackage odinstalován. Tímto způsobem se zachovají přidružení souborů a další položky registru součásti Spouštěče i v případě, že jedna verze VSPackage se odinstaluje.  
  
## <a name="uninstall-and-file-associations"></a>Odinstalujte a přidružení souboru  
 Odinstalace VSPackage, který zapíše položky registru pro přidružení souboru odebere přidružení typu souboru. Proto že rozšíření má žádné přidružené programy. Instalační služba systému Windows "neobnoví" položky registru, které byly přidány při instalaci VSPackage. Tady jsou některé možnosti opravy přidružení souboru uživatele:  
  
-   Použijte sdílené Spouštěče výše popsané.  
  
-   Vyzvat uživatele k spuštění opravy verze VSPackage, který chce uživatel vlastní přidružení souboru.  
  
-   Zadejte samostatný spustitelný program, který přepíše položky odpovídající registru.  
  
-   Zadejte konfigurační možnosti stránky nebo dialogové okno pole, které umožňuje uživatelům zvolit přidružení souborů a uvolnění ztraceny přidružení. Vyzvat uživatele, aby ji spustit po odinstalaci.  
  
## <a name="see-also"></a>Viz také  
 [Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [Registrace operací pro přípony názvů souborů](../extensibility/registering-verbs-for-file-name-extensions.md)