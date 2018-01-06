---
title: "Náhradní řetězce používány. Pkgdef a. Soubory Pkgundef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgdef and .pkgundef files
ms.assetid: b1755d63-d794-4fd7-864b-70a9684881c2
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0405e18419baf8bc152331a2bcfc7254ec602d1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="substitution-strings-used-in-pkgdef-and-pkgundef-files"></a>Náhradní řetězce používány. Pkgdef a. Pkgundef soubory
Můžete použít náhradní řetězce uvedené níže v .pkgdef a .pkgundef soubory, které definujete pro sadu Visual Studio izolované aplikace prostředí.  
  
## <a name="substitution-strings"></a>Náhradní řetězce  
  
|String|Popis|  
|------------|-----------------|  
|$=*RegistryEntry*$|Hodnota *RegistryEntry* položku. Pokud text položky registru končí na zpětné lomítko (\\), je použita výchozí hodnota podklíče registru. Například nahrazování řetězec $= HKEY_CURRENT_USER\Environment\TEMP$ je rozšířena do dočasné složky aktuálního uživatele.|  
|$AppName$|Kvalifikovaný název aplikace, která je předána AppEnv.dll vstupní body. Úplný název se skládá z názvu aplikace, podtržítko a objekt automatizace aplikace, které se taky zaznamená jako hodnota ThisVersionDTECLSID nastavení v souboru projektu .pkgdef identifikátor třídy (CLSID).|  
|$AppDataLocalFolder|Podsložky ve složce % LOCALAPPDATA % pro tuto aplikaci.|  
|$BaseInstallDir$|Úplná cesta k umístění, kam se nainstaloval Visual Studio.|  
|$CommonFiles$|Hodnota proměnné prostředí % CommonProgramFiles %.|  
|$MyDocuments$|Úplná cesta ke složce Dokumenty aktuálního uživatele.|  
|$PackageFolder$|Úplná cesta adresáře, který obsahuje soubory sestavení balíčku pro aplikaci.|  
|$ProgramFiles$|Hodnota proměnné prostředí % ProgramFiles %.|  
|$RootFolder$|Úplná cesta ke kořenovému adresáři aplikace.|  
|$RootKey$|Kořenový klíč registru pro aplikaci. Ve výchozím nastavení je kořenový adresář v HKEY_CURRENT_USER\Software\\*#companyname*\\*ProjectName*\\*Cisloverze* (když aplikace běží, připojí se k tento klíč _Config). Je nastavena podle hodnotě RegistryRoot v *název řešení SolutionName*.pkgdef souboru.<br /><br /> Řetězec $ $RootKey umožňuje načíst hodnotu registru v podklíči aplikace. Například řetězec "$= $RootKey$ \AppIcon$" vrátí hodnotu položky AppIcon v podklíči kořenové aplikace.<br /><br /> Analyzátor zpracovává soubor .pkgdef postupně a k přístup položky registru podklíče aplikace jenom v případě, že dříve definována položka|  
|$ShellFolder$|Úplná cesta k umístění, kam se nainstaloval Visual Studio.|  
|$System$|Složky Windows\system32.|  
|$WINDIR$|Složka systému Windows.|  
  
 Pokud analyzátor nerozpoznává náhradní řetězec, nebo ho nelze stanovit hodnotu položky registru nebo proměnná prostředí, pak neprovede nahrazení na část řetězce.