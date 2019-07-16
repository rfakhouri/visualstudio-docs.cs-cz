---
title: 'CA1822: Označte členy jako statické | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 42c6f0d333d1f7ee3f657b9c57c4154e9f824128
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201683"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: Označte členy jako statické
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [CA1822: Označte členy jako statické](https://docs.microsoft.com/visualstudio/code-quality/ca1822-mark-members-as-static).  
  
|||  
|-|-|  
|TypeName|MarkMembersAsStatic|  
|CheckId|CA1822|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Bez konce – Pokud člen není viditelný mimo sestavení, bez ohledu na změnu provedete.<br /><br /> Bez konce – Pokud stačí změnit člena pro člena instance s `this` – klíčové slovo.<br /><br /> Zásadní - li změnit člena z člena instance statického členu a je viditelný mimo sestavení.|  
  
## <a name="cause"></a>příčina  
 Člen, který není přístup k datům instance není označen jako statické (sdílené v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).  
  
## <a name="rule-description"></a>Popis pravidla  
 Členové, kteří nemají přístup k instanci dat nebo metodám instance volání může být označený jako statické (sdílené v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]). Po označení metod jako statických bude kompilátor generovat těmto členům nevirtuální místa volání. Generování nevirtuální místa volání zabrání kontrolu za běhu pro každé volání, která zajišťuje, že aktuální ukazatel objektu je jiná než null. To můžete dosáhnout dosáhnout měřitelného zisku výkonu pro výkonově citlivý kód. V některých případech představuje selhání pro přístup k aktuální instanci objektu správnost problému.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Označte člena jako statického (nebo poskytne [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) nebo použijte 'this' / 'Me' v metodě body, v případě potřeby.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění tohoto pravidla pro dříve dodané kód, pro kterou bude oprava rozbíjející změny.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)  
  
 [CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)  
  
 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)
