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
ms.openlocfilehash: 6503efd0fa606042089e26b4cac23adcabdcb6e7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041013"
---
# <a name="vs-shell-deployment"></a>Nasazení prostředí VS
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Izolované prostředí umožňuje určit, které Visual Studio funkce, je nutné pracovat s jazyka specifického pro doménu a jak by se měla zobrazit toto řešení. Další informace o prostředí sady Visual Studio, samostatný, naleznete v tématu [přizpůsobení izolovaného prostředí](../extensibility/customizing-the-isolated-shell.md). Můžete najít další informace o tom, jak přizpůsobit izolovaného prostředí v [přizpůsobení izolovaného prostředí](http://msdn.microsoft.com/d75463cd-1155-42e4-8b7a-046ed6becbbf).  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>Chcete-li nastavit Visual Studio Shell jako cíle nasazení  
  
1. V **DslPackage** projekt, otevřete **source.extension.tt**.  
  
2. V části `<SupportedProducts>` vložit:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     Nahraďte *MyIsolatedShell* s názvem vašeho balíčku izolovaného prostředí.
