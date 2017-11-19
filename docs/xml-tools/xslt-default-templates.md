---
title: "Výchozí šablony XSLT | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 773dd34e-67d3-4997-8df9-b71e7f880d88
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e72f0f4b12921c07a66b590655bb8583eb3f9786
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="xslt-default-templates"></a>Výchozí šablony XSLT
Výchozí šablona služby se používá během XSLT zpracováním, když není odpovídající pravidlo explicitní šablony v šabloně stylů. Výchozí šablony, také označovaná jako pravidlo předdefinované šablony, je definovaný v oddílu 5.8 doporučení W3C XSLT 1.0. Výchozí šablony umožňuje XSLT procesor pro zpracování uzlu, i když neexistuje žádné explicitní šablony pravidlo, které odpovídá ho. Ale vzhledem k tomu, že pravidlo předdefinované šablony nejsou výslovně definované v šabloně stylů, to může vést k neočekávané nebo matoucí výsledky transformace XSLT.  
  
 Ladicí program XSLT teď zobrazuje kód XSLT výchozí šablony. Když je krok prostřednictvím transformace XSLT, pokud je použita výchozí šablona, ladicí program zobrazí výchozí šablony v okně. To vám umožňuje procházet kód výchozí šablony a nastavte zarážky v jeho pokyny.  
  
## <a name="see-also"></a>Viz také  
 [Ladění XSLT](../xml-tools/debugging-xslt.md)