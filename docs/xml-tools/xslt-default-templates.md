---
title: Výchozí šablony XSLT
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 773dd34e-67d3-4997-8df9-b71e7f880d88
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2eb71cf0a94f02e5de8af9e61bdc947694920929
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53908381"
---
# <a name="xslt-default-templates"></a>Výchozí šablony XSLT

Výchozí šablona se používá při zpracování, pokud neexistuje žádné odpovídající pravidlo explicitní šablony v šabloně stylů XSLT. Výchozí šablony, které se označují také jako integrované šablony pravidla, je definován v oddíle 5.8 doporučení W3C XSLT 1.0. Výchozí šablona umožňuje procesoru XSLT pro zpracování na uzel, i když neexistuje žádné explicitní šablonu pravidlo, který mu odpovídá. Ale protože předdefinovaných šablony pravidla nejsou výslovně definované v šabloně stylů, to může vést k neočekávaným nebo matoucí výsledky transformace XSLT.

Ladicí program XSLT teď zobrazuje kód výchozí šablony XSLT. Při krokování přes transformace XSLT, pokud je použita výchozí šablona, ladicí program zobrazí v okně výchozí šablony. To umožňuje krokovat kód výchozí šablonu a nastavit zarážky podle jeho pokynů.

## <a name="see-also"></a>Viz také:

- [Ladění XSLT](../xml-tools/debugging-xslt.md)