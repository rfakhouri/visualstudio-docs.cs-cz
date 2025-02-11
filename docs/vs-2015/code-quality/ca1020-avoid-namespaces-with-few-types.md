---
title: 'CA1020: Vyvarujte se oborům názvu s malým množstvím typů | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
helpviewer_keywords:
- CA1020
- AvoidNamespacesWithFewTypes
ms.assetid: 9cb272f6-a3ff-45af-b35d-70dea620b074
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8c94cf09b43eb09482be4a30d9f0b9206678c4dc
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435834"
---
# <a name="ca1020-avoid-namespaces-with-few-types"></a>CA1020: Vyhněte se oborům názvu s malým množstvím typů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidNamespacesWithFewTypes|
|CheckId|CA1020|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Obor názvů než globální obor názvů obsahuje méně než pět typů.

## <a name="rule-description"></a>Popis pravidla
 Ujistěte se, že všechny obory názvů mají logické uspořádání a, existuje platný důvod do typů do řídce zaplněných oborů názvů. Obory názvů by měl obsahovat typy, které se používají společně ve většině scénářů. Když své aplikace se vzájemně vylučují, typy musí nacházet v samostatných oborů názvů. Například <xref:System.Web.UI> obor názvů obsahuje typy, které se používají ve webových aplikacích a <xref:System.Windows.Forms> obor názvů obsahuje typy, které se používají v [!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)]– aplikace založené na. I když oba obory názvů mají typy, které řídí aspekty uživatelského rozhraní, nejsou tyto typy určený k použití ve stejné aplikaci. Proto se nacházejí v samostatných oborů názvů. Pozor, obor názvů organizace může být také užitečné vzhledem k tomu, že jeho hodnota se zvyšuje zjistitelnost funkce. Prozkoumáním hierarchii obor názvů spotřebitelé knihovny by měli být schopen najít typy, které implementují funkce.

> [!NOTE]
> Typy návrhu a oprávnění by neměl sloučeny do jiných oborech názvů pro dosažení souladu s toto pravidlo. Tyto typy patří do své vlastní obory názvů pod hlavním obor názvů a obory názvů by měl končit `.Design` a `.Permissions`v uvedeném pořadí.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zkuste kombinovat obory názvů, které obsahují typy, několika do jednoho oboru názvů.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud obor názvů obsahuje typy, které se používají s typy v jiných obory názvů.
