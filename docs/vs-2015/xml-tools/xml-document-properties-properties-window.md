---
title: Vlastnosti dokumentu XML, okno Vlastnosti | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7145c81a87235d37a0e4825509e7f8fb94ab0f7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675088"
---
# <a name="xml-document-properties-properties-window"></a>Vlastnosti dokumentu XML, okno Vlastnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vlastnosti dokumentu XML, okno Vlastnosti](https://docs.microsoft.com/visualstudio/xml-tools/xml-document-properties-properties-window).  
  
  
**Vlastnosti** okno obsahuje základní informace o dokumentu, který je aktivní v editoru XML. Vlastnosti, které jsou k dispozici se liší v závislosti na typu dokumentu XML, který je aktuálně aktivní.  
  
> [!NOTE]
>  Všechny vlastnosti dokumentu XML se ukládají do řešení. V důsledku toho není nutné znovu zadat tyto hodnoty při příštím otevření řešení.  
  
 **Kódování**  
 Znak kódování souboru. Změna této vlastnosti také změny kódování atributu v deklaraci XML a naopak. Nové kódování se použije ke kódování souboru při uložení souboru.  
  
 **Vstup**  
 Vstupní dokument přidružené šablony stylů XSLT. Používá se **ShowXSLT výstup** příkazu. Dokument lze vybrat pomocí Procházet (**...** ) tlačítko.  
  
 Tato vlastnost je viditelná pouze v případě, že soubor XSLT je aktuálně aktivní v okně editoru.  
  
 **Output**  
 Soubor, který je generován při transformaci dokumentu XML.  
  
 Pokud soubor není zadán, výchozí název souboru je generován a základě `method` atribut na `xsl:output` element, který určuje příponu souboru. Výchozí soubor se nachází v dočasném adresáři aktuálního uživatele.  
  
 **Schémata**  
 Schémata pro ověřování. Tlačítko otevře **schémata XSD** dialogové okno, které lze použít pro výběr schémat použití.  
  
 Můžete také zadat cestu k schémata. Pokud nejsou zadány více schémat, každá cesta schématu musí být uzavřen do dvojitých uvozovek.  
  
 **Šablona stylů**  
 Soubor XSLT, který slouží k transformaci dokumentu při **zobrazit výstup XSLT** příkaz se používá. Pokud toto pole je prázdné, pokud **zobrazit výstup XSLT** příkaz se používá, editor používá hodnotu podle `xml-stylesheet` zpracování dokumentu, nebo vás vyzve k zadání názvu souboru.  
  
 Při úpravách souboru XSLT, tato vlastnost slouží k určení, zda by měl být jiné šablony stylů nepoužívá, pokud **zobrazit výstup XSLT** nebo **ladění XSLT** příkaz. Chcete například provést při úpravách šablony stylů, která je součástí nadřazené šablony stylů.  
  
## <a name="see-also"></a>Viz také  
 [XML Editor](../xml-tools/xml-editor.md)   
 [Součásti editoru XML](../xml-tools/xml-editor-components.md)



