---
title: Vlastnosti dokumentu XML, okno Vlastnosti
ms.date: 03/05/2019
ms.topic: reference
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 679ac529708a49d18025672ce8f880c4f7710471
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808129"
---
# <a name="xml-document-properties-properties-window"></a>Vlastnosti dokumentu XML, okno Vlastnosti

**Vlastnosti** okno obsahuje základní informace o dokumentu, který je aktivní v editoru XML. Vlastnosti, které jsou k dispozici se liší v závislosti na typu dokumentu XML, který je aktuálně aktivní.

> [!NOTE]
> Všechny vlastnosti dokumentu XML se ukládají do řešení. V důsledku toho není nutné znovu zadat tyto hodnoty při příštím otevření řešení.

**Kódování**

Znak kódování souboru. Změna této vlastnosti také změny kódování atributu v deklaraci XML a naopak. Nové kódování se používá ke kódování souboru při uložení souboru.

**Vstup**

Vstupní dokument přidružené šablony stylů XSLT. Používá se **spustit XSLT** příkazy, například **XML** > **spustit XSLT bez ladění**. Dokument lze vybrat pomocí Procházet (**...** ) tlačítko.

Tato vlastnost je viditelná pouze v případě, že soubor XSLT je otevřen v editoru.

**Output**

Soubor, který je generován při transformaci dokumentu XML.

Pokud soubor není zadán, výchozí název souboru je generován a základě `method` atribut na `xsl:output` element, který určuje příponu souboru. Výchozí soubor se nachází v dočasném adresáři aktuálního uživatele.

**Schémata**

Schémata pro ověřování. Tlačítko otevře **schémata XSD** dialogové okno, které lze použít pro výběr schémat použití.

Můžete také zadat cestu k schémata. Pokud nejsou zadány více schémat, každá cesta schématu musí být uzavřen do dvojitých uvozovek.

**Šablona stylů**

Soubor XSLT, který slouží k transformaci dokumentu při **spustit ladění XSLT** a **spustit XSLT bez ladění** příkazy se používají. Pokud je toto pole prázdné, editor používá hodnotu podle `xml-stylesheet` zpracování instrukcí z dokumentu nebo vás vyzve k zadání názvu souboru.

Při úpravách souboru XSLT, tato vlastnost slouží k určení, zda by měl být jiné šablony stylů nepoužívá, pokud **spustit ladění XSLT** nebo **spustit XSLT bez ladění** příkaz. Chcete například provést při úpravách šablony stylů, která je součástí nadřazené šablony stylů.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)