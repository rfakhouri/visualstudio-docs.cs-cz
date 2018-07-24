---
title: Přidání značek počítače do mapování sady čítačů pro zátěžové testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, counter set mappings, computer tags
ms.assetid: f52a73e1-036a-4b28-a6c8-848284bf4488
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 96ce122c78c20b741613ed45820f585236a0383b
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2018
ms.locfileid: "39203664"
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>Postupy: Přidání značek počítače do sad čítačů pomocí editoru zátěžových testů mapování

Značky počítače umožňují určit počítač s názvem snadno rozpoznat. Značky jsou zobrazeny v **mapování sady čítačů** uzel ve stromu v editoru zátěžového testu. Důležitější, značky se zobrazí v sestavách aplikace Excel, které pomáhají identifikovat účastníky jakou roli má počítač v zátěžovém testu. Například "Web Server1 v lab2" nebo "SQL Server2 Phoenixu". Další informace najdete v tématu [sestav zátěžové testy s výsledky pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).

## <a name="to-add-a-tag-to-a-computer"></a>Pokud chcete přidat značku počítače

1.  Otevřete zátěžový test.

2.  Zvolte **spravovat sady čítačů** tlačítko.

     – nebo –

     Klikněte pravým tlačítkem na **sady čítačů** složky v zátěžového testování stromu a zvolte **spravovat sady čítačů**.

     **Spravovat sady čítačů** se zobrazí dialogové okno.

3.  (Volitelné) V **vybrané počítače a sady čítačů budou přidány pod následující nastavení spuštění** seznamu, vyberte jiný parametr spuštění.

    > [!NOTE]
    > To platí, pouze pokud máte více než jeden parametr spuštění zátěžového testu.

4.  V části **počítače a sady čítačů k monitorování**, vyberte počítač, který chcete použít značky.

    > [!NOTE]
    > Informace o tom, jak přidat počítač najdete v tématu [postupy: Správa sad čítačů](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

5.  V **značky počítače** textového pole zadejte značku pro přiřazení k počítači. Například "TestMachine12 v lab3."

6.  Zvolte **OK**.

## <a name="see-also"></a>Viz také:

- [Analýza překročení mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: Správa sad čítačů](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)