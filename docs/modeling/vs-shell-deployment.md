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
ms.openlocfilehash: cbd972609f06f9ce7d3a7745b33b8d0d78dcad2e
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="vs-shell-deployment"></a>Nasazení prostředí VS
Izolované prostředí umožňuje určit, které Visual Studio funkci, budete muset komunikovat s jazyka specifické pro doménu a jak by se měla objevit toto řešení. Další informace o prostředí sady Visual Studio izolované najdete v tématu [přizpůsobení izolované prostředí](../extensibility/customizing-the-isolated-shell.md). Můžete najít další informace o tom, jak přizpůsobit izolované prostředí v [přizpůsobení izolované prostředí](http://msdn.microsoft.com/en-us/d75463cd-1155-42e4-8b7a-046ed6becbbf).  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Chcete-li nastavit jako cíl nasazení prostředí Visual Studio  
  
1.  V **DslPackage** projekt, otevřete **source.extension.tt**.  
  
2.  V části `<SupportedProducts>` vložit:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     Nahraďte *MyIsolatedShell* s názvem vašeho balíčku izolované prostředí.