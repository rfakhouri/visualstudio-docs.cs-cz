---
title: 'CA1044: Vlastnosti by neměly být pouze pro zápis | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PropertiesShouldNotBeWriteOnly
- CA1044
helpviewer_keywords:
- CA1044
- PropertiesShouldNotBeWriteOnly
ms.assetid: 8386bf3a-b161-4841-bf8b-92591595aea9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e053765c2d9dbe35505f826eb6ecebd4db27f23c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669974"
---
# <a name="ca1044-properties-should-not-be-write-only"></a>CA1044: Vlastnosti by neměly být pouze pro zápis
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1044: vlastnosti by neměly být pouze pro zápis](https://docs.microsoft.com/visualstudio/code-quality/ca1044-properties-should-not-be-write-only).  
  
TypeName | PropertiesShouldNotBeWriteOnly |  
| ID kontroly | CA1044 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Veřejné nebo chráněné vlastnosti má přistupující objekt set, ale nemá přistupující objekt get.  
  
## <a name="rule-description"></a>Popis pravidla  
 Získat přístupové objekty poskytnout oprávnění ke čtení pro vlastnost a přístupové objekty set poskytují přístup pro zápis. Ačkoli je přijatelné a často nezbytné použít vlastnost jen pro čtení, směrnice návrhu zakazují použití vlastností jen pro zápis. Je to proto, že umožnit uživateli nastavit hodnotu a poté uživateli zabránit v zobrazování hodnotě neposkytuje žádné zabezpečení. Taktéž bez přístupu pro čtení není možné zobrazit stav sdílených objektů, což omezuje jejich užitečnost.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přidejte přístupový objekt get vlastnosti. Případně pokud chování vlastnost jen pro zápis, je nezbytné, zvažte, převod této vlastnosti na metodu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Důrazně doporučujeme nepotlačujte upozornění tohoto pravidla.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `BadClassWithWriteOnlyProperty` je typ s vlastností jen pro zápis. `GoodClassWithReadWriteProperty` obsahuje opraveným kódem.  
  
 [!code-csharp[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/cs/FxCop.Design.PropertiesNotWriteOnly.cs#1)]
 [!code-vb[FxCop.Design.PropertiesNotWriteOnly#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.PropertiesNotWriteOnly/vb/PropertiesNotWriteOnly.vb#1)]



