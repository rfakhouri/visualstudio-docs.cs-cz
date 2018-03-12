---
title: "Postupy: Nastavte zarážky v pracovních postupech | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 66ed757fab518d9cfe23b26186e6bded06eafe1e
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-set-breakpoints-in-workflows"></a>Postupy: Nastavte zarážky v pracovních postupech
Když použijete návrháře pracovního postupu systému Windows, můžete nastavit zarážky na grafické pracovní postupy jako byste to udělali v kódu Visual Basic a C#. Podle očekávání, zastaví zpracování pracovního postupu u každé zarážky, který nastavíte.

 Zarážku má tři stavy: *čekající*, *vázaný*, a *chyba*. Když nastavíte zarážku, čeká na vyřízení a je reprezentována plnou červenou ikonu. Pokud modul runtime načetl typ pracovního postupu, stane vázána. Pokud zadáte nesprávný formát pro bod přerušení, jako je například název aktivity, který není platný, zobrazí se okno s chyby. Zarážce přidána do okna zarážek, ale je označen s malým "x".

> [!NOTE]
> Nastavení zarážek v pracovních postupech, vyvolá se nepodporuje.

> [!WARNING]
> Ujistěte se, že vyberete možnost **povolit volbu pouze vlastní kód (pouze spravované)** z **nástroje**, **možnosti**, **ladění** nabídky před ladění. Pokud máte dvě pořadí vnořené v jiném pořadí a nastavit bod přerušení na první vnitřní pořadí, stisknete **F11** nebude ladění do druhé vnitřní pořadí, pokud **povolit volbu pouze vlastní kód (spravovaných jenom)**možnost není vybraná.

> [!WARNING]
> V pracovním postupu nebude získat zarážky Pokud není přesný úplná cesta k vlastnosti souboru XAML. Úplná cesta k souboru XAML není přesný po přesunutí projekt nebo řešení do jiné složky nebo do jiného počítače. Vyberte kombinace kláves Ctrl + S uložte a aktualizujte vlastnost úplnou cestu.

### <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>Chcete-li nastavit zarážky aktivity v zobrazení návrhu

1.  Vyberte aktivitu, aby ladicí program na přerušení na.

2.  Na **ladění** nabídce vyberte možnost **Přepnout zarážku**. V levém horním okrajem aktivity se objeví červená ikona.

     Alternativně můžete také stisknout zástupce **F9** klíče po výběru aktivity nebo je můžete klikněte pravým tlačítkem na aktivitu a vyberte **zarážek** pak **vložit zarážku**v místní nabídce.

## <a name="see-also"></a>Viz také

- [Postupy: Spuštění ladicího programu pracovních postupů](../workflow-designer/how-to-invoke-the-workflow-debugger.md)
- [Ladění pracovních postupů pomocí návrháře postupu provádění](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)
- [Postupy: Ladění XAML pomocí návrháře postupu provádění](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)