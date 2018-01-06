---
title: "DA0012: Vysoký objem odrazů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 203de647342affb9d81f0a57d0bcd44ac983f307
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: Vysoký objem odrazů
|||  
|-|-|  
|Id pravidla|DA0012|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování|  
|Zpráva|Vám může být pomocí reflexe nadměrně. Je náročná operace.|  
|Typ pravidla|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání metody System.Reflection například metodu InvokeMember a GetMember nebo typ metody, jako je například MemberInvoke jsou podstatnou část data profilování. Pokud je to možné, zvažte nahrazení tyto metody časná vazba metody závislá sestavení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Reflexe je flexibilní zařízení rozhraní .NET Framework, který slouží k provedení pozdní vazba vaší aplikace na závislé sestavení, spuštění nebo k vytvoření a dynamicky provedení nové typy během spuštění. Tyto postupy však může snížit výkon, pokud jsou často používají nebo volat v úzkou smyčky.  
  
 Další informace najdete v tématu [reflexe a pozdní vazby](http://go.microsoft.com/fwlink/?LinkId=177826) části kapitoly 5 – vylepšení spravované výkon kódu v zvýšení výkonu aplikací .NET a škálovatelnost objem Microsoft Patterns and Practices Library na webu MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Klikněte dvakrát na zprávy v okně Seznam chyb, přejděte na [zobrazení podrobností funkce](../profiling/function-details-view.md) profilování data. Zkontrolujte volání funkcí System.Type nebo System.Reflection metody k vyhledání v částech programu, které nejčastěji se vyskytující využívají rozhraní API reflexe .NET. Vyhněte se použití metody, které vracejí metadata. Pokud výkon vaší aplikace je důležité, vám může být potřeba nepoužívejte pozdní vazby a vytváření typů dynamicky za běhu.