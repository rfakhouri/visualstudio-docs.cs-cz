---
title: ClickOnce – nasazení v systému Windows Vista | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- UAC manifest generation
- ClickOnce deployment, Windows
- manifest generation
- Windows, ClickOnce deployment
ms.assetid: b21a0ebc-0ff6-4f49-8993-7d1ad3f8cac2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c546d7e4287fc47a3770baa306a43a1631be2f06
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31558929"
---
# <a name="clickonce-deployment-on-windows-vista"></a>Implementace ClickOnce v systému Windows Vista
Vytváření aplikací v sadě Visual Studio pro řízení uživatelských účtů (UAC) v systému Windows Vista obvykle generuje manifest vložená data kódovaná v řetězci jako binární soubor XML ve spustitelném souboru aplikace. Vzhledem k tomu, že aplikace ClickOnce a COM bez registrace vyžadují externí manifest, Visual Studio generuje soubor pro tyto typy projektů, které obsahují místo vložený manifest dat nástroje Řízení uživatelských účtů. Ve výchozím nastavení Visual Studio používá informace ze souboru s názvem app.manifest ke generování manifestu informace externí nástroje Řízení uživatelských účtů (pro nasazení ClickOnce a COM bez registrace) nebo pro vložení do aplikace spustitelný soubor (u všech ostatních případech). Visual Studio poskytuje následující možnosti pro generování manifestu:  
  
-   Použijte vložený manifest. Vložit data nástroje Řízení uživatelských účtů ve spustitelném souboru aplikace a spustit jako normální.  
  
     Toto je výchozí nastavení (Pokud používáte ClickOnce). Toto nastavení bude podporovat obvyklým způsobem, ve kterém Visual Studio funguje v systému Windows Vista; To znamená, generování interních a externích manifestu pomocí `AsInvoker`.  
  
-   Použijte externí manifest. Generování manifestu externí pomocí app.manifest.  
  
     Tím se vytvoří pouze externí manifest pomocí informací v app.manifest. Při publikování aplikace pomocí ClickOnce nebo COM bez registrace, Visual Studio přidá app.manifest do projektu a přidá tuto možnost.  
  
-   Použijte žádný manifest. Vytvořte aplikaci bez manifestu.  
  
     Tento přístup je také označován jako *virtualizace*. Tuto možnost použijte pro kompatibilitě se stávajícími aplikacemi z dřívějších verzí sady Visual Studio.  
  
 Nové vlastnosti jsou k dispozici na **aplikace** stránky Návrhář projektu (Visual C# pouze pro projekty) a ve formátu souboru projektu nástroje MSBuild.  
  
 Všimněte si, že metoda pro konfiguraci UAC – generování manifestu v integrovaném vývojovém prostředí sady Visual Studio se liší v závislosti na typu projektu (Visual C# a Visual Basic).  
  
 Informace o konfiguraci projekty Visual C# pro generování manifestu najdete v tématu [stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md).  
  
 Informace o konfiguraci projekty Visual Basic pro generování manifestu najdete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Oprávnění uživatele a Visual Studio](http://msdn.microsoft.com/en-us/d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)