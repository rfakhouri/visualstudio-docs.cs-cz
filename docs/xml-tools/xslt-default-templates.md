---
title: Výchozí šablony XSLT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 773dd34e-67d3-4997-8df9-b71e7f880d88
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b1d2f0a7102821041bf76f1e8dcd73ff01baacc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="xslt-default-templates"></a>Výchozí šablony XSLT
Výchozí šablona služby se používá během XSLT zpracováním, když není odpovídající pravidlo explicitní šablony v šabloně stylů. Výchozí šablony, také označovaná jako pravidlo předdefinované šablony, je definovaný v oddílu 5.8 doporučení W3C XSLT 1.0. Výchozí šablony umožňuje XSLT procesor pro zpracování uzlu, i když neexistuje žádné explicitní šablony pravidlo, které odpovídá ho. Ale vzhledem k tomu, že pravidlo předdefinované šablony nejsou výslovně definované v šabloně stylů, to může vést k neočekávané nebo matoucí výsledky transformace XSLT.  
  
 Ladicí program XSLT teď zobrazuje kód XSLT výchozí šablony. Když je krok prostřednictvím transformace XSLT, pokud je použita výchozí šablona, ladicí program zobrazí výchozí šablony v okně. To vám umožňuje procházet kód výchozí šablony a nastavte zarážky v jeho pokyny.  
  
## <a name="see-also"></a>Viz také  
 [Ladění XSLT](../xml-tools/debugging-xslt.md)