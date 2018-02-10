---
title: "Nasazení prostředí VS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: eb5446c8c3090624f327c234a1b518dc1928b6c9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
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