---
title: Náhradní řetězce použité v. Pkgdef a. Soubory Pkgundef | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode%2C .pkgdef and .pkgundef files
ms.assetid: b1755d63-d794-4fd7-864b-70a9684881c2
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24996e4e32ab86af46fce5280947719f906ffc3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675659"
---
# <a name="substitution-strings-used-in-pkgdef-and-pkgundef-files"></a>Náhradní řetězce použité v. Pkgdef a. Soubory Pkgundef
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [náhradní řetězce použité v. Pkgdef a. Soubory Pkgundef](https://docs.microsoft.com/visualstudio/extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files).  
  
Lze použít náhradní řetězce, uvedené níže v .pkgdef a .pkgundef soubory, které definujete pro Visual Studio izolované prostředí aplikace.  
  
## <a name="substitution-strings"></a>Náhradní řetězce  
  
|String|Popis|  
|------------|-----------------|  
|$=*RegistryEntry*$|Hodnota *RegistryEntry* položka. Pokud řetězec položky registru končí lomítkem (\\), pak je použita výchozí hodnota podklíče registru. Například řetězec nahrazení $= HKEY_CURRENT_USER\Environment\TEMP$ rozbalen do dočasné složky aktuálního uživatele.|  
|$AppName$|Kvalifikovaný název aplikace, který je předán AppEnv.dll vstupní body. Úplný název se skládá z názvu aplikace, podtržítka a identifikátor třídy (CLSID) objektu automatizace aplikace, která je také zaznamenána jako hodnota ThisVersionDTECLSID nastavení v souboru .pkgdef projektu.|  
|$AppDataLocalFolder|Podsložky ve složce % LOCALAPPDATA % pro tuto aplikaci.|  
|$BaseInstallDir$|Úplná cesta k umístění, kam byla nainstalována aplikace Visual Studio.|  
|$CommonFiles$|Hodnota proměnné prostředí % CommonProgramFiles %.|  
|$MyDocuments$|Úplná cesta složky Dokumenty aktuálního uživatele.|  
|$PackageFolder$|Úplná cesta adresáře, který obsahuje soubory sestavení balíčku aplikace.|  
|$ProgramFiles$|Hodnota proměnné prostředí % ProgramFiles %.|  
|$RootFolder$|Úplná cesta ke kořenovému adresáři aplikace.|  
|$RootKey$|Kořenový klíč registru pro aplikaci. Ve výchozím nastavení je kořenový adresář v HKEY_CURRENT_USER\Software\\*CompanyName*\\*ProjectName*\\*číslo_verze* (když aplikace běží, _Config se připojí k tomuto klíči). Je nastavena hodnota RegistryRoot v *SolutionName*soubor .pkgdef.<br /><br /> Řetězec $ $RootKey je možné načíst hodnotu registru pod podklíčem aplikace. Například řetězec "$$RootKey \AppIcon$ =" vrátí hodnotu položky AppIcon podklíči kořenové aplikace.<br /><br /> Analyzátor postupně zpracovává soubor .pkgdef a položky registru v podklíči aplikace můžete přistupovat, pouze v případě, že byla dříve definována položka|  
|$ShellFolder$|Úplná cesta k umístění, kam byla nainstalována aplikace Visual Studio.|  
|$System$|Složky Windows\system32.|  
|$WINDIR$|Složka Windows.|  
  
 Pokud analyzátor nerozpozná náhradní řetězec nebo nemůže určit hodnotu položky registru nebo proměnné prostředí, pak neprovede nahrazení na tuto část řetězce.

