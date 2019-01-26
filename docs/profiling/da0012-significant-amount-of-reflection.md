---
title: 'DA0012: Objem odrazů | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2083b6446fc4f818bfc7d88b2b8a029ef4b06624
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54962115"
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: Objem odrazů

|||  
|-|-|  
|Id pravidla|DA0012|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování|  
|Zpráva|Budete pravděpodobně používáte nadměrně reflexi. Je náročná operace.|  
|Typ pravidla|Upozornění|  

## <a name="cause"></a>Příčina  
 Volání metody System.Reflection například metodu InvokeMember a GetMember nebo typ metody, jako je například MemberInvoke je podstatnou část dat profilování. Pokud je to možné, zvažte nahrazení tyto metody s časná vazba metod závislá sestavení.  

## <a name="rule-description"></a>Popis pravidla  
 Reflexe je flexibilní rozhraní .NET Framework, který slouží k provádění pozdní vazba vaší aplikace na závislé sestavení za běhu nebo k vytvoření a dynamicky za běhu spusťte nové typy zařízení. Tyto postupy však může snížit výkon, pokud jsou často používané nebo volat v těsné smyčky.  

 Další informace najdete v tématu [reflexe a pozdní vazby](http://go.microsoft.com/fwlink/?LinkId=177826) část kapitola 5 – vylepšení spravovaných výkon kódu objemu zlepšení výkonu aplikace .NET a škálovatelnosti Microsoft Patterns and Practices Knihovna na webové stránce MSDN.  

## <a name="how-to-investigate-a-warning"></a>Zkoumání upozornění  
 Dvakrát klikněte na zprávu v okně Seznam chyb, přejděte [zobrazení podrobností funkce](../profiling/function-details-view.md) dat profilování. Zkontrolujte volání funkce System.Type nebo System.Reflection metody, která najdete v částech programu, které nejčastěji použití rozhraní API reflexe .NET. Vyhněte se použití metod, které vracejí metadata. Když je nejdůležitější výkon vaší aplikace, můžete potřebovat nepoužívejte pozdní vazby a dynamické vytváření typů v době běhu.