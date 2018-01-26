---
title: "Nasazení prostředí VS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 26b5075c36b152ecc44d65428521e191e6053609
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
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