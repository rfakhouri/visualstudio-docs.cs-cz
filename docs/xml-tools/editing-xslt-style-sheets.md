---
title: Úpravy XSLT šablony stylů
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16a7d850f8045ce70166bec3324470abaf61b6de
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="editing-xslt-style-sheets"></a>Úpravy XSLT šablony stylů

Editor souborů XML lze také upravit XSLT šablony stylů. Můžete využít výhod výchozí funkce editoru, jako je technologie IntelliSense, osnovy, fragmenty kódu XML a tak dále. Kromě toho existují také nové funkce, které usnadňují vývoj v XSLT.

## <a name="xslt-features"></a>Funkce XSLT
 Následující tabulka popisuje funkce, které jsou specifické pro práci s XSLT šablony stylů.

 **Barevné zvýrazňování syntaxe**

 Klíčová slova XSLT, například `template`, `match`a tak dále se zobrazují v barvu – klíčové slovo XSLT určeného **písma a barev** nastavení.

 **Podtržení vlnovkami**

 Editor souborů XML soubor nainstalované xslt.xsd používá k ověření XSLT šablony stylů. Jako modré podtržení vlnovkami zobrazí chyby ověření. Editor souborů XML také zkompiluje šablony stylů v pozadí a sestavy kompilátoru chyby nebo upozornění s příslušnou podtržení vlnovkami.

 **Podpora pro blocích skriptu**

 Ladicí program XSLT podporuje kódu v blocích skriptu, můžete nastavit zarážky a krokovat kód bloku skriptu.

 **Zobrazit výstup XSLT**

 Můžete provést transformace XSL a zobrazte výstup z editoru XML. Další informace najdete v tématu [postup: provedení transformace XSLT z editoru XML](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md).

 **Ladění XSLT**

 Můžete spustit ladicí program XSLT ze souboru XSLT v editoru XML. Ladicí program podporuje nastavení zarážek v souboru XSLT, zobrazení stavu spuštění XSLT a tak dále. Ukazatele myši na proměnnou XSLT zobrazí popisek s hodnotou proměnné. Ladicí program slouží k ladění šablony stylů a ladit kompilované transformace XSL vyvolat z jiné aplikace. Další informace najdete v tématu [ladění XSLT](../xml-tools/debugging-xslt.md).

## <a name="see-also"></a>Viz také

- [Editor XML](../xml-tools/xml-editor.md)