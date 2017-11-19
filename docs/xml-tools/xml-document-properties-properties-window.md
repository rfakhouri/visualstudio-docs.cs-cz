---
title: "Vlastnosti dokumentu XML, vlastnosti – okno | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 24f3760fb328331684e6894954d79675ff27494e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="xml-document-properties-properties-window"></a>Vlastnosti dokumentu XML, vlastnosti – okno
**Vlastnosti** okno poskytuje základní informace o dokumentu, který je aktivní v editoru XML. Vlastnosti, které jsou k dispozici lišit v závislosti na typu dokumentu XML, který je aktuálně aktivní.  
  
> [!NOTE]
>  Všechny vlastnosti dokumentu XML se uloží v řešení. V důsledku toho není nutné znovu zadat tyto hodnoty při příštím otevření řešení.  
  
 **Kódování**  
 Kódování souboru znaků. Změna této vlastnosti také změny kódování atributu v deklaraci XML a naopak. Nové kódování se použije ke kódování souboru při ukládání souboru.  
  
 **Vstup**  
 Vstupní dokument přidružené šablony stylů XSLT. Je používán **ShowXSLT výstup** příkaz. Dokument lze vybrat pomocí Procházet (**...** ) tlačítko.  
  
 Tato vlastnost je viditelná jenom v případě, že soubor XSLT je aktuálně aktivní v okně editoru.  
  
 **Výstup**  
 Soubor, který se vygeneruje, když transformace dokument XML.  
  
 Pokud soubor není určena, výchozí název souboru se generuje na základě `method` atributu u `xsl:output` element, který určuje příponu souboru. Výchozí soubor se nachází v dočasném adresáři aktuálního uživatele.  
  
 **Schémata**  
 Schémata k ověření. Tlačítko otevře **XSD schémata** dialogové okno, které lze použít k výběru schémata používat.  
  
 Můžete také zadat cestu k schémata. Pokud jsou zadány více schématy, každá cesta schématu musí být uzavřena do uvozovek.  
  
 **Šablony stylů**  
 Soubor XSLT, který se používá k transformaci dokumentu při **zobrazit výstup XSLT** pomocí příkazu. Pokud toto pole je prázdné, když **zobrazit výstup XSLT** se používá příkaz, hodnotu podle používá editor `xml-stylesheet` zpracování instrukcí dokumentu, nebo vás vyzve k zadání názvu souboru.  
  
 Při úpravě soubor XSLT, tato vlastnost slouží k určení, že by měla být jiná šablona stylů použít, když **zobrazit výstup XSLT** nebo **ladění XSLT** příkaz. Například můžete to udělat, když upravujete šablonu stylů, který je součástí šablony stylů nadřazené.  
  
## <a name="see-also"></a>Viz také  
 [XML Editor](../xml-tools/xml-editor.md)   
 [Součásti editoru XML](../xml-tools/xml-editor-components.md)