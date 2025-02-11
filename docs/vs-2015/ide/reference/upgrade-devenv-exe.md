---
title: -Upgradu (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b2ba3caf7931449e2c1657270838a45505fd5d92
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176932"
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Aktualizuje soubor řešení a všechny jeho soubory projektu nebo zadaný pro aktuální soubor projektu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] formáty pro tyto soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv SolutionFile | ProjectFile /upgrade  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionFile`  
 Povinné, pokud upgradujete celé řešení a jeho projekty. Cesta a název souboru řešení. Můžete zadat pouze název souboru řešení nebo úplnou cestu a název souboru řešení. Pokud složka nebo soubor s názvem ještě neexistuje, vytvoří se.  
  
 `ProjectFile`  
 Povinné, pokud upgradujete jeden projekt. Cesta a název souboru projektu v rámci řešení. Můžete zadat pouze název souboru projektu nebo úplnou cestu a název souboru projektu. Pokud složka nebo soubor s názvem ještě neexistuje, vytvoří se.  
  
## <a name="remarks"></a>Poznámky  
 Zálohy jsou automaticky vytvořeny a zkopírován do adresáře s názvem Zálohování, který je vytvořen v aktuálním adresáři.  
  
 Řešení se spravovanými zdroji nebo projekty musí být rezervován dříve, než je možné upgradovat.  
  
 Použití `/upgrade` přepínač nespustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Výsledky upgradu lze zobrazit v sestavě upgradu pro vývojový jazyk řešení nebo projektu. Vrátí se žádné informace o chybě nebo použití. Další informace o upgradu projektů v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], naleznete v tématu [jak: Řešení potíží s upgrady úspěšné sady Visual Studio projekt](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu upgraduje soubor řešení s názvem "MyProject.sln" ve výchozí složce pro [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] řešení.  
  
```  
devenv "MyProject.sln" /upgrade  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Řešení potíží s upgrady projektu úspěšné sady Visual Studio](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
