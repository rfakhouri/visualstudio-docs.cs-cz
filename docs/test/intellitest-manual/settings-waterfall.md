---
title: Vodopádové nastavení | Nástroj pro testování Microsoft IntelliTest Developer
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 966182ca79ffd06e17642e1b24d6e48b8e637efe
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55923718"
---
# <a name="settings-waterfall"></a>Vodopádové nastavení

Koncept vodopádové nastavení znamená, že uživatel může zadat nastavení na **sestavení**, **testovacího přípravku**, a **zkoumání** úroveň:

* Sestavení - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* Testovací přípravek - [PexClass](attribute-glossary.md#pexclass)
* Zkoumání - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

Zadaný v nastavení **sestavení** úroveň ovlivňují všechny komunikací a zkoumání v rámci tohoto sestavení. Zadaný v nastavení **testovacího přípravku** úroveň ovlivňují všechny průzkumů v rámci této testovací přípravek. Nastavení win podřízené&mdash;Pokud nastavení je definován na **sestavení** a **testovacího přípravku** úrovně, **testovacího přípravku** nastavení jsou použita.

Všimněte si, že některá nastavení jsou specifická pro **sestavení** úroveň nebo **testovacího přípravku** úroveň.

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

## <a name="got-feedback"></a>Máte nějakou zpětnou vazbu?

Publikovat své nápady a funkce na požadavky [komunity vývojářů](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).