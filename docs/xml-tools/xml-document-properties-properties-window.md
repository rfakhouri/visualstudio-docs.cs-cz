---
title: Vlastnosti dokumentu XML, okno Vlastnosti
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 69cd8a8f1acd650c65c995f303adc4d3ee2c1bc5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938240"
---
# <a name="xml-document-properties-properties-window"></a>Vlastnosti dokumentu XML, okno Vlastnosti

**Vlastnosti** okno obsahuje základní informace o dokumentu, který je aktivní v editoru XML. Vlastnosti, které jsou k dispozici se liší v závislosti na typu dokumentu XML, který je aktuálně aktivní.

> [!NOTE]
> Všechny vlastnosti dokumentu XML se ukládají do řešení. V důsledku toho není nutné znovu zadat tyto hodnoty při příštím otevření řešení.

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

## <a name="see-also"></a>Viz také:

- [Editor XML](../xml-tools/xml-editor.md)
- [Součásti editoru XML](../xml-tools/xml-editor-components.md)