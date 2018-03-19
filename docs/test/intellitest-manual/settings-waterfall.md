---
title: "Nastavení vodopádu | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs"
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: b771194924fbd7757a356b119aa693eb46b3a17b
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
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
