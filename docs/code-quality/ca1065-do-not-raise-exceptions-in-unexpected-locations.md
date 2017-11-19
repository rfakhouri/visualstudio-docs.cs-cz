---
title: "CA1065: Není vyvolání výjimky v neočekávaných umístěních | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1065
- DoNotRaiseExceptionsInUnexpectedLocations
helpviewer_keywords:
- DoNotRaiseExceptionsInUnexpectedLocations
- CA1065
ms.assetid: 4e1bade4-4ca2-4219-abc3-c7b2d741e157
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3511778536bb9664726fc9a61b4773c209a0fd46
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1065-do-not-raise-exceptions-in-unexpected-locations"></a>CA1065: Nevyvolávejte výjimky v neočekávaných umístěních
|||  
|-|-|  
|TypeName|DoNotRaiseExceptionsInUnexpectedLocations|  
|CheckId|CA1065|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Metoda, u které není předpokládáno vyvolání výjimky, vyvolá výjimku.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metody, které nejsou očekávané vyvolat výjimky můžete rozdělit takto:  
  
-   Metody Get vlastností  
  
-   Metody přístupových objektů události  
  
-   Equals – metody  
  
-   GetHashCode metody  
  
-   Metody ToString  
  
-   Statické konstruktory  
  
-   Finalizační metody  
  
-   Dispose – metody  
  
-   Operátory rovnosti  
  
-   Operátory implicitního přetypování  
  
 Následující části popisují tyto typy metoda.  
  
### <a name="property-get-methods"></a>Metody Get vlastností  
 Vlastnosti jsou v podstatě inteligentní pole. Proto by se měly chovat jako pole co nejvíc. Pole nevyvolá výjimku výjimky a ani má vlastnosti. Pokud je vlastnost, která vyvolá výjimku, zvažte, což metodu.  
  
 Vyvolání z metody get vlastnost jsou povolené následující výjimky:  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName>a všechny odvozené konfigurace (včetně <xref:System.ObjectDisposedException?displayProperty=fullName>)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName>a všechny odvozené konfigurace  
  
-   <xref:System.ArgumentException?displayProperty=fullName>(jenom z indexovaného get)  
  
-   <xref:System.Collections.Generic.KeyNotFoundException>(jenom z indexovaného get)  
  
### <a name="event-accessor-methods"></a>Metody přístupových objektů události  
 Přístupové objekty událostí by měl být jednoduché operace, které není generování výjimek. Události by neměly vyvolat výjimku při pokusu o přidání nebo odebrání obslužné rutiny události.  
  
 Vyvolání z události accesor jsou povoleny následující výjimky:  
  
-   <xref:System.InvalidOperationException?displayProperty=fullName>a všechny odvozené konfigurace (včetně <xref:System.ObjectDisposedException?displayProperty=fullName>)  
  
-   <xref:System.NotSupportedException?displayProperty=fullName>a všechny odvozené konfigurace  
  
-   <xref:System.ArgumentException>a odvozené konfigurace  
  
### <a name="equals-methods"></a>Equals – metody  
 Následující **rovná** metody by neměla vyvolat výjimky:  
  
-   <xref:System.Object.Equals%2A?displayProperty=fullName>  
  
-   [M:IEquatable.Equals](http://go.microsoft.com/fwlink/?LinkId=113472)  
  
 **Rovná** metoda by měla vrátit `true` nebo `false` místo došlo k výjimce. Například pokud je rovno je předán dva typy neodpovídající má být právě vrácen `false` místo vyvolání <xref:System.ArgumentException>.  
  
### <a name="gethashcode-methods"></a>GetHashCode metody  
 Následující **GetHashCode** metody by neměla obvykle vyvolat výjimky:  
  
-   <xref:System.Object.GetHashCode%2A>  
  
-   [M:IEqualityComparer.GetHashCode(T)](http://go.microsoft.com/fwlink/?LinkId=113477)  
  
 **GetHashCode** by vždy vrátit hodnotu. Jinak může dojít ke ztrátě položky v zatřiďovací tabulce.  
  
 Verze **GetHashCode** trvají argument můžete vyvolat <xref:System.ArgumentException>. Ale **Object.GetHashCode** nikdy vyvoláním výjimky.  
  
### <a name="tostring-methods"></a>Metody ToString  
 Ladicí program používá <xref:System.Object.ToString%2A?displayProperty=fullName> můžete zobrazit informace o objektech ve formátu řetězce. Proto **ToString** nesmí změnit stav objektu a jeho nesmí generování výjimek.  
  
### <a name="static-constructors"></a>Statické konstruktory  
 Vyvolání výjimek ze statického konstruktoru způsobí, že typ nebude možné použít v aktuální doméně aplikace. Měli byste mít velmi dobré důvod (například porušení zabezpečení) pro vyvolání výjimky z statického konstruktoru.  
  
### <a name="finalizers"></a>Finalizační metody  
 Došlo k výjimce z finalizační metody způsobí, že CLR rychlé a selhání, které strhne proces. Proto vyvolávání výjimek v finalizační metody vždy je nutno.  
  
### <a name="dispose-methods"></a>Dispose – metody  
 A <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metoda nesmí vyvolat výjimku. Uvolnění se často říká jako součást logiky čištění `finally` klauzule. Proto explicitně došlo k výjimce z uvolnění vynutí uživateli přidat uvnitř zpracování výjimek `finally` klauzule.  
  
 **Dispose(false)** cesta kódu by nikdy vyvolat výjimky, protože to je téměř vždy volat z finalizační metody.  
  
### <a name="equality-operators--"></a>Operátory rovnosti (==,! =)  
 Jako rovná metody by měla vrátit operátory rovnosti buď `true` nebo `false` a nesmí generování výjimek.  
  
### <a name="implicit-cast-operators"></a>Operátory implicitního přetypování  
 Protože uživatel je často neví, že byla volána operátor přetypování implicitní, je zcela neočekávané výjimky vyvolané operátor implicitní přetypování. Proto nedocházelo k výjimkám by měl být vyvolána z operátory implicitního přetypování.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pro vlastnost metod getter buď změnit logiku, takže už má vyvolat výjimku, nebo změňte vlastnost do metody.  
  
 Pro všechny ostatní metody typy uvedených výše změňte logiku tak, aby ho už musí vyvolat výjimku.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li deklarace výjimka místo vyvolaná výjimka způsobila porušení zásady.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2219: Není vyvolání výjimky v klauzulích výjimky](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)  
  
## <a name="see-also"></a>Viz také  
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)