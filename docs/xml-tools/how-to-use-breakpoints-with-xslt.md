---
title: 'Postupy: Používání zarážek v XSLT'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 72a22937792cc06bcac18f70a2bd4c53be98f7fe
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53894886"
---
# <a name="how-to-use-breakpoints-with-xslt"></a>Postupy: Používání zarážek v XSLT

Můžete nastavit zarážky v šabloně stylů XSLT, nebo ve zdrojovém dokumentu XML. Pokud nastavíte zarážku na značku, při spuštění zarážce přejde k další příkaz, který obsahuje informace o řádku zdroje.

Další informace najdete v tématu [základní informace o ladění: Zarážky](../debugger/using-breakpoints.md).

## <a name="set-a-breakpoint-in-a-style-sheet"></a>Nastavte zarážku v šabloně stylů

Zarážky lze nastavit na počáteční značky, koncovými značkami a textové uzly šablony stylů XSLT. Zarážky můžete také nastavit na kód v bloku skriptu.

### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>Chcete-li nastavit zarážku v šabloně stylů

1.  Otevření šablony stylů v editoru XML.

2.  Umístěte kurzor myši v místě zarážky, klikněte pravým tlačítkem, přejděte na **zarážku**a klikněte na tlačítko **vložit zarážku**.

3.  Klikněte na tlačítko Procházet (**...** ) na **vstup** pole v okně Vlastnosti dokumentu.

4.  Vyhledejte zdrojový dokument XML a klikněte na tlačítko **otevřít**.

     Tím se nastaví zdrojový soubor dokumentu, který slouží k transformaci XSLT.

5.  Klikněte na tlačítko **ladění XSL** tlačítko na panelu nástrojů editoru XML.

## <a name="set-a-breakpoint-in-an-xml-source-document"></a>Nastavit zarážku ve zdrojovém dokumentu XML

Zarážky lze nastavit na elementy, atributy, uzel oboru názvů, komentáře, instrukce pro zpracování a textové uzly zdrojovém dokumentu XML. Nelze nastavit zarážku na uzel dokumentu nebo na uzel oboru názvů, který je zděděn z nadřazeného elementu.

### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>Chcete-li nastavit zarážku ve zdrojovém dokumentu XML

1.  Otevřete dokument XML v editoru XML.

2.  Umístěte kurzor myši v místě zarážky, klikněte pravým tlačítkem, přejděte na **zarážku**a klikněte na tlačítko **vložit zarážku**.

3.  Klikněte na tlačítko Procházet (**...** ) na **šablony stylů** pole v okně Vlastnosti dokumentu.

4.  Vyhledejte zdrojový dokument XML a klikněte na tlačítko **otevřít**.

     Tím se nastaví zdrojový soubor dokumentu, který slouží k transformaci XSLT.

5.  Klikněte na tlačítko **ladění XSL** tlačítko na panelu nástrojů editoru XML.

## <a name="see-also"></a>Viz také:

- [Návod: Ladění stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)