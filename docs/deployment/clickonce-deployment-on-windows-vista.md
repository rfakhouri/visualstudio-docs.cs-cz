---
title: ClickOnce – nasazení v systému Windows Vista | Dokumentace Microsoftu
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4beefddd429384fadda71d9742e8c0fac606c38e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62900499"
---
# <a name="clickonce-deployment-on-windows-vista"></a>ClickOnce – nasazení v systému Windows Vista

Vytváření aplikací v sadě Visual Studio pro řízení uživatelských účtů (UAC) v systému Windows Vista obvykle generuje vloženého manifestu kódovaný jako binární data XML do spustitelného souboru aplikace.  ClickOnce a modelu COM bez registrace aplikace nebudou potřebovat manifest externí, Visual Studio generuje soubor pro tyto projekty obsahující data nástroje Řízení uživatelských účtů místo vloženého manifestu. Pro nasazení ClickOnce a modelu COM bez registrace, Visual Studio používá informace ze souboru s názvem *app.manifest* externí nástroje Řízení uživatelských účtů ke generování manifestu informace. U všech ostatních případech sady Visual Studio vloží data nástroje Řízení uživatelských účtů ve spustitelném souboru aplikace.

Visual Studio poskytuje následující možnosti pro generování manifestu:

- Použití vloženého manifestu. Vložit data nástroje Řízení uživatelských účtů ve spustitelném souboru aplikace a spusťte v režimu normálního uživatele.

   Toto je výchozí nastavení (Pokud nechcete použít ClickOnce). Toto nastavení podporuje obvyklým způsobem, ve kterém aplikace Visual Studio pracuje v systému Windows Vista, s generování interní a externí manifest pomocí `AsInvoker`.

- Použijte externí manifest. Generovat manifest externí pomocí *app.manifest*.

   Tím se vygeneruje pouze externím manifestem podle informací uvedených v *app.manifest*. Při publikování aplikace pomocí technologie ClickOnce nebo COM bez registrace, sada Visual Studio přidá *app.manifest* do projektu a pak přidá tuto možnost.

- Použít žádný manifest. Vytvořte aplikaci bez manifestu.

   Tento přístup se také označuje jako *virtualizace*. Tuto možnost použijte, pokud z důvodu kompatibility se stávajícími aplikacemi z předchozích verzí sady Visual Studio.

  Nové vlastnosti jsou k dispozici na **aplikace** stránky Návrháře projektu (Visual C# pouze pro projekty) a ve formátu souboru projektu MSBuild.

  Metoda konfigurace generování manifestu nástroje Řízení uživatelských účtů v integrovaném vývojovém prostředí sady Visual Studio se liší v závislosti na typu projektu (Visual C# nebo Visual Basic).

  * Informace o konfiguraci nástroje pro generování manifestu projekty Visual C# najdete v tématu [stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md).

  * Informace o konfiguraci projektů jazyka Visual Basic pro generování manifestu naleznete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md).

## <a name="see-also"></a>Viz také:
- [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)
- [Uživatelská oprávnění a sada Visual Studio](https://msdn.microsoft.com/library/d5c55084-1e7b-4b61-b478-137db01c0fc0)
- [Stránka Aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)