---
title: "CA2208: Vytvořte instanci výjimky argumentu správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2208
- InstantiateArgumentExceptionsCorrectly
helpviewer_keywords:
- InstantiateArgumentExceptionsCorrectly
- CA2208
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 78d510d966f2467123105ad777d61c99ad11e99a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2208-instantiate-argument-exceptions-correctly"></a>CA2208: Vytvořte správně instance výjimky argumentu
|||  
|-|-|  
|TypeName|InstantiateArgumentExceptionsCorrectly|  
|CheckId|CA2208|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Možné příčiny následujících situacích:  
  
-   Přišla žádost o výchozího konstruktoru (bez parametrů), nebo je odvozen od typu výjimka <xref:System.ArgumentException>.  
  
-   Argument řetězce není správný předaný konstruktoru parametrizované nebo je odvozen od typu výjimka <xref:System.ArgumentException>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Namísto volání výchozí konstruktor, volání jednoho z přetížení konstruktoru, která umožňuje smysluplnější zpráva o výjimce, musíte zadat. Zpráva o výjimce by měl cíli vývojář a jasně popisují chybový stav a jak opravit nebo vyloučit výjimku.  
  
 Signatur jeden a dva konstruktory řetězec z <xref:System.ArgumentException> a nejsou konzistentní s ohledem na jeho odvozených typů `message` a `paramName` parametry. Ujistěte se, že tyto konstruktory se nazývají s argumenty správný řetězec. Podpisy jsou následující:  
  
 <xref:System.ArgumentException>(řetězec `message`)  
  
 <xref:System.ArgumentException>(řetězec `message`, řetězec `paramName`)  
  
 <xref:System.ArgumentNullException>(řetězec `paramName`)  
  
 <xref:System.ArgumentNullException>(řetězec `paramName`, řetězec `message`)  
  
 <xref:System.ArgumentOutOfRangeException>(řetězec `paramName`)  
  
 <xref:System.ArgumentOutOfRangeException>(řetězec `paramName`, řetězec `message`)  
  
 <xref:System.DuplicateWaitObjectException>(řetězec `parameterName`)  
  
 <xref:System.DuplicateWaitObjectException>(řetězec `parameterName`, řetězec `message`)  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, volání konstruktor, který přijímá zprávy, název parametru nebo obojí a zkontrolujte, zda jsou argumenty jsou správné pro typ <xref:System.ArgumentException> volána.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo pouze v případě, že parametrizované konstruktor je volán s správné řetězcové argumenty.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje konstruktor, který se nesprávně vytvoří instanci typu ArgumentNullException.  
  
 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_1.cpp)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_1.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_1.vb)]  
  
## <a name="example"></a>Příklad  
 Následující příklad opravy výše porušení přepnutím argumenty konstruktoru.  
  
 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_2.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_2.vb)]