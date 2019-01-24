---
title: Nasazení prostředí VS | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6c79a8a0558594e8981959750ebd348b6f9f4d60
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54773453"
---
# <a name="vs-shell-deployment"></a>Nasazení prostředí VS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Izolované prostředí umožňuje určit, které Visual Studio funkce, je nutné pracovat s jazyka specifického pro doménu a jak by se měla zobrazit toto řešení. Další informace o prostředí sady Visual Studio, samostatný, naleznete v tématu [přizpůsobení izolovaného prostředí](../extensibility/customizing-the-isolated-shell.md). Můžete najít další informace o tom, jak přizpůsobit izolovaného prostředí v [přizpůsobení izolovaného prostředí](http://msdn.microsoft.com/d75463cd-1155-42e4-8b7a-046ed6becbbf).  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Chcete-li nastavit Visual Studio Shell jako cíle nasazení  
  
1.  V **DslPackage** projekt, otevřete **source.extension.tt**.  
  
2.  V části `<SupportedProducts>` vložit:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     Nahraďte *MyIsolatedShell* s názvem vašeho balíčku izolovaného prostředí.
