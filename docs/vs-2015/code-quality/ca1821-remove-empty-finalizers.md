---
title: 'CA1821: Odstraňte prázdné finalizační metody | Dokumentace Microsoftu'
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
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: efd7a2675326780c8e66daf49390587a7f85db3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668013"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Odstraňte prázdné finalizační metody
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1821: odstraňte prázdné finalizační metody](https://docs.microsoft.com/visualstudio/code-quality/ca1821-remove-empty-finalizers).  
  
TypeName | RemoveEmptyFinalizers |  
| ID kontroly | CA1821 |  
| Kategorie | Microsoft.Performance|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Typ implementuje finalizační metodu, která je prázdný, vyžaduje pouze základní typ finalizační metodu nebo volá pouze podmíněně vyslané metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Kdykoli je to možné, vyhněte se použití finalizačních metod kvůli dodatečným nárokům na výkon spojeným se sledováním životního cyklu objektu. Uvolňování paměti spustí finalizační metodu, předtím, než se shromáždí objektů. To znamená, že dvě kolekce se bude vyžadovat ke shromažďování objektu. Prázdná finalizační metoda zvyšuje touto přidanou režie bez žádnou výhodu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Odstraňte prázdné finalizační metody. Pokud se vyžaduje pro ladění finalizační metodu, uzavřete celý finalizační metodu v `#if DEBUG / #endif` direktivy.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte zprávy z tohoto pravidla. Selhání pro potlačení dokončení snižuje výkon a poskytuje žádné výhody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje prázdná finalizační metoda, která by měla být odebrána, finalizační metodu, která by měl být uzavřen v `#if DEBUG / #endif` směrnicemi a finalizační metodu, která používá `#if DEBUG / #endif` direktivy správně.  
  
 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.RemoveEmptyFinalizers/cs/FxCop.Performance.RemoveEmptyFinalizers.cs#1)]



