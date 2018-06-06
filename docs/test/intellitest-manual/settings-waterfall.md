---
title: Nastavení vodopádu | Nástroj pro testování Microsoft IntelliTest Developer
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ec6364b3d130ab3ca333838c7e1b6eb2fdcb4a3d
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815048"
---
# <a name="settings-waterfall"></a>Vodopádové nastavení

Koncept vodopádu nastavení znamená, že může uživatel zadat nastavení na **sestavení**, **přípojka**, a **zkoumání** úroveň:

* Sestavení – [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Přípojka - [PexClass](attribute-glossary.md#pexclass)
* Zkoumání - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

Nastavení zadané **sestavení** úroveň vliv na všechny příslušenství a zkoumání v rámci této položky assembly. Zadaný v nastavení **přípojka** úroveň vliv na všechny explorations v rámci této přípojka. Podřízené nastavení win&mdash;Pokud je nastavení definované v **sestavení** a **přípojka** úrovně, **přípojka** nastavení se používá.

Všimněte si, že některá nastavení jsou specifické pro **sestavení** úroveň nebo **přípojka** úroveň.

**Příklad**

```csharp
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

Vystavení vašich nápadů a funkce požadavky na [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest).
