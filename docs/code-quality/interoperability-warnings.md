---
title: "Upozornění interoperability | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis warnings, interoperability warnings
- interoperability warnings
- warnings, interoperability
ms.assetid: 95de6eb3-40c4-4063-9f59-25cb70e3b2b3
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9d8a0587bdfce2284f4767087c88faab573e04b7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="interoperability-warnings"></a>Upozornění interoperability
Upozornění interoperability podporují interakci s klienty COM.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
|Pravidlo|Popis|  
|----------|-----------------|  
|[CA1400: Vstupní body P/Invoke by měla existovat.](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|Veřejná nebo chráněná metoda je označena pomocí atributu System.Runtime.InteropServices.DllImportAttribute. Nespravovanou knihovnu nelze nalézt nebo nelze metodu porovnat s funkcí v knihovně.|  
|[CA1401: P/by neměla být viditelné](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|Metoda veřejných nebo chráněné v veřejného typu má atribut System.Runtime.InteropServices.DllImportAttribute (také implementované Declare – klíčové slovo v jazyce Visual Basic). Tyto metody by neměly být vystaveny.|  
|[CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM](../code-quality/ca1402-avoid-overloads-in-com-visible-interfaces.md)|Když jsou přetížené metody vystaveny klientům modulu COM, zachová svůj název pouze první přetížení metody. Následná přetížení jsou jednoznačně přejmenována přidáním podtržítka (_) a celého čísla odpovídajícího pořadí deklarace tohoto přetížení.|  
|[CA1403: Typy automatického rozložení by neměly být viditelné modelu COM](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|Hodnotový typ viditelný modulem COM je označen pomocí atributu System.Runtime.InteropServices.StructLayoutAttribute, nastaveného na hodnotu LayoutKind.Auto. Mezi verzemi můžete změnit rozložení těchto typů [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], které by došlo k přerušení klientů modelu COM, které očekávají konkrétní rozložení.|  
|[CA1404: Volejte GetLastError ihned po volání P/Invoke](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|Přišla žádost na metodu Marshal.GetLastWin32Error nebo jeho ekvivalent [!INCLUDE[TLA2#tla_win32](../code-quality/includes/tla2sharptla_win32_md.md)] GetLastError funkce a okamžitě předchozího volání není pro platformu vyvolat metodu.|  
|[CA1405: Základní typy viditelného typu modelu COM by měly být viditelné modelu COM](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|Typ viditelný modulem COM je odvozen od typu, který není viditelný modulem COM.|  
|[CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)|Visual Basic 6 COM klienti nemají přístup k 64bitových celých čísel.|  
|[CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)|Modul COM nepodporuje statické metody.|  
|[CA1408: Nepoužívejte AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)|Typy, které používají duální rozhraní, umožňují klientům navázat se na určité rozložení rozhraní. Změny v budoucí verzi rozložení typu nebo jakéhokoli základního typu přeruší klienty modulu COM, kteří jsou navázáni na toto rozhraní. Pokud ve výchozím nastavení není zadán atribut ClassInterfaceAttribute, použije se pouze rozhraní určené pro odesílání.|  
|[CA1409: Viditelné typy modelu COM by měly být vytvořitelné](../code-quality/ca1409-com-visible-types-should-be-creatable.md)|Odkazový typ, který je označen jako viditelný modulům COM, obsahuje veřejný parametrizovaný konstruktor, ale neobsahuje veřejný výchozí konstruktor (bez parametrů). Typ bez veřejného výchozího konstruktoru není možné vytvořit klienty typu COM.|  
|[CA1410: Metody registrace modelu COM by si měly odpovídat](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|Typ deklaruje metodu, která je označena pomocí <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atribut ale nedeklaruje metodu, která je označena pomocí <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> atribut, nebo naopak.|  
|[CA1411: Metody registrace modelu COM by neměly být viditelné](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)|Metoda, která je označena pomocí System.Runtime.InteropServices.ComRegisterFunctionAttribute atribut, nebo atribut System.Runtime.InteropServices.ComUnregisterFunctionAttribute je viditelné.|  
|[CA1412: Označte rozhraní ComSource jako IDispatch](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)|Typ je označen atributem System.Runtime.InteropServices.ComSourceInterfacesAttribute a alespoň jedno ze zadaných rozhraní není označeno pomocí atributu System.Runtime.InteropServices.InterfaceTypeAttribute nastaveného na hodnotu ComInterfaceType.InterfaceIsIDispatch.|  
|[CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)|Neveřejná pole instancí hodnotových typů viditelných moduly COM jsou viditelná klientům typu COM. Zkontrolujte obsah polí, zda neobsahují informace, které by neměly být vystaveny nebo které budou mít nežádoucí účinky na návrh nebo zabezpečení.|  
|[CA1414: Označte logické P/Invoke pomocí MarshalAs](../code-quality/ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md)|Datový typ Boolean má v nespravovaném kódu různé reprezentace.|  
|[CA1415: Deklarujte správně](../code-quality/ca1415-declare-p-invokes-correctly.md)|Toto pravidlo vyhledá vyvolání platformy metoda deklarace cílených [!INCLUDE[TLA2#tla_win32](../code-quality/includes/tla2sharptla_win32_md.md)] funkce, které mají ukazatel na OVERLAPPED struktury parametr a odpovídající spravované parametr není ukazatel na <xref:System.Threading.NativeOverlapped?displayProperty=fullName> struktury.|