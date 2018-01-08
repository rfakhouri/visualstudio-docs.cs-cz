---
title: Chyby jazyka FxCopCmd | Microsoft Docs
ms.custom: 
ms.date: 10/19/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FxCopCmd errors
ms.assetid: bb614ed0-1b7c-4b56-99ae-da50ef6cfef9
caps.latest.revision: "12"
ms.author: gewarren
author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 48b082f5b00f260d2f8e2519a4551fab23dc1011
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="fxcopcmd-errors"></a>Chyby jazyka FxCopCmd
Fxcopcmd – nebere v úvahu všechny chyby jako kritické. Pokud jazyka FxCopCmd má dostatečné informace k provedení částečné analýzy, provede analýzu a sestavy chybách, ke kterým došlo k chybě. Kód chyby, která je 32bitové celé číslo, obsahuje bitovou kombinaci číselných hodnot, které odpovídají chyby.  
  
 Následující tabulka popisuje kódů chyb vrácených nástrojem jazyka FxCopCmd:  
  
|Chyba|Číselná hodnota|  
|-----------|-------------------|  
|Žádné chyby|0x0|  
|Chyba analýzy|0x1|  
|Pravidlo výjimky|0x2|  
|Chyba načtení projektu|0x4|  
|Chyba načtení sestavení|0x8|  
|Chyba načtení knihovny pravidlo|0x10|  
|Chyba při importu sestavy zatížení|0x20|  
|Chyby výstupu|0x40|  
|Chyba přepínače příkazového řádku|0x80|  
|Chyba inicializace|0x100|  
|Chyba odkazy na sestavení|0x200|  
|BuildBreakingMessage|0x400|  
|Neznámá chyba|0x1000000|  
  
 Závažné chyby, je vrácena následující chyba analýzy. Označuje, že analýza nelze dokončit. V případě potřeby obsahuje kód chyby taky základní příčinu této závažné chyby. Tyto podmínky generovat závažné chyby:  
  
-   Analýzy nelze provést způsobené dostatek vstup.  
  
-   Analýza došlo k výjimce, který není zpracováván jazyka FxCopCmd.  
  
-   Soubor zadaného projektu nebyl nalezen nebo je poškozen.  
  
-   Nebyla zadána možnost output nebo soubor nelze zapsat.  
  
    > [!NOTE]
    >  Jazyka FxCopCmd návratový kód "Sestavení odkazuje na chyby" 0x200 sám o sobě je upozornění, nikoli k chybě. Tento návratový kód označuje, že nebyly nalezeny odkazy na chybějící nepřímých ale, aby bylo možné k jejich zpracování jazyka FxCopCmd. Je upozornění, že je možné, že některé výsledky analýzy může mít dojde k narušení bezpečnosti. Při kombinaci s jakýkoli návratový kód, zvažte "Sestavení odkazuje na chyby" návratový kód za chybu.  
  
## <a name="see-also"></a>Viz také  
 [Chyby aplikace Analýzy kódu](../code-quality/code-analysis-application-errors.md)