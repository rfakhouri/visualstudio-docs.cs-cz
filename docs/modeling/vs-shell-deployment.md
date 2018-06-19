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
ms.openlocfilehash: e7df1991832e954def71a6cee5bd5516dfd4e961
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31946985"
---
# <a name="vs-shell-deployment"></a>Nasazení prostředí VS

Izolované prostředí umožňuje určit, které Visual Studio funkci, budete muset komunikovat s jazyka specifické pro doménu a jak by se měla objevit toto řešení. Další informace o prostředí sady Visual Studio izolované najdete v tématu [přizpůsobení izolované prostředí](../extensibility/customizing-the-isolated-shell.md).

## <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Chcete-li nastavit jako cíl nasazení prostředí Visual Studio

1.  V **DslPackage** projekt, otevřete **source.extension.tt**.

2.  V části `<SupportedProducts>` vložit:

    ```
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
    ```

     Nahraďte *MyIsolatedShell* s názvem vašeho balíčku izolované prostředí.