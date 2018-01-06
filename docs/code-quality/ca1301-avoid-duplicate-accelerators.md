---
title: "CA1301: Vyhněte se duplicitním akcelerátorům | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a61e4c0ab9957772609c20623f0bc6ef7659a9d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: Vyhněte se duplicitním akcelerátorům
|||  
|-|-|  
|TypeName|AvoidDuplicateAccelerators|  
|CheckId|CA1301|  
|Kategorie|Microsoft.Globalization|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ rozšiřuje <xref:System.Windows.Forms.Control?displayProperty=fullName> a obsahuje dvě nebo více nejvyšší úrovně ovládacích prvků, které jsou identické přístupové klávesy, které jsou uložené v souboru prostředků.  
  
## <a name="rule-description"></a>Popis pravidla  
 Přístupová klávesa neboli akcelerátor umožňuje klávesnici přístup k ovládacímu prvku pomocí klávesy ALT. Když má více ovládacích prvků duplicitní přístupové klávesy, není chování přístupové klávesy dobře definováno. Uživatel nemusí být možné získat přístup k prvku určený pomocí přístupového klíče a může být povoleno řízení než ten, který je určený.  
  
 Aktuální implementace toto pravidlo ignoruje položky nabídky. Položky nabídky v podnabídce stejné však by neměl mít identické přístupové klíče.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, definujte jedinečný přístupových klíčů pro všechny ovládací prvky.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje minimální formulář, který obsahuje dvou ovládacích prvků, které mají stejné přístupové klíče. Klíče jsou uložené v souboru prostředků, který není vidět; jejich hodnoty se však zobrazí ve komentáři out `checkBox.Text` řádky. Chování duplicitním akcelerátorům můžete zkoumat výměna `checkBox.Text` řádky se jejich komentáři se svými protějšky. Ale v takovém případě příkladu nebudou se generovat upozornění z tohoto pravidla.  
  
 [!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Resources.ResourceManager?displayProperty=fullName>   
 [Prostředky v desktopových aplikacích](/dotnet/framework/resources/index)