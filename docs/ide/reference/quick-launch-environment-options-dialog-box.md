---
title: Dialogové okno Snadné spuštění, Prostředí, Možnosti
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f8f8bc5a19e3cb91634b5a61e0b3e917fb0a3f9a
ms.sourcegitcommit: 2dc924c96a6d48803c8eedc3d6781202629b41fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/11/2019
ms.locfileid: "57737001"
---
# <a name="quick-launch-environment-options-dialog-box"></a>Dialogové okno Snadné spuštění, Prostředí, Možnosti

Můžete použít **Snadné spuštění** chcete rychle najít a spustit akce pro prostředky IDE, jako jsou možnosti, šablony, nabídky. Nemůžete použít **Snadné spuštění** k vyhledání kódu a symbolům. **Snadné spuštění** vyhledávacího pole se nachází v pravém horním rohu řádku nabídek a je přístupný výběrem klávesy Ctrl + Q. Do pole zadejte hledaný řetězec. K vyhledání řetězce, které obsahují @, použijte ”@@”. 

**Snadné spuštění** je ve výchozím nastavení povolené při instalaci sady Visual Studio. Na panelu nabídky můžete zobrazit nebo skrýt **Snadné spuštění** výběrem **nástroje**, **možnosti**. Rozbalte **prostředí** uzel a klikněte na tlačítko **Snadné spuštění**. Zaškrtněte nebo zrušte zaškrtnutí **umožňují snadné spuštění** zaškrtávací políčko. Můžete také povolit nebo zakázat kategorie vyhledávání na této stránce.

## <a name="category-list"></a>Seznam kategorií

Rychlé spuštění výsledky hledání se zobrazí v čtyři kategorie: **Většina naposledy použité**, **nabídky**, **možnosti**, a **otevřené dokumenty**, spolu s počtem položek v kategorii. Průchodné výsledky hledání podle kategorií, stiskněte klávesy Ctrl + Q pro zobrazení všech výsledků z další kategorie. Za poslední se zobrazí kategorie, Ctrl + Q dozvíte několik výsledky z každé kategorie. Ctrl + Shift + Q můžete použít k procházení mezi kategorií v obráceném pořadí. Chcete-li zobrazit všechny výsledky hledání podle kategorie, zvolte název kategorie.

Následující klávesové zkratky můžete použít k omezení hledání na konkrétní kategorie.

|Kategorie|Zástupce|Popis místní|
|--------------|--------------| - |
|Naposledy použité|@mru<br /><br /> Třeba `@mru font`.|Zobrazí až pět položek, které jste **naposledy použitých**.|
|Nabídky|@menu<br /><br /> Třeba `@menu project`.|Omezení vyhledávání a položkami nabídky.|
|Možnosti|@opt<br /><br /> Třeba `@opt font`.|Omezuje vyhledávání na nastavení v **možnosti** dialogové okno.|
|Dokumenty|@doc<br /><br /> Třeba `@doc program.cs`.|Omezuje vyhledávání na názvy souborů a cesty otevřené dokumenty pro kritéria vyhledávání, ale nebude hledat text mezi soubory sami.|

> [!NOTE]
> Můžete změnit klávesové zkratky na **Obecné**, **klávesnice** stránku **možnosti** dialogové okno.

## <a name="show-previous-results"></a>Zobrazit předchozí výsledky

Ve výchozím nastavení není mezi relacemi hledání trvalých hledaný termín, který zadáte. Hledaný řetězec není zaškrtnuto, je-li vyhledat termín, přesuňte kurzor mimo **Snadné spuštění** oblasti a pak se vraťte zpět. Pokud chcete zachovat výsledky hledání, přejděte na **možnosti** dialogového okna zvolte **Snadné spuštění**a pak vyberte **zobrazit výsledky předchozího vyhledávání. Pokud je aktivováno Snadné spuštění.** Zaškrtávací políčko. Při příštím hledání, ponechte v oblasti Snadné spuštění a vraťte, snadné spuštění bude uchovávat hledaný termín, naposledy použité a také zobrazit výsledky hledání.

Nejnovější tipy a triky pro použití **Snadné spuštění**, naleznete v tématu [blogu Visual Studio](http://go.microsoft.com/fwlink/?LinkId=236054).

## <a name="see-also"></a>Viz také

- [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)
