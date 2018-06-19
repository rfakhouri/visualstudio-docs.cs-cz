---
title: 'CA2118: Revize použití SuppressUnmanagedCodeSecurityAttribute'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2118
- ReviewSuppressUnmanagedCodeSecurityUsage
helpviewer_keywords:
- ReviewSuppressUnmanagedCodeSecurityUsage
- CA2118
ms.assetid: 4cb8d2fc-4e44-4dc3-9b74-7f5838827d41
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 3eeff4eca5bcc6d2490fc077501726e3ba7e8de1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917173"
---
# <a name="ca2118-review-suppressunmanagedcodesecurityattribute-usage"></a>CA2118: Revize použití SuppressUnmanagedCodeSecurityAttribute
|||
|-|-|
|TypeName|ReviewSuppressUnmanagedCodeSecurityUsage|
|CheckId|CA2118|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejné nebo chráněného typ nebo člen má <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> atribut.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> Změní výchozí chování systému zabezpečení pro členy, které jsou spouštěny pomocí COM zprostředkovatel komunikace s objekty nebo platformy, volání nespravovaného kódu. Obecně platí, umožňuje systém [Data a modelování](/dotnet/framework/data/index) oprávnění pro nespravovaný kód. Tomuto požadavku dojde v době běhu pro každé vyvolání člena a kontroluje všechny volajícího v zásobníku volání pro oprávnění. Pokud je přítomen atribut, díky systému [požadavky propojení](/dotnet/framework/misc/link-demands) pro oprávnění: oprávnění bezprostředního volajícího jsou zaškrtnutá políčka, pokud má volající kompilována.

 Tento atribut slouží především ke zvýšení výkonu, ačkoliv nárůst výkonu může být spojen s významnými riziky zabezpečení. Pokud jste na veřejné členy, které volají metody nativní atribut, volající v zásobníku volání (jiné než bezprostředního volajícího) není nutné nespravovaného kódu oprávnění k provedení nespravovaného kódu. V závislosti na veřejné člen akce a zpracování vstupních se může povolit nedůvěryhodným volajícím funkce přístupu obvykle omezené na důvěryhodného kódu.

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Spoléhá na kontrol zabezpečení, aby se zabránilo volající získat přímý přístup k aktuální proces adresní prostor. Protože tento atribut obchází normální zabezpečení, představuje váš kód závažné ohrožení, pokud lze číst nebo zapisovat do paměti procesu. Všimněte si, že riziko není omezeno na metody, které záměrně poskytovat přístup ke zpracování paměti; je také součástí nějaký scénář, kde škodlivý kód můžete dosáhnout přístup a to jakýmkoli způsobem, například tím, že poskytuje překvapivé, poškozený nebo neplatný vstup.

 Výchozí zásady zabezpečení nespravovaného kódu oprávnění k sestavení neposkytne, pokud se spouští z místního počítače nebo je členem jedné z následujících skupin:

-   Moje skupina počítačů zóny kódu

-   Skupiny kódu název silným Microsoft

-   ECMA silným názvem kód skupiny

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pečlivě zkontrolujte kód a ujistěte se, že tento atribut je nezbytně nutné. Pokud nejste obeznámeni s zabezpečení spravovaného kódu, nebo není srozumitelný zabezpečení důsledky použití tento atribut, odeberte ji z vašeho kódu. Pokud atribut se vyžaduje, je nutné zajistit, že volající závadně nelze použít váš kód. Pokud váš kód nemá oprávnění k provedení nespravovaného kódu, tento atribut nemá žádný vliv a měla by být odebrána.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Bezpečně potlačit upozornění na toto pravidlo, je nutné zajistit, že váš kód nenabízí volající přístup k nativní operace nebo prostředky, které můžete použít destruktivní způsobem.

## <a name="example"></a>Příklad
 Následující příklad porušuje pravidlo.

 [!code-csharp[FxCop.Security.TypesDoNotSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_1.cs)]

## <a name="example"></a>Příklad
 V následujícím příkladu `DoWork` metoda poskytuje cestu veřejně přístupný kód do metody vyvolání platformy `FormatHardDisk`.

 [!code-csharp[FxCop.Security.PInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_2.cs)]

## <a name="example"></a>Příklad
 V následujícím příkladu, veřejná metoda `DoDangerousThing` způsobí, že porušení. Chcete-li vyřešit porušení, `DoDangerousThing` je třeba provést privátní a přístup k němu by měla být prostřednictvím veřejná metoda zabezpečeny požadavek zabezpečení, které jsou popsány v `DoWork` metoda.

 [!code-csharp[FxCop.Security.TypeInvokeAndSuppress#1](../code-quality/codesnippet/CSharp/ca2118-review-suppressunmanagedcodesecurityattribute-usage_3.cs)]

## <a name="see-also"></a>Viz také
 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines) [Data a modelování](/dotnet/framework/data/index) [požadavky na propojení](/dotnet/framework/misc/link-demands)
