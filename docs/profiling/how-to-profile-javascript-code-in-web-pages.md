---
title: 'Postupy: profilování kódu JavaScript na webových stránkách | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
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
ms.openlocfilehash: 3a00f182b21082ed9c3942b270f84b9db0d66f2d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>Postupy: profilování kódu JavaScript ve webové stránky

Profilace nástroje sady Visual Studio můžete shromažďovat data o výkonu pro kód JavaScript, který se spustí v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, libovolné webové stránky nebo aplikace JavaScript pomocí metoda profilování instrumentace. Vyžaduje Internet Explorer 8 nebo novější.

> [!WARNING]
> Profil JavaScript v aplikacích pro UPW, najdete v tématu [paměť jazyka JavaScript](../profiling/javascript-memory.md) 

Profilace Průvodce vám pomůže vytvořit relaci výkonu. Zadejte metody instrumentace a pak zadejte JavaScript profilace možnost na stránce instrumentace dialogové okno Vlastnosti výkonnostní relace.

Když zadáte JavaScript – profilace, kód jazyka JavaScript, která se spouští v prohlížeči a [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] jsou profilovaným kód, který spouští na serveru.

- Pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace, i kód JavaScript, který spouští v prohlížeči a [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] jsou profilovaným kód, který spouští na serveru.

- Pro webovou stránku libovolný je profilovaným kód JavaScript, který se spustí v prohlížeči.

## <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>Do profilu JavaScript v projektu aplikace ASP.NET

1. Otevřete [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webového projektu v sadě Visual Studio.

2. Na **analyzovat** nabídky, klikněte na tlačítko **spusťte Průvodce výkonu**.

3. Na první stránce průvodce výkonu, zadejte **instrumentace** metoda profilování a pak klikněte na **Další**.

4. Na druhé stránce průvodce, ujistěte se, zda je aktuální projekt vybrán v seznamu cílů a pak klikněte na tlačítko **Další.**

5. Na třetí stránce průvodce vyberte **profil JavaScript** zaškrtněte políčko a potom klikněte na **Další**.

6. Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit** spuštění webové aplikace v prohlížeči.

7. Výkonu funkce, které chcete profil.

8. K ukončení relace profilování, zavřete prohlížeč.

### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>Do profilu JavaScript v jednotlivých webové stránky nebo aplikace JavaScript

1. Otevřete Visual Studio.

2. Na **analyzovat** nabídky, klikněte na tlačítko **spusťte Průvodce výkonu**.

3. Na první stránce průvodce výkonu, zadejte **instrumentace** metoda profilování a pak klikněte na **Další**.

4. Na druhé stránce průvodce, klikněte na aplikace ASP.NET nebo JavaScript a pak klikněte na tlačítko **Další.**

5. Na třetí stránce průvodce:

    1. Zadejte adresu URL stránky v **jaké adresu URL nebo cestu aplikaci spustit** pole.

    2. Vyberte **profil JavaScript** zaškrtněte políčko a potom klikněte na **Další**.

6. Na čtvrté stránce průvodce, klikněte na tlačítko **Dokončit** spustit webovou stránku v prohlížeči.

7. Výkonu funkce, které chcete profil.

8. K ukončení relace profilování, zavřete prohlížeč.