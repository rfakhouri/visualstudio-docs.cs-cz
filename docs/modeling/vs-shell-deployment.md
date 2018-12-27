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
ms.technology: vs-ide-modeling
ms.openlocfilehash: 663e706dba9ec7b6479e3e9360ef8aa2d12b1400
ms.sourcegitcommit: 159ed9d4f56cdc1dff2fd19d9dffafe77e46cd4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/21/2018
ms.locfileid: "53739494"
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