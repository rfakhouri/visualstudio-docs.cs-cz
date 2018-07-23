---
title: 'Postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET v sadě Visual Studio'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.asp
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: c924a866f1bb34f41664fbf62e372b77f4d2620e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178234"
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>Postupy: Konfigurace Analýzy kódu pro webovou aplikaci ASP.NET

V sadě Visual Studio, můžete vybrat ze seznamu analýzy kódu *sad pravidel* vyrovnat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci. Výchozí sada pravidel je Microsoft Minimální doporučená pravidla. Můžete vybrat jinou sadu pravidel, která platí pro webové stránky.

1. Vyberte web v **Průzkumníka řešení**.

2. Na **analyzovat** nabídky, klikněte na tlačítko **konfigurovat analýzu kódu pro webovou stránku**.

3. Pokud jste vybrali řešení a řešení obsahuje více než jeden projekt, vyberte sestavení konfigurace a cílový operační systém z **konfigurace** a **platformy** seznamy.

4. Pro každý projekt v řešení, klikněte na tlačítko **sady pravidel** sloupec a pak klikněte na název pravidla nastaven na spouštění.

5. Ve výchozím nastavení je analýza kódu spuštěna na všechny projekty v řešení. Pokud chcete zakázat nebo povolit analýzu kódu pro konkrétní projekt, postupujte takto:

    1. Klikněte pravým tlačítkem na název projektu a pak klikněte na vlastnosti.

    2. Zaškrtněte nebo zrušte zaškrtnutí **povolit analýzu kódu** zaškrtávací políčko. Můžete také spustit analýzu kódu ručně tak, že vyberete **spustit analýzu kódu na webu** z **analyzovat** nabídky.

6. V **spustit tuto sadu pravidel** rozevírací seznam, postupujte podle těchto kroků:

    - Vyberte sadu pravidel, který chcete použít.

    - Vyberte  **\<procházet >** zadat sadu existujících vlastních pravidel, která se nenachází v seznamu.

    - Definování [vlastní sady pravidel](../code-quality/how-to-create-a-custom-rule-set.md).