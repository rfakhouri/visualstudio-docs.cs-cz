---
title: Formát specifikátorů v jazyce C# | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- CSharp
helpviewer_keywords:
- expressions [C#], formatting values
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- specifiers, watch variable format
- QuickWatch dialog box, format specifiers in C#
- specifiers
- watch variable symbols
- Watch window, format specifiers in C#
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 345c8589-5f36-4d34-a58c-e56271687dd6
caps.latest.revision: 34
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 27c3dcf59068ca511f52850e328ef186c22b3dfa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683334"
---
# <a name="format-specifiers-in-c"></a>Specifikátory formátu v jazyce C# #
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [specifikátory formátu v jazyce C#](https://docs.microsoft.com/visualstudio/debugger/format-specifiers-in-csharp).  
  
Můžete změnit formát, ve kterém se zobrazí hodnota v **Watch** okna pomocí specifikátorů formátu. Můžete také použít specifikátory formátu v **okamžité** okně **příkaz** okna a dokonce i ve zdrojových oknech. Pokud pozastavíte výraz v těchto oknech, výsledek se zobrazí v datovém tipu. Datové tipy budou odrážet formát specifikátoru v zobrazení datového tipu.  
  
 Použití specifikátoru formátu, zadejte výraz, za nímž následuje čárka. Za čárkou přidejte odpovídající specifikátor.  
  
## <a name="using-format-specifiers"></a>Použití specifikátorů formátu  
 Pokud máte následující kód:  
  
```  
{  
        int my_var1 = 0x0065;  
        int my_var2 = 0x0066;  
        int my_var3 = 0x0067;  
}  
```  
  
 Přidat `my_var1` proměnné okno kukátka (při ladění, **ladění / Windows / sledovat / sledovat 1**) a nastavte zobrazení do šestnáctkové soustavy (v **Watch** okna, klikněte pravým tlačítkem na proměnnou a vyberte **Hexadecimální zobrazení**). Nyní **Watch** okno zobrazuje, že obsahuje hodnotu 0x0065. Chcete-li zobrazit tuto hodnotu vyjádřenou jako desítkové celé číslo místo šestnáctkové celé číslo, ve sloupci Název za název proměnné, přidejte specifikátor formátu desítkové soustavy: **, d**. Sloupec hodnota nyní zobrazuje desítkovou hodnotu 101  
  
 ![WatchFormatCSharp](../debugger/media/watchformatcsharp.png "WatchFormatCSharp")  
  
## <a name="format-specifiers"></a>Specifikátory formátu  
 V následující tabulce jsou uvedeny C# specifikátory formátu rozpoznán v ladicím programu.  
  
|Specifikátor|Formát|Původní hodnota Watch|Zobrazí|  
|---------------|------------|--------------------------|--------------|  
|ac|Vynucení vyhodnocení výrazu. To může být užitečné, když je vypnutý implicitní vyhodnocování vlastností a implicitních volání funkcí. Zobrazit [vedlejší efekty a výrazy](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e).|Zpráva "implicitní vyhodnocení funkce vypnul uživatel"|\<Hodnota >|  
|d|desítkové celé číslo|0x0065|101|  
|dynamické odkazy|Zobrazí zadaný objekt pomocí dynamického zobrazení|Zobrazí všechny členy objektu, včetně dynamického zobrazení|Zobrazí pouze dynamické zobrazení|  
|h|Šestnáctkové celé číslo|61541|0x0000F065|  
|NQ|řetězec s žádné uvozovky|"String"|Moje řetězec|  
|hidden|Zobrazí všechny veřejné a neveřejné členy|Zobrazí veřejné členy|Zobrazí všechny členy|  
|nezpracované|Zobrazí položky, jak se zobrazí v uzlu nezpracovaná položka. Platí pouze pro objekty proxy.|Slovník\<T >|Nezpracované zobrazení, slovníku\<T >|  
|výsledky|Použít s proměnnou typu, který implementuje rozhraní IEnumerable nebo IEnumerable\<T >, obvykle výsledek výrazu dotazu. Zobrazí pouze členy, které obsahují výsledku dotazu.|Zobrazí všechny členy.|Zobrazí členy, splňují podmínky dotazu.|  
  
## <a name="see-also"></a>Viz také  
 [Kukátko a Rychlé kukátko Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Proměnné Windows](http://msdn.microsoft.com/library/ce0a67f6-2502-4b7a-ba45-cc32f8aeba3e)





