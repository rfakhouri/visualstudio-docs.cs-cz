---
title: Fxcopcmd – chyby | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- FxCopCmd errors
ms.assetid: bb614ed0-1b7c-4b56-99ae-da50ef6cfef9
caps.latest.revision: 12
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 016f22591deb019718c8271cf0b307d3f4c597c1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60043105"
---
# <a name="fxcopcmd-errors"></a>Chyby jazyka FxCopCmd
Fxcopcmd – nebere v úvahu všechny chyby, chcete-li být závažné. Pokud fxcopcmd – má dostatek informací k provedení částečné analýzy, provede analýzu a sestavy chyb, ke kterým došlo. Kód chyby, která je 32bitové celé číslo, obsahuje bitová kombinace číselných hodnot, které odpovídají chyby.  
  
 Následující tabulka popisuje kódů chyb vrácených nástrojem fxcopcmd –:  
  
|Chyba|Číselná hodnota|  
|-----------|-------------------|  
|Žádné chyby|0x0|  
|Chyba analýzy|0x1|  
|Pravidlo výjimky|0x2|  
|Chyba při načítání projektu|0x4|  
|Chyba při načítání sestavení|0x8|  
|Chyba při načítání knihovny pravidlo|0x10|  
|Chyba při načítání sestavy importu|0x20|  
|Chyba výstupu|0x40|  
|Chyba přepínač příkazového řádku|0x80|  
|Chyba při inicializaci|0x100|  
|Chyba odkazy na sestavení|0x200|  
|BuildBreakingMessage|0x400|  
|Došlo k neznámé chybě|0x1000000|  
  
 Chyba analýzy, je vrácena pro závažné chyby. Znamená to, že analýzu nelze dokončit. Pokud se používá, kód chyby: také obsahuje základní příčiny závažná chyba. Následující podmínky generovat závažné chyby:  
  
- Analýzy nelze provést, způsobené dostatek vstup.  
  
- Analýzy došlo k výjimce, která není zpracována fxcopcmd –.  
  
- Zadaný soubor projektu nebyl nalezen nebo je poškozený.  
  
- Možnost výstupu se nezadalo nebo nebylo možné zapsat soubor.  
  
    > [!NOTE]
    >  Fxcopcmd – návratový kód "Sestavení odkazuje na chybu" 0x200 sám o sobě je varování spíše než chybu. Tento návratový kód znamená, že nebyly nalezeny chybějící nepřímé odkazy, ale, že fxcopcmd – bylo možné jejich zpracování. Jde upozornění, že je možné, že některé výsledky analýzy mohl být ohrožený. Vezměte v úvahu "Sestavení odkazuje na chybu" návratový kód jako chyba kombinaci s jakýkoli návratový kód.  
  
## <a name="see-also"></a>Viz také  
 [Chyby aplikace Analýzy kódu](../code-quality/code-analysis-application-errors.md)