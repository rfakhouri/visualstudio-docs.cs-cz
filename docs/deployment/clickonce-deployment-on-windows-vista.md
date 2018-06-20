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
ms.openlocfilehash: 81bd18d10b91f06636ad6bba8230ec29b0d81312
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36235151"
---
# <a name="clickonce-deployment-on-windows-vista"></a>ClickOnce – nasazení v systému Windows Vista

Vytváření aplikací v sadě Visual Studio pro řízení uživatelských účtů (UAC) v systému Windows Vista obvykle generuje manifest vložená data kódovaná v řetězci jako binární soubor XML ve spustitelném souboru aplikace.  Aplikace ClickOnce a COM bez registrace potřebovat manifest externí, Visual Studio vytvoří soubor pro tyto projekty obsahující místo vložený manifest dat nástroje Řízení uživatelských účtů. Pro nasazení ClickOnce a COM bez registrace Visual Studio používá informace ze souboru s názvem app.manifest ke generování manifestu informací o externí nástroje Řízení uživatelských účtů. Visual Studio všech ostatních případech vloží data nástroje Řízení uživatelských účtů ve spustitelném souboru aplikace. 

Visual Studio poskytuje následující možnosti pro generování manifestu:  
  
-   Použijte vložený manifest. Vložit data nástroje Řízení uživatelských účtů ve spustitelném souboru aplikace a spustit jako normální uživatelské.  
  
     Toto je výchozí nastavení (Pokud používáte ClickOnce). Toto nastavení podporuje obvyklým způsobem, ve kterém Visual Studio funguje v systému Windows Vista, s generování interní i externí manifest pomocí `AsInvoker`.  
  
-   Použijte externí manifest. Generování manifestu externí pomocí app.manifest.  
  
     Tím se vytvoří pouze externí manifest pomocí informací v app.manifest. Při publikování aplikace pomocí ClickOnce nebo COM bez registrace, Visual Studio přidá app.manifest do projektu a potom přidá tuto možnost.  
  
-   Použijte žádný manifest. Vytvořte aplikaci bez manifestu.  
  
     Tento přístup je také označován jako *virtualizace*. Tuto možnost použijte pro kompatibilitě se stávajícími aplikacemi z dřívějších verzí sady Visual Studio.  
  
 Nové vlastnosti jsou k dispozici na **aplikace** stránky Návrhář projektu (Visual C# pouze pro projekty) a ve formátu souboru projektu nástroje MSBuild.  
  
 Metoda pro konfiguraci UAC – generování manifestu v integrovaném vývojovém prostředí sady Visual Studio se liší v závislosti na typu projektu (Visual C# nebo Visual Basic).  
  
   * Informace o konfiguraci projekty Visual C# pro generování manifestu najdete v tématu [stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md).  
  
   * Informace o konfiguraci projekty Visual Basic pro generování manifestu najdete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Oprávnění uživatele a Visual Studio](http://msdn.microsoft.com/en-us/d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)