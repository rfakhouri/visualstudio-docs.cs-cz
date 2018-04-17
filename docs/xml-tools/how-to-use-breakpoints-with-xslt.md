---
title: 'Postupy: použití zarážek s XSLT | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f262fa2b1822f74dc15b6f8599b88161c0a1cf8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-breakpoints-with-xslt"></a>Postupy: použití zarážek s XSLT

Můžete nastavit zarážky v šabloně stylů XSLT nebo ve zdrojovém dokumentu XML. Pokud nastavíte zarážku na značku, při spuštění zarážce přesune na další příkaz, který obsahuje informace o řádku zdroje.

Další informace najdete v tématu [základní informace o ladění: zarážky](../debugger/using-breakpoints.md).

## <a name="set-a-breakpoint-in-a-style-sheet"></a>Nastavte zarážky v šabloně stylů.

Zarážky lze nastavit u počáteční značky, koncové značky a textové uzly stylů XSLT. Na kód v bloku skriptu můžete také nastavit zarážky.  
  
### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>Chcete-li nastavit zarážky v šabloně stylů.
  
1.  Otevřete list stylu v editoru XML.  
  
2.  Umístěte kurzor do zarážek umístění, klikněte pravým tlačítkem, přejděte na **zarážek**a klikněte na tlačítko **vložit zarážku**.  
  
3.  Klikněte na tlačítko Procházet na tlačítko Procházet (**...** ) na **vstup** pole v okně vlastností dokumentu.  
  
4.  Vyhledejte zdrojový dokument XML a klikněte na tlačítko **otevřete**.  
  
     Toto nastaví zdrojový soubor dokumentu, který se používá pro transformace XSLT.  
  
5.  Klikněte **ladění XSL** tlačítka na panelu nástrojů editoru XML.  

## <a name="set-a-breakpoint-in-an-xml-source-document"></a>Nastavit zarážky ve zdrojovém dokumentu XML

Zarážky můžete nastavit na elementy, atributy, uzel oboru názvů, komentáře, pokyny pro zpracování a textové uzly zdrojový dokument XML. Nelze nastavit zarážky na uzel dokumentu nebo na uzel oboru názvů, který dědí z nadřazeného elementu.  

### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>Chcete-li nastavit zarážky ve zdrojovém dokumentu XML

1.  Otevřete dokument XML v editoru XML.  
  
2.  Umístěte kurzor do zarážek umístění, klikněte pravým tlačítkem, přejděte na **zarážek**a klikněte na tlačítko **vložit zarážku**.  
  
3.  Klikněte na tlačítko Procházet na tlačítko Procházet (**...** ) na **šablony stylů** pole v okně vlastností dokumentu.  
  
4.  Vyhledejte zdrojový dokument XML a klikněte na tlačítko **otevřete**.  
  
     Toto nastaví zdrojový soubor dokumentu, který se používá pro transformace XSLT.  
  
5.  Klikněte **ladění XSL** tlačítka na panelu nástrojů editoru XML.  
 
## <a name="see-also"></a>Viz také

[Návod: Ladění šablony stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)