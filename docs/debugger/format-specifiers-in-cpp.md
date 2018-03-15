---
title: "Specifikátory v ladicím programu (C++) formátu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- QuickWatch dialog box, format specifiers in C++
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- expressions [C++], format specifiers
- specifiers, watch variable format
- specifiers
- Watch window, format specifiers in C++
- watch variable symbols
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 0f6f3b7c-ce2c-4b4d-b14f-7589dbed5444
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b7efb90e6f2a2489fffb890c664393252021e6f
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="format-specifiers-in-c-in-the-visual-studio-debugger"></a>Specifikátory formátu v jazyce C++ v ladicím programu sady Visual Studio
Formát, ve kterém je zobrazená hodnota v lze změnit **sledovat** okno použití specifikátorů formátu.  
  
 Můžete také použít specifikátory formátu v **Immediate** okně **příkaz** okno v [tracepoints](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints)a to i v systému windows zdroje. Pokud přesunutí ukazatele myši na výrazu v těchto windows, zobrazí se v datového tipu výsledek. Popis dat zobrazení odráží specifikátor formátu.  
  
> [!NOTE]
>  Při nativní ladicí program Visual Studio na nový modul ladění, byly přidány některé nové specifikátory formátu a některé staré byly odebrány. Starší ladicí program je stále používán, když se zprostředkovatel komunikace s objekty (smíšená nativní a spravovaná) ladění pomocí C + +/ CLI. Následující části v tomto tématu ukazují specifikátory formátu pro každý motor ladění.
>   
>  -   [Specifikátory formátu](#BKMK_Visual_Studio_2012_format_specifiers) popisuje specifikátory formátu v nový modul ladění.  
> -   [Specifikátory formátu pro ladění spolupráce s C + +/ CLI](#BKMK_Format_specifiers_for_interop_debugging_and_C___edit_and_continue) popisuje specifikátory formátu v starší modul ladění.  
  
## <a name="using-format-specifiers"></a>Použití specifikátorů formátu  
 Pokud máte následující kód:  
  
```C++  
int main() {  
    int my_var1 = 0x0065;  
    int my_var2 = 0x0066;  
    int my_var3 = 0x0067;  
}  
```  
  
 Přidat `my_var1` proměnnou **sledovat** okno (při ladění, **ladění > Windows > sledovat > sledovat 1**) a poté nastavte zobrazení na šestnáctkové (v **sledovat**okně proměnné klikněte pravým tlačítkem a vyberte **hexadecimální zobrazení**). Okno kukátka nyní zobrazuje, že obsahuje hodnotu 0x0065. Tato hodnota, vyjádřené jako znak místo celé číslo ve sloupci Název po názvu proměnné najdete v části Přidání specifikátor formátu znak **c**. **Hodnotu** sloupec se teď zobrazí s **101 "e"**.  
  
 ![WatchFormatCPlus1](../debugger/media/watchformatcplus1.png "WatchFormatCPlus1")  
  
##  <a name="BKMK_Visual_Studio_2012_format_specifiers"></a> Specifikátory formátu  
 Následující tabulky popisují specifikátory formátu, které můžete v sadě Visual Studio. Specifikátory tučným písmem nejsou podporované pro zprostředkovatele komunikace s objekty ladění pomocí C + +/ CLI.  
  
|Specifikátor|Formát|Původní hodnotu sledování|Zobrazené hodnoty|  
|---------------|------------|--------------------------|---------------------|  
|d|desítkové celé číslo|0x00000066|102|  
|o|osmičkové celé číslo bez znaménka|0x00000066|000000000146|  
|x<br /><br /> **h**|hexadecimální celé číslo|102|0xcccccccc|  
|X<br /><br /> **H**|hexadecimální celé číslo|102|0xCCCCCCCC|  
|c|jeden znak|0x0065, c|101 "e"|  
|s|const char * řetězce|\<umístění > "hello, world"|"hello, world"|  
|**sb**|const char * řetězec (bez uvozovek)|\<umístění > "hello, world"|Ahoj světe|  
|s8|Řetězec ve formátu UTF-8|\<umístění > "Toto je â˜• Šálek kávy UTF-8"|"Toto je ☕ Šálek kávy UTF-8"|
|**s8b**|Řetězec ve formátu UTF-8 (bez uvozovek)|\<umístění > "hello, world"|Ahoj světe|  
|su|Řetězec znaků Unicode (kódování UTF-16)|\<umístění > L "hello, world"|L "hello, world"<br /><br /> U "hello world"|  
|Sub –|Řetězec znaků Unicode (kódování UTF-16) (bez uvozovek)|\<umístění > L "hello, world"|Ahoj světe|  
|bstr|Řetězce BSTR|\<umístění > L "hello, world"|L "hello, world"|  
|env|Blok prostředí (ukončenou řetězec dvojitou hodnotu null)|\<umístění > L "=:: =::\\\\"|L "=:: =::\\\\\\0 = C: = C:\\\\windows\\\\system32\\0ALLUSERSPROFILE =...|
|**s32**|Řetězec ve formátu UTF-32|\<umístění > U "hello world"|U "hello world"|  
|**s32b**|Znakové sady UTF-32 řetězec (bez uvozovek)|\<umístění > U "hello world"|Ahoj světe|  
|**en**|enum|Saturday(6)|Sobota|  
|**hv**|Typ ukazatele – označuje, že hodnota ukazatele ke kontrole je výsledek přidělení haldy pole, například `new int[3]`.|\<umístění > {\<první člen >}|\<umístění > {\<první člen >, \<druhý člen >,...}|  
|**na**|Potlačí adresa paměti ukazatele na objekt.|\<umístění >, {člen = hodnota...}|{{člen = hodnota...}|  
|**ND**|Zobrazí pouze základní třída informace, ignoruje odvozené třídy|`(Shape*) square` obsahuje základní třída a odvozené informace o třídě|Zobrazí pouze základní informace o třídě|  
|personální oddělení|Kód chyby HRESULT nebo Win32. (Ladicí program nyní dekóduje hodnoty HRESULT automaticky, takže tento specifikátor nevyžaduje v těchto případech.|S_OK|S_OK|  
|wc|Příznak okno – třída|0x0010|WC_DEFAULTCHAR|  
|wm|Čísla zpráv Windows|16|FUNKCE WM_CLOSE BUDE|  
|!|formátu RAW, ignoruje veškerá přizpůsobení zobrazení typu dat|\<přizpůsobit reprezentace >|4|  
  
> [!NOTE]
>  Když **hv** specifikátor formátu přítomen, ladicí program se pokusí zjistit délka vyrovnávací paměti a zobrazí odpovídající počet elementů. Protože vždy není možné v ladicím programu najít přesnou vyrovnávací paměti velikost pole, měli byste používat specifikátor velikosti `(pBuffer,[bufferSize])` kdykoli je to možné. **Hv** specifikátor formátu je určený pro scénáře, kde velikost vyrovnávací paměti není snadno dostupné  
  
###  <a name="BKMK_Size_specifiers_for_pointers_as_arrays_in_Visual_Studio_2012"></a> Specifikátory velikost pro ukazatele jako pole  
 Pokud máte ukazatel na objekt, který chcete zobrazit jako pole, můžete použít celé číslo nebo výraz zadat počet elementů pole:  
  
|Specifikátor|Formát|Původní hodnotu sledování|Zobrazené hodnoty|  
|---------------|------------|---------------------------|---------------------|  
|n|Decimal nebo **hexadecimální** celé číslo|pBuffer [32]<br /><br /> pBuffer,**[0x20]**|Zobrazí `pBuffer` jako 32 element pole.|  
|**[exp]**|Platný výraz C++, který se vyhodnotí na celé číslo.|pBuffer [bufferSize]|Zobrazí pBuffer jako pole `bufferSize` elementy.|  
|**expand(n)**|Platný výraz C++, který se vyhodnotí na celé číslo|pBuffer, expand(2)|Zobrazí třetí elementu  `pBuffer`|  
  
##  <a name="BKMK_Format_specifiers_for_interop_debugging_and_C___edit_and_continue"></a> Specifikátory formátu pro ladění spolupráce s C + +/ CLI  
 Specifikátory v **tučné** jsou podporovány pouze pro ladění nativní a C + +/ CLI kódu.  
  
|Specifikátor|Formát|Původní hodnotu sledování|Zobrazené hodnoty|  
|---------------|------------|--------------------------|---------------------|  
|**d, i**|desetinné číslo se znaménkem|0xF000F065|-268373915|  
|**u**|celé číslo bez znaménka decimal|0x0065|101|  
|o|osmičkové celé číslo bez znaménka|0xF065|0170145|  
|x,X|hexadecimální celé číslo|61541|0x0000f065|  
|**l,h**|dlouhé nebo krátké předponu pro: d, i u, o x X|00406042|0x0c22|  
|**f**|podepsané plovoucí desetinné čárky|(3./2.), f|1.500000|  
|**e**|podepsaného vědecká notace|(3.0/2.0)|1.500000e + 000|  
|**g**|podepsané plovoucí desetinnou čárkou nebo podepsané exponenciální notace, podle toho, co je kratší|(3.0/2.0)|1.5|  
|c|jeden znak|\<umístění >|101 "e"|  
|s|const char *|\<umístění >|"hello, world"|  
|su|Const wchar_t *<br /><br /> Const char16_t\*|\<umístění >|L "hello, world"|  
|Sub –|Const wchar_t *<br /><br /> Const char16_t\*|\<umístění >|Ahoj světe|  
|s8|const char *|\<umístění >|"hello, world"|  
|personální oddělení|Kód chyby HRESULT nebo Win32. (Ladicí program nyní dekóduje hodnoty HRESULT automaticky, takže tento specifikátor nevyžaduje v těchto případech.|S_OK|S_OK|  
|wc|Okno třída příznak.|0x00000040,|WC_DEFAULTCHAR|  
|wm|Čísla zpráv Windows|0x0010|FUNKCE WM_CLOSE BUDE|  
|!|formátu RAW, ignoruje veškerá přizpůsobení zobrazení typu dat|\<přizpůsobit reprezentace >|4|  
  
###  <a name="BKMK_Format_specifiers_memory_locations_in_interop_debugging_and_C___edit_and_continue"></a> Formátování specifikátory umístění v paměti v spolupráce ladění pomocí C + +/ CLI  
 Následující tabulka obsahuje formátování symboly použité pro umístění v paměti. Můžete vytvořit specifikátorem umístění paměti se všechny hodnoty nebo výrazy, které vyhodnotí do umístění.  
  
|Symbol|Formát|Původní hodnotu sledování|Zobrazené hodnoty|  
|------------|------------|--------------------------|---------------------|  
|**ma**|64 znaků ASCII|0x0012ffac|0x0012ffac .4...0...".0W&.......1W&.0.:W..1...."..1.JO&.1.2.."..1...0y....1|  
|**m**|16 bajtů šestnáctkových číslic, za nímž následuje 16 znaků ASCII|0x0012ffac|0x0012ffac B3 34 CB 00 84 30 94 80 FF 22 8A 30 57 26 00 00 .4...0...".0W&..|  
|**mb**|16 bajtů šestnáctkových číslic, za nímž následuje 16 znaků ASCII|0x0012ffac|0x0012ffac B3 34 CB 00 84 30 94 80 FF 22 8A 30 57 26 00 00 .4...0...".0W&..|  
|**mw**|8 slova|0x0012ffac|0x0012ffac 34B3 00CB 3084 8094 22FF 308A 2657 0000|  
|**md**|4 doublewords|0x0012ffac|0x0012ffac 00CB34B3 80943084 308A22FF 00002657|  
|**mq**|2 quadwords|0x0012ffac|0x0012ffac 7ffdf00000000000 5f441a790012fdd4|  
|**mu**|2bajtové znaky (Unicode)|0x0012ffac|0x0012ffac 8478 77f4 ffff ffff 0000 0000 0000 0000|  
  
###  <a name="BKMK_Size_specifier_for_pointers_as_arrays_in_interop_debugging_and_C___edit_and_continue"></a> Specifikátor velikosti pro ukazatele jako pole ve spolupráce ladění pomocí C + +/ CLI  
 Pokud máte ukazatel na objekt, který chcete zobrazit jako pole, můžete zadat počet elementů pole celé číslo:  
  
|Specifikátor|Formát|Výraz|Zobrazené hodnoty|  
|---------------|------------|----------------|---------------------|  
|n|desítkové celé číslo|pBuffer[32]|Zobrazí `pBuffer` jako 32 element pole.|
