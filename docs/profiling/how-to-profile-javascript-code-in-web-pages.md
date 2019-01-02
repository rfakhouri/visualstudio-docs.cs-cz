---
title: 'Postupy: Profilování kódu JavaScript ve webových stránkách | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- JavaScript performance profiling
- Profiling Tools,JavaScript
- web site performance profiling
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc3c83e81608d671db8bad655c4853e5262ea467
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53863635"
---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>Postupy: Profilování kódu JavaScript ve webových stránkách

Visual Studio Tools profilace můžete shromažďovat údaje o výkonu pro kód jazyka JavaScript, který se spustí v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, libovolná webová stránka nebo JavaScript aplikace s použitím metoda profilace instrumentace. Vyžaduje aplikaci Internet Explorer 8 nebo novější.

> [!WARNING]
> Chcete-li Profilovat jazyk JavaScript v aplikacích pro UPW, přečtěte si téma [paměti jazyka JavaScript](../profiling/javascript-memory.md) 

Průvodce Profilováním můžete použít k vytvoření relace výkonu. Určete metody instrumentace a potom určete možnost na stránce instrumentace dialogové okno Vlastnosti relace výkonu profilace jazyka JavaScript.

Když zadáte profilace JavaScriptu, kód jazyka JavaScript, který se spustí v prohlížeči a [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] kód, který se spustí na serveru jsou profilovány.

- Pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, jak kód jazyka JavaScript, který se spustí v prohlížeči a [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] kód, který se spustí na serveru jsou profilovány.

- Pro libovolnou webovou stránku je profilována kód jazyka JavaScript, který se spustí v prohlížeči.

## <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>Chcete-li Profilovat jazyk JavaScript v projektu webové aplikace ASP.NET

1. Otevřít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webový projekt v sadě Visual Studio.

2. Na **analyzovat** nabídky, klikněte na tlačítko **spustit Průvodce výkonem**.

3. Na první stránce Průvodce výkonem, zadejte **instrumentace** metoda profilace a potom klikněte na **Další**.

4. Na druhé stránce průvodce, ujistěte se, že je aktuální projekt vybraný v seznamu cílů a potom klikněte na tlačítko **Další.**

5. Na třetí stránce průvodce vyberte **Profilovat jazyk JavaScript** zaškrtněte políčko a potom klikněte na tlačítko **Další**.

6. Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit** spusťte webovou aplikaci v prohlížeči.

7. Vykonává funkce, které chcete profil.

8. Chcete-li ukončit relaci profilování, ukončete prohlížeč.

### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>Chcete-li Profilovat jazyk JavaScript v jednotlivých webových stránek nebo aplikací jazyka JavaScript

1. Otevřít Visual Studio.

2. Na **analyzovat** nabídky, klikněte na tlačítko **spustit Průvodce výkonem**.

3. Na první stránce Průvodce výkonem, zadejte **instrumentace** metoda profilace a potom klikněte na **Další**.

4. Na druhé stránce průvodce, klikněte na aplikace ASP.NET nebo JavaScript a potom klikněte na tlačítko **Další.**

5. Na třetí stránce průvodce:

    1. Zadejte adresu URL stránky v **jaká adresa URL nebo cesta se spustí aplikace** pole.

    2. Vyberte **Profilovat jazyk JavaScript** zaškrtněte políčko a potom klikněte na tlačítko **Další**.

6. Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit** spuštění webové stránky v prohlížeči.

7. Vykonává funkce, které chcete profil.

8. Chcete-li ukončit relaci profilování, ukončete prohlížeč.