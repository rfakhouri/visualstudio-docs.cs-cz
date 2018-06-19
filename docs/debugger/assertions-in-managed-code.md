---
title: Kontrolní výrazy ve spravovaném kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], assertions in managed code
- Trace.Assert method
- debugging managed code, assertions
- Debug.Assert method
- Debug.Listeners property
- assertions, side effects
- Trace.Listeners property
- assertions, managed code
ms.assetid: 70ab2522-6486-4076-a1a9-e0f11cd0f3a1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e5b4c66beba2a4c3953a0720a3f770f7f651db79
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465405"
---
# <a name="assertions-in-managed-code"></a>Kontrolní výrazy ve spravovaném kódu
Na kontrolní výraz systému nebo `Assert` testuje podmínku, kterou zadáte jako argument pro příkaz, `Assert` příkaz. Pokud je podmínka vyhodnocena jako true, nedojde k žádné akci. Pokud je podmínka vyhodnocena jako false, kontrolní výraz se nezdaří. Pokud používáte s sestavení ladicí verze, váš program vstupuje do režimu pozastavení.  
  
##  <a name="BKMK_In_this_topic"></a> V tomto tématu  
 [Vyhodnotí v Namespace System.Diagnostics](#BKMK_Asserts_in_the_System_Diagnostics_Namespace)  
  
 [Debug.Assert – metoda](#BKMK_The_Debug_Assert_method)  
  
 [Vedlejší efekty Debug.Assert –](#BKMK_Side_effects_of_Debug_Assert)  
  
 [Trasování a ladění požadavky](#BKMK_Trace_and_Debug_Requirements)  
  
 [Assert – argumenty](#BKMK_Assert_arguments)  
  
 [Přizpůsobení chování Assert](#BKMK_Customizing_Assert_behavior)  
  
 [Kontrolní výrazy nastavení v konfiguračních souborech](#BKMK_Setting_assertions_in_configuration_files)  
  
##  <a name="BKMK_Asserts_in_the_System_Diagnostics_Namespace"></a> Vyhodnotí v Namespace System.Diagnostics  
 V jazyce Visual Basic a Visual C#, můžete použít `Assert` metoda buď z <xref:System.Diagnostics.Debug> nebo <xref:System.Diagnostics.Trace>, které jsou v <xref:System.Diagnostics> oboru názvů. <xref:System.Diagnostics.Debug> metody třídy nejsou součástí verzi vašeho programu, zvětšit velikost nebo snížení rychlosti verze kódu.  
  
 C++ nepodporuje <xref:System.Diagnostics.Debug> metody třídy. Stejného efektu můžete dosáhnout pomocí <xref:System.Diagnostics.Trace> třídy s Podmíněná kompilace, jako například `#ifdef DEBUG`... `#endif`.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_The_Debug_Assert_method"></a> Debug.Assert – metoda  
 Použití <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> metoda volně k testování podmínky, které by měl obsahovat hodnotu true, pokud jste kód napsali správně. Předpokládejme například, že jste napsali dělení funkce celé číslo. Pravidly Matematika dělitel nikdy nemůže mít hodnotu nula. Může toto vyzkoušíte pomocí kontrolní výrazy:  
  
```VB  
Function IntegerDivide(ByVal dividend As Integer, ByVal divisor As Integer) As Integer  
    Debug.Assert(divisor <> 0)  
    Return CInt(dividend / divisor)  
End Function  
```  
  
```csharp  
int IntegerDivide ( int dividend , int divisor )  
    { Debug.Assert ( divisor != 0 );  
        return ( dividend / divisor ); }  
```  
  
 Pokud spustíte tento kód v ladicím programu, kontrolní výraz vyhodnotí, ale ve verzi, není srovnání provedeno, je proto bez dalších zásahů.  
  
 Zde je další příklad. Máte třídu, která implementuje účet kontroluje následujícím způsobem:  
  
```VB  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Debug.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Debug.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 Předtím, než jste odstoupení peníze z účtu, budete chtít Ujistěte se, že je zůstatek účtu nepokrývají částku, kterou se připravujete na odstoupení. Kontrolní výrazy zkontrolovat zůstatek může zapsat:  
  
```VB  
Dim amount, balance As Double  
balance = savingsAccount.balance  
Trace.Assert(amount <= balance)  
SavingsAccount.Withdraw(amount)  
```  
  
```csharp  
float balance = savingsAccount.Balance;  
Trace.Assert ( amount <= balance );  
savingsAccount.Withdraw ( amount );  
```  
  
 Všimněte si, že volá, aby se <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> metoda zmizí při vytváření verzi vašeho kódu. To znamená, že volání, která kontroluje rovnováhu mezi zmizí ve vydané verzi. Chcete-li tento problém vyřešit, měli byste nahradit <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> s <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, který nezmizí ve verzi:  
  
 Volání <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> přidat nároky na prodejní verzi, na rozdíl od volání <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Side_effects_of_Debug_Assert"></a> Vedlejší efekty Debug.Assert –  
 Při použití <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, zajistěte, aby žádný kód uvnitř `Assert` nezmění výsledky program, pokud `Assert` se odebere. Jinak hodnota může nechtěně způsobit chyby, který se zobrazí pouze ve verzi vašeho programu. Buďte opatrní hlavně o vyhodnotí, které obsahují funkce nebo procedury volání, jako například v následujícím příkladu:  
  
```VB  
' unsafe code  
Debug.Assert (meas(i) <> 0 )  
```  
  
```csharp  
// unsafe code  
Debug.Assert (meas(i) != 0 );  
```  
  
 Toto použití <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> se může objevit bezpečné na první pohled, ale Předpokládejme, že funkce meas aktualizace čítače pokaždé, když je volána. Při sestavování prodejní verze volání meas je odstraněny, takže čítač neaktualizuje. Jedná se o příklad funkce s vedlejším účinkem. Volání funkce, která má vedlejší účinky odstranění může mít za následek chybu, která se zobrazí pouze ve verzi. Chcete-li se těmto problémům, neumísťujte volání funkce v <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> příkaz. Místo toho použijte dočasnou proměnnou:  
  
```VB  
temp = meas( i )  
Debug.Assert (temp <> 0)  
```  
  
```csharp  
temp = meas( i );  
Debug.Assert ( temp != 0 );  
```  
  
 I když použijete <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, můžete chtít stále předejde volání funkcí uvnitř `Assert` příkaz. Takové volání by měla být bezpečné, protože <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> nejsou eliminovat příkazy v sestavení pro vydání. Je-li se vyhnout takové konstrukce jako řádu která podporují, je však méně pravděpodobné, ujistěte se, že při použití <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Trace_and_Debug_Requirements"></a> Trasování a ladění požadavky  
 Pokud vytvoříte projekt pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] průvodců symbol trasování je definována ve výchozím nastavení v konfiguracích verze a ladění. Symboly pro ladění je definována ve výchozím nastavení pouze v sestavení ladicí verze.  
  
 Jinak pro <xref:System.Diagnostics.Trace> metod pro práci, váš program musí mít jednu z následujících v horní části zdrojového souboru:  
  
-   `#Const TRACE = True` V jazyce Visual Basic  
  
-   `#define TRACE` v jazyce Visual C# a C++  
  
 Nebo váš program musí být vytvořená s možností trasování:  
  
-   `/d:TRACE=True` V jazyce Visual Basic  
  
-   `/d:TRACE` v jazyce Visual C# a C++  
  
 Pokud potřebujete použít metody ladění sestavení C# nebo Visual Basic verze, je nutné zadat symbol ladění ve vaší verzi konfiguraci.  
  
 C++ nepodporuje <xref:System.Diagnostics.Debug> metody třídy. Stejného efektu můžete dosáhnout pomocí <xref:System.Diagnostics.Trace> třídy s Podmíněná kompilace, jako například `#ifdef DEBUG`... `#endif`. Můžete definovat tyto symboly v  **\<Projekt > stránky vlastností** dialogové okno. Další informace najdete v tématu [Změna nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md) nebo [Změna nastavení projektu pro C nebo C++ ladění konfigurace](../debugger/project-settings-for-a-cpp-debug-configuration.md).  
  
##  <a name="BKMK_Assert_arguments"></a> Assert – argumenty  
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> a <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> trvat až tři argumenty. První argument, který je povinný, je podmínku, kterou chcete zkontrolovat. Když zavoláte <xref:System.Diagnostics.Trace.Assert(System.Boolean)?displayProperty=fullName> nebo <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=fullName> s pouze jedním argumentem `Assert` metoda kontroluje podmínku a pokud je výsledek hodnotu false, výstupy obsah bude zásobník volání **výstup** okno. Následující příklad ukazuje <xref:System.Diagnostics.Trace.Assert(System.Boolean)?displayProperty=fullName> a <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=fullName>:  
  
```VB  
Debug.Assert(stacksize > 0)  
Trace.Assert(stacksize > 0)  
```  
  
```csharp  
Debug.Assert ( stacksize > 0 );  
Trace.Assert ( stacksize > 0 );   
```  
  
 Druhý a třetí argument, pokud existuje, musí být řetězce. Když zavoláte <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> nebo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> se dva nebo tři argumenty s prvním argumentem je podmínku. Metoda kontroluje podmínku a pokud je výsledek hodnotu false, výstupy řetězec druhý a třetí řetězce. Následující příklad ukazuje <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=fullName> a <xref:System.Diagnostics.Trace.Assert(System.Boolean,System.String)?displayProperty=fullName> použít s dva argumenty:  
  
```VB  
Debug.Assert(stacksize > 0, "Out of stack space")  
Trace.Assert(stacksize > 0, "Out of stack space")  
```  
  
```csharp  
Debug.Assert ( stacksize > 0, "Out of stack space" );  
Trace.Assert ( stacksize > 0, "Out of stack space" );  
```  
  
 Následující příklad ukazuje <xref:System.Diagnostics.Debug.Assert%2A> a <xref:System.Diagnostics.Trace.Assert%2A>:  
  
```VB  
Debug.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:" , Format(size, "G"))  
Trace.Assert(stacksize > 0, "Out of stack space. Bytes left:", "inctemp failed on third call" )  
```  
  
```csharp  
Debug.Assert ( stacksize > 100, "Out of stack space" , "Failed in inctemp" );  
Trace.Assert ( stacksize > 0, "Out of stack space", "Failed in inctemp" );   
```  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Customizing_Assert_behavior"></a> Přizpůsobení chování Assert  
 Pokud spustíte aplikaci v režimu uživatelského rozhraní `Assert` metoda zobrazí **kontrolní výraz** dialogové okno když podmínky selhání. Akce, které dojít, když selže kontrolní výrazy jsou řízeny <xref:System.Diagnostics.Debug.Listeners%2A> nebo <xref:System.Diagnostics.Trace.Listeners%2A> vlastnost.  
  
 Výstup chování můžete přizpůsobit přidáním <xref:System.Diagnostics.TraceListener> do objektu `Listeners` kolekce odebráním <xref:System.Diagnostics.TraceListener> z `Listeners` kolekce, nebo přepsáním <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> metoda existujícího `TraceListener` Chcete-li chovat jinak.  
  
 Například může přepsat <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> metoda k zápisu do protokolu událostí místo **kontrolní výraz** dialogové okno.  
  
 Chcete-li přizpůsobit výstup tímto způsobem, váš program musí obsahovat naslouchací proces a musí dědit z <xref:System.Diagnostics.TraceListener> a přepsat její <xref:System.Diagnostics.TraceListener.Fail%2A?displayProperty=fullName> metoda.  
  
 Další informace najdete v tématu [trasování – moduly naslouchání](/dotnet/framework/debug-trace-profile/trace-listeners).  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Setting_assertions_in_configuration_files"></a> Kontrolní výrazy nastavení v konfiguračních souborech  
 Kontrolní výrazy v konfiguračním souboru aplikace také můžete nastavit jako váš kód. Další informace naleznete v tématech <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> a <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Trasování a instrumentace aplikací](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)   
 [Postupy: Podmíněná kompilace pomocí trasování a ladění](/dotnet/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)