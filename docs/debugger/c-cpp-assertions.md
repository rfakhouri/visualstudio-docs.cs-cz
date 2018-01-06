---
title: "Kontrolní výrazy jazyka C/C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [MFC], assertions
- results, checking
- result checking
- Call Stack window, assertion failures
- debugging [C++], assertions
- VERIFY macro
- assertions, side effects
- assertions
- ASSERT macro
- errors [C++], catching with assertions
- testing, error conditions with assertion statements
- _DEBUG macro
- Assertion Failed dialog box
- failures, finding locations
ms.assetid: 2d7b0121-71aa-414b-bbb6-ede1093d0bfc
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46ea417ccd8b4dbecd0c6584699e9f2e98330d69
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cc-assertions"></a>Kontrolní výrazy jazyka C/C++
Příkaz assertion Určuje podmínku, která byste měli mít hodnotu true v okamžiku v programu. Pokud není tato podmínka true, kontrolní výraz selže, provádění vašeho programu přeruší a [dialogové okno kontrolní výraz](../debugger/assertion-failed-dialog-box.md) se zobrazí.  
  
 Visual C++ podporuje assertion příkazy, které jsou založeny na následující konstrukce:  
  
-   Kontrolní výrazy MFC MFC programů.  
  
-   [ATLASSERT](http://msdn.microsoft.com/Library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3) pro programy, které používají knihovnu ATL.  
  
-   Kontrolní výrazy CRT pro programy, které používají běhové knihovny jazyka C.  
  
-   ANSI [assert funkce](/cpp/c-runtime-library/reference/assert-macro-assert-wassert) pro jiné programy C/C++.  
  
 Kontrolní výrazy můžete použít pro zachycení logiku chyb, zkontrolujte výsledky operace a testování chybové stavy, které by byly zpracovány.  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [Jak fungují kontrolní výrazy](#BKMK_How_assertions_work)  
  
 [Kontrolní výrazy v sestavení pro ladění a vydání](#BKMK_Assertions_in_Debug_and_Release_builds)  
  
 [Vedlejší efekty použití kontrolní výrazy](#BKMK_Side_effects_of_using_assertions)  
  
 [Kontrolní výrazy CRT](#BKMK_CRT_assertions)  
  
 [Kontrolní výrazy MFC](#BKMK_MFC_assertions)  
  
-   [Assert_valid – MFC a CObject::AssertValid](#BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid)  
  
-   [Omezení AssertValid](#BKMK_Limitations_of_AssertValid)  
  
 [Pomocí kontrolních výrazů](#BKMK_Using_assertions)  
  
-   [Zachytávání logické chyby](#BKMK_Catching_logic_errors)  
  
-   [Kontrola výsledků](#BKMK_Checking_results_)  
  
-   [Hledání neošetřené chyby](#BKMK_Testing_error_conditions_)  
  
##  <a name="BKMK_How_assertions_work"></a>Jak fungují kontrolní výrazy  
 Jakmile ladicí program zastaví z důvodu assertion běhové knihovny MFC nebo C, pak pokud je zdroj dostupný, ladicí program přejde do bodu ve zdrojovém souboru, kde došlo k chybě kontrolní výraz. Kontrolní výraz zpráva se zobrazí v obou [výstup – okno](../ide/reference/output-window.md) a **kontrolní výraz** dialogové okno. Můžete zkopírovat assertion zprávu od **výstup** okna okno text, pokud chcete uložit pro budoucí použití. **Výstup** okno může obsahovat další chybové zprávy. Zkontrolujte tyto zprávy pečlivě, protože poskytují různá vodítka na příčinu selhání kontrolní výraz.  
  
 Kontrolní výrazy použijte ke zjištění chyby během vývoje. Pravidlo můžete použijte jeden výraz pro každý předpokladů. Pokud budete předpokládat, že argument není NULL, například použijte kontrolní výrazy k testování této předpokladů.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Assertions_in_Debug_and_Release_builds"></a>Kontrolní výrazy v sestavení pro ladění a vydání  
 Kontrolní výraz příkazy zkompilovat pouze v případě `_DEBUG` je definována. Jinak kompilátor kontrolní výrazy jsou považovány za příkazy hodnotu null. Proto assertion příkazy Uložit bez režie nebo výkonu náklady v poslední verzi programu a umožňují nepoužívejte `#ifdef` direktivy.  
  
##  <a name="BKMK_Side_effects_of_using_assertions"></a>Vedlejší efekty použití kontrolní výrazy  
 Když přidáte kontrolní výrazy kódu, ujistěte se, že že kontrolní výrazy nemají vedlejší účinky. Zvažte například následující kontrolní výraz, který změní `nM` hodnotu:  
  
```  
ASSERT(nM++ > 0); // Don't do this!  
  
```  
  
 Protože `ASSERT` výraz, který není vyhodnocen ve verzi vašeho programu `nM` bude mít různé hodnoty v verze pro ladění a vydání. Nechcete-li tento problém v prostředí MFC, můžete použít [OVĚŘTE](http://msdn.microsoft.com/Library/3e1ab4ee-cbc7-4290-a777-c92f42ce7b96) makro místo `ASSERT`.  `VERIFY`vyhodnotí výraz ve všech verzích ale nekontroluje výsledek v prodejní verzi.  
  
 Být obzvláště opatrní při používání volání funkcí v příkazech kontrolní výraz, protože vyhodnocování funkce může mít neočekávané vedlejší účinky.  
  
```  
ASSERT ( myFnctn(0)==1 ) // unsafe if myFnctn has side effects  
VERIFY ( myFnctn(0)==1 ) // safe  
```  
  
 `VERIFY`volání `myFnctn` v ladění i vydání verze, takže se dá použít. Však pomocí `VERIFY` ukládá režii volání nepotřebné funkce ve verzi.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_CRT_assertions"></a>Kontrolní výrazy CRT  
 CRTDBG. Definuje soubor hlaviček H [_ASSERT a _asserte – makra](/cpp/c-runtime-library/reference/assert-asserte-assert-expr-macros) assertion kontroly.  
  
|– Makro|Výsledek|  
|-----------|------------|  
|`_ASSERT`|Pokud zadaný výraz vyhodnocena jako FALSE, soubor název a řádek číslo `_ASSERT`.|`_ASSERTE`|  
|`_ASSERTE`|Stejné jako `_ASSERT`, plus řetězcovou reprezentaci výraz, který byl prohlašovanou.|  
  
 `_ASSERTE`je mnohem snazší, protože oznámí uplatňovaná výraz, který je FALSE. To může být dost identifikovat problém bez odkazující na zdrojový kód. Ladicí verze aplikace však obsahuje řetězcová konstanta pro každý výraz prohlašovanou pomocí `_ASSERTE`. Pokud použijete mnoho `_ASSERTE` makra, tyto výrazy řetězec trvat až významné množství paměti. Pokud je to představovat problém, použijte `_ASSERT` uložit paměti.  
  
 Když `_DEBUG` je definována `_ASSERTE` makro je definován následujícím způsobem:  
  
```  
#define _ASSERTE(expr) \  
   do { \  
      if (!(expr) && (1 == _CrtDbgReport( \  
         _CRT_ASSERT, __FILE__, __LINE__, #expr))) \  
         _CrtDbgBreak(); \  
   } while (0)  
```  
  
 Pokud je výsledkem uplatňovaná výrazu na hodnotu FALSE, [_crtdbgreport –](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) je volána k hlášení assertion selhání (pomocí dialogového okna zprávy ve výchozím nastavení). Pokud se rozhodnete **opakujte** v dialogovém okně zpráva `_CrtDbgReport` vrátí hodnotu 1 a `_CrtDbgBreak` volá ladicí program prostřednictvím `DebugBreak`.  
  
### <a name="checking-for-heap-corruption"></a>Kontrola poškození haldy  
 Následující příklad používá [_crtcheckmemory –](/cpp/c-runtime-library/reference/crtcheckmemory) zkontrolujte poškození haldy:  
  
```  
_ASSERTE(_CrtCheckMemory());  
```  
  
### <a name="checking-pointer-validity"></a>Kontrola platnosti ukazatele  
 Následující příklad používá [_crtisvalidpointer –](/cpp/c-runtime-library/reference/crtisvalidpointer) k ověření, že paměti daný rozsah je platný pro čtení nebo zápis.  
  
```  
_ASSERTE(_CrtIsValidPointer( address, size, TRUE );  
```  
  
 Následující příklad používá [_crtisvalidheappointer –](/cpp/c-runtime-library/reference/crtisvalidheappointer) ověření ukazatel odkazuje na paměť v lokální haldy (halda vytvořen a spravován společností tuto instanci běhové knihovny jazyka C – knihovny DLL může mít svou vlastní instanci knihovny, a proto vlastní haldy, mimo haldě aplikace). Tento kontrolní výraz součásti zachytí není pouze hodnotu null nebo out-of-bounds adresy, ale také odkazy na statické proměnné, proměnné zásobníku a libovolná jiná paměť příchozí data.  
  
```  
_ASSERTE(_CrtIsValidPointer( myData );  
```  
  
### <a name="checking-a-memory-block"></a>Kontrola bloku paměti  
 Následující příklad používá [_crtismemoryblock –](/cpp/c-runtime-library/reference/crtismemoryblock) k ověřte, zda blok paměti je v lokální haldy a má platný blok typem.  
  
```  
_ASSERTE(_CrtIsMemoryBlock (myData, size, &requestNumber, &filename, &linenumber));  
```  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_MFC_assertions"></a>Kontrolní výrazy MFC  
 Definuje MFC [ASSERT](http://msdn.microsoft.com/Library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) makro assertion kontroly. Definuje také `MFC ASSERT_VALID` a `CObject::AssertValid` metody pro kontrolu vnitřní stav `CObject`-odvozené objektu.  
  
 Pokud v argumentu MFC `ASSERT` makro vyhodnocen jako nula nebo hodnotu false, makro zastaví spuštění programu a upozorní uživatele; jinak, pokračuje v provádění.  
  
 Když kontrolní výrazy selže, dialogové okno zpráva se zobrazuje název zdrojového souboru a číslo řádku kontrolní výraz. Pokud se rozhodnete opakování v dialogovém okně pole, volání [afxdebugbreak –](http://msdn.microsoft.com/Library/c4cd79b9-9327-4db5-a9d6-c4004a92aa30) způsobí, že provádění možnost proniknout do ladicího programu. V tomto okamžiku můžete prozkoumat zásobník volání a pomocí jiných zařízení ladicí program můžete určit, proč se nepodařilo kontrolní výraz. Pokud jste povolili [pouze za běhu ladění](../debugger/just-in-time-debugging-in-visual-studio.md)a ladicí program již nebyla spuštěna, dialogové okno můžete spustit ladicí program.  
  
 Následující příklad ukazuje, jak používat `ASSERT` Zkontrolujte návratovou hodnotu funkce:  
  
```  
int x = SomeFunc(y);  
ASSERT(x >= 0);   //  Assertion fails if x is negative  
```  
  
 Můžete použít ASSERT s [IsKindOf](/cpp/mfc/reference/cobject-class.md#CObject__IsKindOf) funkce zajistit typ kontroly argumenty funkce:  
  
```  
ASSERT( pObject1->IsKindOf( RUNTIME_CLASS( CPerson ) ) );  
```  
  
 `ASSERT` Makro nevygeneruje žádný kód ve vydané verzi. Pokud potřebujete při vyhodnocování výrazu ve verzi, použijte [OVĚŘTE](http://msdn.microsoft.com/Library/3e1ab4ee-cbc7-4290-a777-c92f42ce7b96) místo ASSERT – makro.  
  
###  <a name="BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid"></a>Assert_valid – MFC a CObject::AssertValid  
 [CObject::AssertValid](/cpp/mfc/reference/cobject-class.md#CObject__AssertValid) metoda poskytuje spuštění kontroly interní stavu objektu. I když nejsou nezbytné k přepsání `AssertValid` při odvozování třídě z `CObject`, můžete použít třídu spolehlivější tímto způsobem. `AssertValid`kontrolní výrazy proveďte na všechny proměnné členů objektu k ověření, jestli obsahují platné hodnoty. Například měli zkontrolovat, že ukazatel členské proměnné nejsou NULL.  
  
 Následující příklad ukazuje, jak deklarovat `AssertValid` funkce:  
  
```  
class CPerson : public CObject  
{  
protected:  
    CString m_strName;  
    float   m_salary;  
public:  
#ifdef _DEBUG  
    // Override  
    virtual void AssertValid() const;  
#endif  
    // ...  
};  
  
```  
  
 Při přepsání `AssertValid`, volat základní třída verzi `AssertValid` před provedením vlastní kontroly. Potom pomocí makra ASSERT zkontrolujte členy jedinečný do odvozené třídy, jak je vidět tady:  
  
```  
#ifdef _DEBUG  
void CPerson::AssertValid() const  
{  
    // Call inherited AssertValid first.  
    CObject::AssertValid();  
  
    // Check CPerson members...  
    // Must have a name.  
    ASSERT( !m_strName.IsEmpty());  
    // Must have an income.  
    ASSERT( m_salary > 0 );  
}  
#endif  
  
```  
  
 Pokud některé z členské proměnné ukládat objekty, můžete použít `ASSERT_VALID` makro k otestování svých interní platnosti (pokud jejich třídy přepsat `AssertValid`).  
  
 Představte si třeba třídu `CMyData`, která ukládá [CObList](/cpp/mfc/reference/coblist-class) v jednom z jeho proměnné členů. `CObList` Proměnnou, `m_DataList`, ukládá kolekce `CPerson` objekty. Zkrácené deklarace `CMyData` vypadá podobně jako tento:  
  
```  
class CMyData : public CObject  
{  
    // Constructor and other members ...  
    protected:  
        CObList* m_pDataList;  
    // Other declarations ...  
    public:  
#ifdef _DEBUG  
        // Override:  
        virtual void AssertValid( ) const;  
#endif  
    // And so on ...  
};  
  
```  
  
 `AssertValid` Potlačení v `CMyData` vypadá podobně jako tento:  
  
```  
#ifdef _DEBUG  
void CMyData::AssertValid( ) const  
{  
    // Call inherited AssertValid.  
    CObject::AssertValid( );  
    // Check validity of CMyData members.  
    ASSERT_VALID( m_pDataList );  
    // ...  
}  
#endif  
  
```  
  
 `CMyData`používá `AssertValid` mechanismus pro testování platnosti objektů, které je uložen v jeho – datový člen. Přepsání `AssertValid` z `CMyData` vyvolá `ASSERT_VALID` makro pro vlastní m_pDataList členské proměnné.  
  
 Testování platnosti nezastaví na této úrovni protože třída `CObList` také přepsání `AssertValid`. Toto přepsání provede další platnosti testování na vnitřní stav seznamu. Proto na test platnost `CMyData` objekt vede k další platnosti testů pro interní stavy uložené `CObList` objekt seznamu.  
  
 Pomocí některé další práci, můžete přidat platnosti testů `CPerson` objekty uložené v seznamu také. Může odvození třídy `CPersonList` z `CObList` a přepsání `AssertValid`. V přepsání, volání `CObject::AssertValid` a pak iteraci v rámci seznamu volání `AssertValid` na každém `CPerson` objekt uložený v seznamu. `CPerson` Třída zobrazí na začátku tohoto tématu již přepíše `AssertValid`.  
  
 Toto je výkonný mechanismus při sestavení pro ladění. Když následně vytváříte pro vydání, tento mechanismus je automaticky vypnout.  
  
###  <a name="BKMK_Limitations_of_AssertValid"></a>Omezení AssertValid  
 Spouštěná assertion označuje, že objekt je výborný chybný a provádění se zastaví. Však chybějících assertion označuje pouze nebyl nalezen žádný problém, že objekt nemusí být funkční.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Using_assertions"></a>Pomocí kontrolních výrazů  
  
###  <a name="BKMK_Catching_logic_errors"></a>Zachytávání logické chyby  
 Kontrolní výrazy můžete nastavit podmínku, která musí být splněné podle logiky aplikace. Kontrolní výraz nemá žádný vliv, pokud dojde k chybě logiku.  
  
 Předpokládejme například, že jsou simulaci plynu přenosů v kontejneru a proměnná `numMols` představuje celkový počet přenosů. Toto číslo nesmí být menší než nula, tak mohou zahrnovat příkazu MFC assertion takto:  
  
```  
ASSERT(numMols >= 0);  
  
```  
  
 Nebo může zahrnovat CRT assertion takto:  
  
```  
_ASSERT(numMols >= 0);  
```  
  
 Tyto příkazy nic nestane, pokud váš program pracuje správně. Pokud logická chyba způsobí, že `numMols` Pokud chcete být menší než nula, ale kontrolní výraz zastaví provádění vašeho programu a zobrazí [kontrolní se nezdařilo dialogové okno](../debugger/assertion-failed-dialog-box.md).  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Checking_results_"></a>Kontrola výsledků  
 Kontrolní výrazy jsou důležité pro testování operace, jejichž výsledky nejsou zřejmé z rychlé visual kontroly.  
  
 Zvažte například následující kód, který aktualizuje proměnnou `iMols` na základě obsahu odkazovaného seznamu, na kterou odkazuje `mols`:  
  
```  
/* This code assumes that type has overloaded the != operator  
 with const char *   
It also assumes that H2O is somewhere in that linked list.   
Otherwise we'll get an access violation... */  
while (mols->type != "H2O")  
{  
 iMols += mols->num;  
 mols = mols->next;  
}  
ASSERT(iMols<=numMols); // MFC version  
_ASSERT(iMols<=numMols); // CRT version  
```  
  
 Počet přenosů zjištěné službou `iMols` musí být vždycky menší než nebo rovna celkový počet přenosů, `numMols`. Vizuální kontrola smyčky nezobrazuje, že to nutně bude v případě, takže příkazu assertion po smyčky slouží k otestování této podmínky.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Testing_error_conditions_"></a>Hledání neošetřené chyby  
 Kontrolní výrazy můžete použít k testování pro chybové podmínky v bodě ve vašem kódu kde všechny chyby by měl být manipulováno. V následujícím příkladu grafické rutiny vrátí kód chyby nebo nula pro úspěch.  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* Code to handle errors and  
   reset myErr if successful */  
  
ASSERT(!myErr); -- MFC version  
_ASSERT(!myErr); -- CRT version  
```  
  
 Pokud kód pro ošetření chyb funguje správně, měla by ji zpracovat chyba a `myErr` resetování na nulu před dosažením kontrolní výraz. Pokud `myErr` má jinou hodnotu, se nezdaří assertion, program zdržovalo a [kontrolní se nezdařilo dialogové okno](../debugger/assertion-failed-dialog-box.md) se zobrazí.  
  
 Kontrolní výraz příkazy nejsou ale nenahrazuje kód pro ošetření chyb. Následující příklad ukazuje příkazu kontrolní výraz, který může vést k problémům v konečné verze kódu:  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* No Code to handle errors */  
  
ASSERT(!myErr); // Don't do this!  
_ASSERT(!myErr); // Don't do this, either!  
```  
  
 Tento kód spoléhá na příkaz assertion zpracování chybového stavu. V důsledku toho se žádný kód chyby vrácený `myGraphRoutine` bude neošetřená v kódu finální verzi.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Kontrolní výrazy ve spravovaném kódu](../debugger/assertions-in-managed-code.md)