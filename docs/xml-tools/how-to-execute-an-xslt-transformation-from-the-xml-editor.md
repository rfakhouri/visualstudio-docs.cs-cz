---
title: Provedení transformace XSLT
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 56a0fe82-5231-487d-8b6e-a08a9b04e0fc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e84b1c6303da4c0db39da1b3585a7d4548560feb
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526370"
---
# <a name="how-to-execute-an-xslt-transformation-from-the-xml-editor"></a>Postupy: Provedení transformace XSLT z editoru XML

XML editor umožňuje přidružit dokumentu XML v šabloně stylů XSLT, provést transformaci a zobrazte výstup. Výsledný výstup z transformace XSLT se zobrazí v novém okně dokumentu.

**Výstup** vlastnost určuje název souboru pro výstup. Pokud **výstup** je vlastnost prázdná, jejichž název souboru se vygeneruje v dočasném adresáři. Přípona souboru je založen na `xsl:output` prvek vašemu stylu listů a může být. *XML*,. *txt* nebo. *htm*.

Pokud **výstup** vlastnost určuje název souboru. *htm* nebo. *HTML* rozšíření, výstup XSLT je zobrazená v náhledu pomocí webového prohlížeče. Jiné přípony souborů jsou otevřené pomocí výchozího editoru zvolené pomocí sady Visual Studio. Například, pokud je přípona souboru. *xml*, Visual Studio používá editoru XML.

## <a name="execute-an-xslt-transformation-from-an-xml-file"></a>Provedení transformace XSLT ze souboru XML

1. Otevřete dokument XML v editoru XML.

2. Šablony stylů XSLT přidružte k dokumentu XML.

    - Přidat `xml-stylesheet` zpracování instrukcí v dokumentu XML. Například přidejte následující řádek kódu prologu dokumentu: `<?xml-stylesheet type='text/xsl' href='filename.xsl'?>`

       -nebo-

    - Přidat list Styl XSLT pomocí **vlastnosti** okna. V souboru XML otevřen v editoru, klikněte pravým tlačítkem na libovolné místo v editoru a zvolte **vlastnosti**. V **vlastnosti** okno, kliknutím na webu **šablony stylů** pole a klikněte na tlačítko Procházet (...). Vyberte šablony stylů XSLT a pak zvolte **otevřít**.

3. V panelu nabídky zvolte **XML** > **spustit XSLT bez ladění**. Také můžete stisknout klávesu **Ctrl**+**Alt**+**F5**.

   Zobrazí se výstup z transformace XSLT v novém okně dokumentu.

   > [!NOTE]
   > Pokud není k dispozici žádné šablony stylů přidružené k dokumentu XML, dialogové okno zobrazí výzvu k zadání šablony stylů k použití.

## <a name="execute-an-xslt-transformation-from-an-xslt-style-sheet"></a>Provedení transformace XSLT z šablony stylů XSLT

1. Otevření šablony stylů XSLT v editoru XML.

2. Zadejte v dokumentu XML **vstup** pole dokumentu **vlastnosti** okna.

   > [!NOTE]
   > Dokument XML je vstupní dokument použitý pro transformaci. Pokud dokument není zadán při spuštění transformace XSLT **otevřít soubor** zobrazí se dialogové okno a zadáte dokumentu v daném čase.

3. V panelu nabídky zvolte **XML** > **spustit XSLT bez ladění**. Také můžete stisknout klávesu **Ctrl**+**Alt**+**F5**.

   Zobrazí se výstup z transformace XSLT v novém okně dokumentu.

## <a name="specify-an-output-file-name"></a>Zadejte název výstupního souboru

Můžete zadat název výstupního souboru pro soubory XML a XSL. Otevřít **vlastnosti** okna a zadejte název souboru v **výstup** pole.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)