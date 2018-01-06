---
title: "Nastavení vodopádu | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Settings waterfall
ms.assetid: 45777037-9E16-4ABF-BD26-5AF4E740D4E6
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: a56062f68fb0952d2b18726e1edecc26432e3fc3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="settings-waterfall"></a>Nastavení vodopádu

Koncept vodopádu nastavení znamená, že může uživatel zadat nastavení na **sestavení**, **přípojka** a **zkoumání** úroveň: 

* Sestavení – [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Přípojka - [PexClass](attribute-glossary.md#pexclass)
* Zkoumání - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

Nastavení zadané **sestavení** úroveň ovlivní všechny příslušenství a zkoumání v rámci této položky assembly. Nastavení zadané **přípojka** úroveň ovlivní všechny explorations v rámci této přípojka. Podřízené nastavení win: Pokud je nastavení definované v **sestavení** a **přípojka** úrovně, **přípojka** nastavení budou použita.

Všimněte si, že některá nastavení jsou specifické pro **sestavení** úroveň nebo **přípojka** úroveň. 

**Příklad**

```
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500 
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
