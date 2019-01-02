---
title: Nasazení prostředí VS
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 2d732b050a9f12b6324abaf253739cd4f3e223aa
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53914485"
---
# <a name="vs-shell-deployment"></a>Nasazení prostředí VS

Izolované prostředí umožňuje určit, které Visual Studio funkce, je nutné pracovat s jazyka specifického pro doménu a jak by se měla zobrazit toto řešení. Další informace o prostředí sady Visual Studio, samostatný, naleznete v tématu [přizpůsobení izolovaného prostředí](https://vspartner.com/pages/vsshells).

Chcete-li nastavit Visual Studio Shell jako cíl nasazení:

1. V **DslPackage** projekt, otevřete **source.extension.tt**.

2. V části `<SupportedProducts>` vložit:

   ```xml
   <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
   ```

   Nahraďte *MyIsolatedShell* s názvem vašeho balíčku izolovaného prostředí.