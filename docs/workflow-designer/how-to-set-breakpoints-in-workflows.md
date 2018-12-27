---
title: 'Návrhář postupu provádění – jak: Nastavení zarážek v pracovních postupech'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 96db38e8a69d0b8b9ee042420647851aa1fbf0c0
ms.sourcegitcommit: 935e341a02dba1c2aa3b6e89469388aa6e626f7f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53684246"
---
# <a name="how-to-set-breakpoints-in-workflows"></a>Postupy: Nastavení zarážek v pracovních postupech

Při použití návrháře postupu provádění můžete nastavit zarážky na grafické pracovních postupů, jako byste to udělali v jazyce Visual Basic nebo C# kódu. Podle očekávání, zastaví provádění pracovního postupu u každé zarážky, které jste nastavili.

Zarážka má tři stavy: *Čekající*, *vázán*, a *chyba*. Pokud nastavíte zarážku, čeká na vyřízení a je reprezentována solid červenou ikonu. Při načítání pracovního postupu typu modulu runtime vázán. Pokud zadáte nesprávný formát pro zarážku, jako je například název aktivity, která není platná, zobrazí se okno aplikace chyba. Zarážka je přidána do okna zarážky, ale je označena s malým "x".

> [!NOTE]
> Nastavení zarážek v pracovních postupech, vyvolali se nepodporuje.

> [!NOTE]
> Ujistěte se, že vyberete možnost **povolit volbu pouze vlastní kód (pouze spravované)** z **nástroje** > **možnosti** > **ladění**  nabídku před ladění. Pokud tato možnost není vybrána a máte dvou sekvencí, které jsou vnořené uvnitř jiné pořadí a nastavit bod přerušení na první vnitřní pořadí, stisknutím klávesy **F11** není ladění do druhé vnitřní pořadí.

> [!NOTE]
> V pracovním postupu nejsou zarážky pokud úplná cesta k vlastnosti souboru XAML není přesné. Úplná cesta k souboru XAML není přesné po přesunutí projektu nebo řešení do jiné složky nebo do jiného počítače. Vyberte **Ctrl**+**S** uložte a aktualizujte vlastnost úplnou cestu.

## <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>Chcete-li nastavit zarážku pro aktivitu v návrhovém zobrazení

1. Vyberte aktivitu má ladicí program na přerušení na.

2. Na **ladění** nabídce vyberte možnost **Přepnout zarážku**. Červená ikona se zobrazí v levém horním okrajem aktivity.

   Alternativně můžete stisknout **F9** po výběru aktivity, nebo můžete klikněte pravým tlačítkem na aktivitu a vyberte **zarážku** > **vložit zarážku** v místní nabídce.

## <a name="see-also"></a>Viz také:

- [Ladění pracovních postupů pomocí návrháře postupu provádění](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)
- [Postupy: Ladění XAML pomocí návrháře postupu provádění](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)