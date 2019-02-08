---
title: Nasazení prostředí VS
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70f39dd23851a2ebc0a48afd05da54b0d8deb24a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955671"
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