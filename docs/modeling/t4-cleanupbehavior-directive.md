---
title: T4 CleanUpBehavior – direktiva
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 27df15c0b935ff4bae497940c095dba1598bc4c1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62964102"
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior – direktiva

Pro odstranění domény appDomain po zpracování textové šablony vložte následující řádek:

```
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>
```

Textové šablony jsou zpracovávány v doméně appDomain, která je oddělena od hostitelského procesu. Ve většině případů se po zpracování jedné textové šablony použije doména appdomain znovu ke zpracování další šablony. Pokud ale zadáte CleanupBehavior, doména appDomain se odstraní a další šablona se zpracuje pomocí nové domény appDomain.

Sice se zpomalí zpracování textu, ale může to být užitečné, protože tím zajistíte likvidaci prostředků.

Tato direktiva funguje pouze u hostitele sady Visual Studio.