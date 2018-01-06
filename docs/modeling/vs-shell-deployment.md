---
title: "Nasazení prostředí VS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: aeb4ca2153d4c060862d31e53202312f061bf1ef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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