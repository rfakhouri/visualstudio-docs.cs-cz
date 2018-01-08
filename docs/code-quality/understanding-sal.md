---
title: "Porozumění SAL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 196bfdbeeda00199861ea2f676553f024fcaf98f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="understanding-sal"></a>Porozumění SAL
Poznámky jazyk zdrojového kódu Microsoft (SAL) poskytuje sadu poznámky, které lze použít k popisu, jak funkce používá jeho parametrů, předpokladů, které umožňuje o nich a záruky, které umožňuje po dokončení. Poznámky jsou definovány v záhlaví souboru `<sal.h>`. Visual Studio analýzy kódu pro jazyk C++ používá poznámek SAL k úpravě jeho analýzu funkce. Další informace o SAL 2.0 ovladače pro vývoj pro Windows najdete v tématu [poznámky SAL 2.0 pro Windows ovladače](http://go.microsoft.com/fwlink/?LinkId=250979).  
  
 C a C++ nativně, zadejte jenom omezené způsoby vývojářům konzistentně express záměr a invariance. Pomocí poznámek SAL můžete popsat funkcí podrobněji tak, aby vývojáři, kteří je spotřebovávají můžete lépe pochopili, jak je používat.  
  
## <a name="what-is-sal-and-why-should-you-use-it"></a>Co je SAL a proč ho používat?  
 Jednoduše řečeno, SAL je levný způsob, jak umožnit kompilátoru kontrolovat kódu.  
  
### <a name="sal-makes-code-more-valuable"></a>SAL snižuje Code více  
 SAL usnadňuje návrhu kód srozumitelnější, pro člověka i pro nástrojů pro analýzu kódu. Vezměte v úvahu tento příklad, který ukazuje funkci C runtime `memcpy`:  
  
```cpp  
  
void * memcpy(  
   void *dest,   
   const void *src,   
   size_t count  
);  
  
```  
  
 Zjistit, co tato funkce dělá? Pokud funkce je implementována nebo volat, musí být zachovaná některé vlastnosti zajistit správnost programu. Podle vzhledu deklaraci, jako je třeba v příkladu, nevíte, co jsou. Bez SAL – poznámky museli byste tedy spoléhat na dokumentaci nebo komentáře kódu. Tady je co v MSDN dokumentaci pro `memcpy` uvádí:  
  
> "Kopie počet bajtů src do cíle. Pokud zdrojové a cílové překrývají, chování memcpy není definován. Memmove – použijte ke zpracování překrývající se oblasti.   
> **Poznámka k zabezpečení:** Ujistěte se, že cílová vyrovnávací paměť je stejný, velké nebo větší než zdrojová vyrovnávací paměť. Další informace najdete v tématu zabraňující způsobí přetečení vyrovnávací paměti."  
  
 Dokumentace obsahuje několik bits informace, které naznačují, že má váš kód k udržování určité vlastnosti zajistit správnost program:  
  
-   `memcpy`kopie `count` bajty z vyrovnávací paměti zdrojové a cílové vyrovnávací paměti.  
  
-   Cílová vyrovnávací paměť musí být alespoň tak velké, jaká zdrojová vyrovnávací paměť.  
  
 Kompilátor však nelze přečíst, dokumentace nebo neformální komentáře. Není známo, že je vztah mezi dvěma vyrovnávací paměti a `count`, a je také nelze snadno uhodnout efektivně o vztahu. SAL může poskytovat další přehlednost o vlastnostech a implementace funkce, jak je vidět tady:  
  
```cpp  
  
void * memcpy(  
   _Out_writes_bytes_all_(count) void *dest,   
   _In_reads_bytes_(count) const void *src,   
   size_t count  
);  
```  
  
 Všimněte si, že tyto poznámky připomínají informace v dokumentaci k webu MSDN, ale jsou přesnější a se řídí sémantického vzor. Při čtení tento kód můžete rychle pochopit vlastnosti této funkce a jak se vyhnout problémy se zabezpečením přetečení vyrovnávací paměti. I lépe sémantického vzorů, které poskytuje SAL může zvýšit efektivitu nástrojů pro analýzu automatizované kódu v časná zjišťování potenciální chyby. Představte si, že někdo zapisuje tato buggy implementace `wmemcpy`:  
  
```cpp  
  
wchar_t * wmemcpy(  
   _Out_writes_all_(count) wchar_t *dest,   
   _In_reads_(count) const wchar_t *src,   
   size_t count)  
{  
   size_t i;  
   for (i = 0; i <= count; i++) { // BUG: off-by-one error  
      dest[i] = src[i];  
   }  
   return dest;  
}  
  
```  
  
 Tato implementace obsahuje běžnou chybou vypnout po druhém. Naštěstí kódu Autor zahrnuté poznámky SAL vyrovnávací paměti velikost – nástroj pro analýzu kódu může catch chybě analýzou tuto funkci samostatně.  
  
### <a name="sal-basics"></a>Základy SAL  
 SAL definuje čtyři základní typy parametrů, které jsou klasifikovány podle vzor používání.  
  
|Kategorie|Parametr poznámky|Popis|  
|--------------|--------------------------|-----------------|  
|**Volá se vstup do funkce**|`_In_`|Data je předán volaná funkce a považuje jen pro čtení.|  
|**Volal funkci vstup a výstup volajícího**|`_Inout_`|Použitelné dat je předána do funkce a potenciálně je změnit.|  
|**Výstup volajícího**|`_Out_`|Volající pouze místo volaná funkce k zápisu. Volaná funkce zapíše data do tohoto prostoru.|  
|**Výstup ukazatele volajícího**|`_Outptr_`|Jako **výstup volajícího**. Hodnota, kterou vrátí volaná funkce je ukazatel.|  
  
 Tyto čtyři základní poznámky můžete provést podrobnější různými způsoby. Ve výchozím nastavení, parametry s poznámkami ukazatel se předpokládá, že bude vyžadovat – musí být jinou hodnotu než NULL pro funkce proběhla úspěšně. Nejčastěji používané variantu základní poznámky označuje, že je volitelný parametr ukazatele – Pokud je hodnota NULL, funkce může být přesto úspěšné, v jeho pracuje.  
  
 Tato tabulka ukazuje, jak k rozlišení mezi povinných a volitelných parametrů:  
  
||Jsou vyžadovány parametry|Parametry jsou volitelné.|  
|-|-----------------------------|-----------------------------|  
|**Volá se vstup do funkce**|`_In_`|`_In_opt_`|  
|**Volal funkci vstup a výstup volajícího**|`_Inout_`|`_Inout_opt_`|  
|**Výstup volajícího**|`_Out_`|`_Out_opt_`|  
|**Výstup ukazatele volajícího**|`_Outptr_`|`_Outptr_opt_`|  
  
 Tyto poznámky identifikaci možné Neinicializovaný hodnoty a neplatné ukazatele null používá formální a přesná způsobem. Předání hodnotou NULL pro požadovaný parametr může způsobit selhání, nebo může způsobit kód "se nezdařilo" chyby má být vrácen. V obou případech funkce nelze úspěšně dokončit v provádění úlohy.  
  
## <a name="sal-examples"></a>Příklady SAL  
 Tato část uvádí příklady kódu pro základní poznámek SAL.  
  
### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Nástroj pro analýzu kódu sadě Visual Studio pomocí najít závad  
 V příkladech je nástroj pro analýzu kódu Visual Studio použít společně s poznámek SAL k vyhledání závad v kódu. Chcete-li to udělat.  
  
##### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>Použití nástrojů pro analýzu kódu aplikace Visual Studio a SAL  
  
1.  V sadě Visual Studio otevřete projekt C++, který obsahuje poznámek SAL.  
  
2.  Na řádku nabídek zvolte **sestavení**, **spustit analýza kódu v řešení**.  
  
     Vezměte v úvahu _In\_ příklad v této části. Pokud v něm spustíte analýza kódu, toto upozornění se zobrazí:  
  
    > **C6387 Neplatná hodnota parametru**   
    > 'pinta, může být '0': to není ve správném specifikace pro funkci 'InCallee'.  
  
### <a name="example-the-in-annotation"></a>Příklad: _In\_ – Poznámka  
 `_In_` Poznámky znamená, že:  
  
-   Parametr musí být platné a se nezmění.  
  
-   Funkce bude číst jenom z jedné položce vyrovnávací paměti.  
  
-   Volající musí poskytnout vyrovnávací paměti a provést jeho inicializaci.  
  
-   `_In_`Určuje "jen pro čtení". Obvyklou chybou, je použít `_In_` parametr, který by měl být `_Inout_` poznámky místo.  
  
-   `_In_`je povolen, ale ignorovat analyzátor na jiný ukazatel skalárních hodnot.  
  
```cpp  
void InCallee(_In_ int *pInt)  
{  
   int i = *pInt;  
}  
  
void GoodInCaller()  
{  
   int *pInt = new int;  
   *pInt = 5;  
  
   InCallee(pInt);  
   delete pInt;     
}  
  
void BadInCaller()  
{  
   int *pInt = NULL;  
   InCallee(pInt); // pInt should not be NULL  
}  
  
```  
  
 Pokud používáte Visual Studio analýza kódu v tomto příkladu, ověřuje, že volající předat inicializovaného velikost vyrovnávací paměti pro ukazatel nesmí být nulová `pInt`. V takovém případě `pInt` ukazatel nemůže mít hodnotu NULL.  
  
### <a name="example-the-inopt-annotation"></a>Příklad: _In_opt\_ – Poznámka  
 `_In_opt_`je stejný jako `_In_`kromě toho, že vstupní parametr může mít hodnotu NULL, a proto měli zkontrolovat funkce pro tento.  
  
```cpp  
  
void GoodInOptCallee(_In_opt_ int *pInt)  
{  
   if(pInt != NULL) {  
      int i = *pInt;  
   }  
}  
  
void BadInOptCallee(_In_opt_ int *pInt)  
{  
   int i = *pInt; // Dereferencing NULL pointer 'pInt'  
}  
  
void InOptCaller()  
{  
   int *pInt = NULL;  
   GoodInOptCallee(pInt);  
   BadInOptCallee(pInt);  
}  
  
```  
  
 Analýza kódu Visual Studio ověří, že funkce vyhledává NULL před přistupuje k vyrovnávací paměti.  
  
### <a name="example-the-out-annotation"></a>Příklad: _Out\_ – Poznámka  
 `_Out_`podporuje běžný scénář, ve kterém je ukazatel jinou hodnotu než NULL, který odkazuje na element vyrovnávací paměť předaná a funkce inicializuje elementu. Volající nemá k chybě při inicializaci vyrovnávací paměti před voláním; Umožňuje provést jeho inicializaci předtím, než se vrátí, nabízí volaná funkce.  
  
```cpp  
  
void GoodOutCallee(_Out_ int *pInt)  
{  
   *pInt = 5;  
}  
  
void BadOutCallee(_Out_ int *pInt)  
{  
   // Did not initialize pInt buffer before returning!  
}  
  
void OutCaller()  
{  
   int *pInt = new int;  
   GoodOutCallee(pInt);  
   BadOutCallee(pInt);  
   delete pInt;  
}  
  
```  
  
 Visual Studio nástroj pro analýzu kódu ověří, že volající předá do vyrovnávací paměti pro jinou hodnotu než NULL ukazatel `pInt` a že vyrovnávací paměť se inicializuje pomocí funkce před vrátí.  
  
### <a name="example-the-outopt-annotation"></a>Příklad: _Out_opt\_ – Poznámka  
 `_Out_opt_`je stejný jako `_Out_`kromě toho, že je parametr povoleno na hodnotu NULL, a proto by zkontrolujte funkce, pro tento.  
  
```cpp  
  
void GoodOutOptCallee(_Out_opt_ int *pInt)  
{  
   if (pInt != NULL) {  
      *pInt = 5;  
   }  
}  
  
void BadOutOptCallee(_Out_opt_ int *pInt)  
{  
   *pInt = 5; // Dereferencing NULL pointer 'pInt'  
}  
  
void OutOptCaller()  
{  
   int *pInt = NULL;  
   GoodOutOptCallee(pInt);  
   BadOutOptCallee(pInt);  
}  
  
```  
  
 Analýza kódu Visual Studio ověří, že tato funkce zkontroluje NULL před `pInt` je přímo odkázat a pokud `pInt` nemá hodnotu NULL, že vyrovnávací paměť se inicializuje pomocí funkce před vrátí.  
  
### <a name="example-the-inout-annotation"></a>Příklad: _inout –\_ – Poznámka  
 `_Inout_`slouží k přidání poznámek ke ukazatel parametr, který může být změněna funkce. Ukazatele musí odkazovat na platný inicializovaného data před voláním a i když se změní, musí mít platnou hodnotu stále na vrátit. Poznámka Určuje, že funkce může volně číst z a zapsat do vyrovnávací paměti jeden element. Volající musí poskytnout vyrovnávací paměti a provést jeho inicializaci.  
  
> [!NOTE]
>  Jako `_Out_`, `_Inout_` se musí vztahovat na upravitelnými hodnotu.  
  
```cpp  
  
void InOutCallee(_Inout_ int *pInt)  
{  
   int i = *pInt;  
   *pInt = 6;  
}  
  
void InOutCaller()  
{  
   int *pInt = new int;  
   *pInt = 5;  
   InOutCallee(pInt);  
   delete pInt;  
}  
  
void BadInOutCaller()  
{  
   int *pInt = NULL;  
   InOutCallee(pInt); // 'pInt' should not be NULL  
}  
  
```  
  
 Visual Studio Code Analysis ověří, že volající předat inicializovaného velikost vyrovnávací paměti pro jinou hodnotu než NULL ukazatel `pInt`a že před return `pInt` stále není prázdné a vyrovnávací paměť je inicializován.  
  
### <a name="example-the-inoutopt-annotation"></a>Příklad: _Inout_opt\_ – Poznámka  
 `_Inout_opt_`je stejný jako `_Inout_`kromě toho, že vstupní parametr může mít hodnotu NULL, a proto měli zkontrolovat funkce pro tento.  
  
```cpp  
  
void GoodInOutOptCallee(_Inout_opt_ int *pInt)  
{  
   if(pInt != NULL) {  
      int i = *pInt;  
      *pInt = 6;  
   }  
}  
  
void BadInOutOptCallee(_Inout_opt_ int *pInt)  
{  
   int i = *pInt; // Dereferencing NULL pointer 'pInt'  
   *pInt = 6;  
}  
  
void InOutOptCaller()  
{  
   int *pInt = NULL;  
   GoodInOutOptCallee(pInt);  
   BadInOutOptCallee(pInt);  
}  
  
```  
  
 Analýza kódu Visual Studio ověří, že tato funkce zkontroluje NULL před přistupuje k vyrovnávací paměť a pokud `pInt` nemá hodnotu NULL, že vyrovnávací paměť se inicializuje pomocí funkce před vrátí.  
  
### <a name="example-the-outptr-annotation"></a>Příklad: _Outptr\_ – Poznámka  
 `_Outptr_`slouží k přidání poznámek ke parametr, který se má vrátit ukazatel.  Parametr samotné nesmí mít hodnotu NULL a volaná funkce vrátí ukazatel jinou hodnotu než NULL a tento ukazatel odkazuje na inicializovaného data.  
  
```cpp  
  
void GoodOutPtrCallee(_Outptr_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 5;  
  
   *pInt = pInt2;  
}  
  
void BadOutPtrCallee(_Outptr_ int **pInt)  
{  
   int *pInt2 = new int;  
   // Did not initialize pInt buffer before returning!  
   *pInt = pInt2;  
}  
  
void OutPtrCaller()  
{  
   int *pInt = NULL;  
   GoodOutPtrCallee(&pInt);  
   BadOutPtrCallee(&pInt);  
}  
  
```  
  
 Analýza kódu Visual Studio ověří, že volající předá ukazatel jinou hodnotu než NULL `*pInt`, a že vyrovnávací paměť se inicializuje pomocí funkce před vrátí.  
  
### <a name="example-the-outptropt-annotation"></a>Příklad: _Outptr_opt\_ – Poznámka  
 `_Outptr_opt_`je stejný jako `_Outptr_`kromě toho, že se jedná o volitelný parametr – volající můžete předat ukazatele s hodnotou NULL pro parametr.  
  
```cpp  
  
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 6;  
  
   if(pInt != NULL) {  
      *pInt = pInt2;  
   }  
}  
  
void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 6;  
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'  
}  
  
void OutPtrOptCaller()  
{  
   int **ppInt = NULL;  
   GoodOutPtrOptCallee(ppInt);  
   BadOutPtrOptCallee(ppInt);  
}  
  
```  
  
 Analýza kódu Visual Studio ověří, že tato funkce zkontroluje NULL před `*pInt` je přímo odkázat, a že vyrovnávací paměť se inicializuje pomocí funkce před vrátí.  
  
### <a name="example-the-success-annotation-in-combination-with-out"></a>Příklad: _Success\_ poznámky v kombinaci s _Out\_  
 Poznámky je použít pro většinu objektů.  Konkrétně může opatřit poznámkami celou funkci.  Jedním z nejobvyklejší charakteristiky funkce je, že ji úspěch nebo neúspěch. Ale jako přidružení mezi vyrovnávací paměť a její velikost, nelze C/C++ express funkce úspěch nebo selhání. Pomocí `_Success_` poznámky, řekněte vypadá jaké úspěch pro funkci.  Pomocí parametru `_Success_` poznámky je právě výraz, když to není pravda označuje, že funkce proběhl úspěšně. Výraz může být cokoli, co může zpracovat analyzátor poznámky. Důsledky poznámky po vrácení funkce se dají použít jenom, když funkce úspěšné. Tento příklad ukazuje, jak `_Success_` komunikuje s `_Out_` udělat správné věci. Můžete použít klíčové slovo `return` představují návratovou hodnotu.  
  
```cpp  
  
_Success_(return != false) // Can also be stated as _Success_(return)  
bool GetValue(_Out_ int *pInt, bool flag)  
{  
   if(flag) {  
      *pInt = 5;  
      return true;  
   } else {  
      return false;  
   }  
}  
  
```  
  
 `_Out_` Poznámky způsobí, že Visual Studio analýza kódu k ověření, volající předá do vyrovnávací paměti pro jinou hodnotu než NULL ukazatel `pInt`, a že vyrovnávací paměť se inicializuje pomocí funkce před vrátí.  
  
## <a name="sal-best-practice"></a>Osvědčeným postupem SAL  
  
### <a name="adding-annotations-to-existing-code"></a>Přidání poznámky do existujícího kódu  
 SAL je výkonná technologie, která vám může pomoct zlepšit zabezpečení a spolehlivost kódu. Po dozvíte SAL, můžete použít nové dovednosti pro každodenní práci. V nový kód můžete na základě SAL specifikace návrhu v celé; ve starším kódu můžete přidat poznámky postupně a tím zvýšit výhody při každé aktualizaci.  
  
 Microsoft veřejné hlavičky jsou již poznámky. Doporučujeme proto, že v projektech nejprve přidávat poznámky funkce uzel typu list a funkce, které volat rozhraní API Win32 pro využívat výhod.  
  
### <a name="when-do-i-annotate"></a>Když anotaci?  
 Zde je několik doporučení:  
  
-   Přidání poznámek ke všechny parametry ukazatele.  
  
-   Tak, aby analýza kódu můžete zajistit bezpečnost vyrovnávací paměti a ukazatel opatřit poznámkami poznámky rozsah hodnot.  
  
-   Přidání poznámek ke uzamčení pravidla a uzamčení vedlejší účinky. Další informace najdete v tématu [zadávání poznámek k chování při zamykání](../code-quality/annotating-locking-behavior.md).  
  
-   Přidání poznámek ke vlastnosti ovladače a další vlastnosti specifické pro doménu.  
  
 Nebo může opatřit poznámkami všechny parametry, aby se v celé vaší záměrné zaškrtnutí a usnadňují zkontrolujte, že jsou prováděny poznámky.  
  
## <a name="related-resources"></a>Související informační zdroje  
 [Blog týmu analýzy kódu](http://go.microsoft.com/fwlink/p/?LinkId=251197)  
  
## <a name="see-also"></a>Viz také  
 [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)   
 [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)   
 [Zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)   
 [Zadávání poznámek k chování při zamykání](../code-quality/annotating-locking-behavior.md)   
 [Určení, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [Osvědčené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)