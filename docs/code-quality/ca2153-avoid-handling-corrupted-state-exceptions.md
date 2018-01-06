---
title: "CA2153: Vyhněte se zpracování výjimek poškozená stavu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 418cc9cb-68ad-47e9-a6c8-a48b9c35db45
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 92fa57068a760fc8168fa46cf32a5660293b2e9b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2153-avoid-handling-corrupted-state-exceptions"></a>CA2153: Vyhněte se zpracování poškozená stavu výjimek
|||  
|-|-|  
|TypeName|AvoidHandlingCorruptedStateExceptions|  
|CheckId|CA2153|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 [Poškozený stav výjimky (rozšíření na straně klienta)](https://msdn.microsoft.com/en-us/magazine/dd419661.aspx) znamenat, že paměť poškození existuje v procesu. Zachytávání tyto než umožní procesu havárií může vést k ohrožení zabezpečení, pokud útočník můžete umístit zneužití do oblasti poškozená paměti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Rozšíření na straně klienta signalizuje, že stav procesu má byla poškozena a nebyla zachycena v systému. V poškozeném stavu scénáři obslužnou rutinu obecné pouze zachytí výjimky Pokud označíte metodu správné `HandleProcessCorruptedStateExceptions` atribut. Ve výchozím nastavení [Common Language Runtime (CLR)](/dotnet/standard/clr) nebude vyvolat catch obslužné rutiny pro rozšíření na straně klienta.  
  
 Povolení, že proces havárií bez zachytávání tyto druhy výjimek je nejbezpečnější možnosti, jako i protokolování kód útočníkovi umožnit, aby před zneužitím chyb poškození paměti.  
  
 Toto upozornění se aktivuje při zachycování rozšíření na straně klienta pomocí obecné obslužné rutiny, které zachytí všechny výjimky, jako je například catch(exception) nebo catch (bez specifikace výjimek).  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li vyřešit toto upozornění proveďte jednu z těchto možností:  
  
 1. Odeberte `HandleProcessCorruptedStateExceptions` atribut. To obnoví na výchozí chování za běhu, kde nejsou předán obslužné rutiny zachytávání rozšíření na straně klienta.  
  
 2. Odeberte obslužná rutina obecné catch in preference of obslužných rutin, které catch výjimky pro konkrétní typy.  To může zahrnovat rozšíření na straně klienta za předpokladu, že je může zpracovat bezpečně kód obslužné rutiny (velmi výjimečných).  
  
 3. Znovu vyvolejte rozšíření na straně klienta v catch obslužná rutina, která zajišťuje výjimka předaný volající a způsobí ukončení běžící proces.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="pseudo-code-example"></a>Příklad pseudo kódu  
  
### <a name="violation"></a>Porušení  
 Následující kód pseudo ilustruje vzor zjistil tímto pravidlem.  
  
```  
[HandleProcessCorruptedStateExceptions]   
//method to handle and log CSE exceptions   
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (Exception e)  
    {  
        // Handle error  
    }  
}  
```  
  
### <a name="solution-1"></a>Řešení 1  
 Odebráním atributu HandleProcessCorruptedExceptions zajistí, že výjimky nebudou zpracovány.  
  
```  
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (IOException e)  
    {  
        // Handle error  
    }  
    catch (UnauthorizedAccessException e)  
    {  
        // Handle error  
    }  
}  
```  
  
### <a name="solution-2"></a>Řešení 2  
 Catch – obecné obslužné rutiny odebírání a catch pouze typy konkrétních výjimek.  
  
```  
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (IOException e)  
    {  
        // Handle error  
    }  
    catch (UnauthorizedAccessException e)  
    {  
        // Handle error  
    }  
}  
```  
  
### <a name="solution-3"></a>Řešení 3  
 Znovu vyvolejte výjimku.  
  
```  
void TestMethod1()   
{   
    try  
    {  
        FileStream fileStream = new FileStream("name", FileMode.Create);  
    }    
    catch (Exception e)  
    {  
        // Handle error  
        throw;  
    }  
}  
```