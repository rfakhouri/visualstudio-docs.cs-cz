---
title: 'Postup: provedení transformace XSLT z editoru XML | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 56a0fe82-5231-487d-8b6e-a08a9b04e0fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ce56195d0bc9750af3b869cb3e8bb0a780fdcde
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-execute-an-xslt-transformation-from-the-xml-editor"></a>Postup: provedení transformace XSLT z editoru XML
Editor souborů XML umožňuje přidružit stylů XSLT dokumentu XML provedení transformace a zobrazte výstup. Výsledný výstup transformace XSLT se zobrazí v novém okně dokumentu.  
  
 **Výstup** vlastnost určuje název souboru pro výstup. Pokud **výstup** vlastnost je prázdná, název souboru je vygenerována v dočasném adresáři. Přípona souboru je založena na `xsl:output` element vaším stylem list a může být XML, txt nebo .htm.  
  
 Pokud **výstup** vlastnost určuje název souboru .htm nebo .html rozšíření, výstup XSLT zobrazení náhledu pomocí [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Internet Explorer. Jiné přípony souborů jsou otevřené pomocí editoru výchozí, kterou si zvolí [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Visual Studio. Například pokud přípona souboru .xml, Visual Studio použije editoru XML.  
  
### <a name="to-execute-an-xslt-transformation-from-an-xml-document"></a>K provedení transformace XSLT z dokumentu XML  
  
1.  Otevřete dokument XML v editoru XML.  
  
2.  Přidružte stylů XSLT v dokumentu XML.  
  
    -   Přidat `xml-stylesheet` zpracování instrukcí v dokumentu XML. Například přidejte následující řádek `<?xml-stylesheet type='text/xsl' href='filename.xsl'?>` k prologu dokumentu.  
  
         -nebo-  
  
    -   Přidat pomocí list stylu XSLT **vlastnosti** okno. V dokumentu **vlastnosti – okno**, klikněte **Procházet** tlačítko pro **šablony stylů** pole, vyberte styl XSLT a klikněte na **otevřete**.  
  
3.  Klikněte na tlačítko **ShowXSL výstup** tlačítko **editoru XML** panelu nástrojů.  
  
    > [!NOTE]
    >  Pokud není žádná šablona stylů přidružené k dokumentu XML, dialogové okno zobrazí výzvu k zadání šablony stylů používat.  
    >   
    >  Výsledný výstup transformace XSLT se zobrazí v novém okně dokumentu.  
  
### <a name="to-execute-an-xslt-transformation-from-an-xslt-style-sheet"></a>K provedení transformace XSLT z šablony stylů XSLT  
  
1.  Otevřete šablonu stylů XSLT v editoru XML.  
  
2.  Zadejte dokument XML v **vstup** pole dokumentu **vlastnosti** okno.  
  
    > [!NOTE]
    >  V dokumentu XML je vstupní dokument použít pro transformaci. Pokud není zadán dokument a při spuštění transformace XSLT **otevřít soubor** zobrazí se dialogové okno, a zadáte dokumentu v daném čase.  
  
3.  Klikněte na tlačítko **ShowXSLT výstup** tlačítko **editoru XML** panelu nástrojů.  
  
     Výsledný výstup transformace XSLT se zobrazí v novém okně dokumentu.  
  
### <a name="to-provide-a-different-output-file-name"></a>K zadání názvu souboru odlišný výstup  
  
1.  Zadejte název souboru do **výstup** pole dokumentu **vlastnosti** okno.  
  
2.  Klikněte na tlačítko **ShowXSLT výstup** tlačítko **editoru XML** panelu nástrojů.  
  
     Výsledný výstup transformace XSLT se zobrazí v novém okně dokumentu a editoru použít ve výstupním okně, závisí na příponu vaše **výstup** dokumentu vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)