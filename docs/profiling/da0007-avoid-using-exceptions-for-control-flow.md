---
title: "DA0007: Vyhněte se použití výjimek pro tok řízení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAExceptionsThrown
- vs.performance.7
- vs.performance.rules.DA0007
- vs.performance.DA0007
ms.assetid: ee8ba8b5-2313-46c9-b129-3f3a2a232898
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0b85bcc736f91aced9336f3168f8409384d109df
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="da0007-avoid-using-exceptions-for-control-flow"></a>DA0007: Vyhněte se použití výjimek pro tok řízení
|||  
|-|-|  
|Id pravidla|DA0007|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Všechny|  
|Zpráva|Vysoký počet výjimek jsou konzistentně hlášeny. Zvažte snížení použití výjimek v programu logiku.|  
|Typ zprávy|Upozornění|  
  
 Pokud je profil s použitím vzorkování, využívání paměti rozhraním .NET nebo metody sporu prostředků, musí shromažďovat alespoň 25 vzorků pro aktivaci tohoto pravidla.  
  
## <a name="cause"></a>příčina  
 V profilaci data měla volat vysokou míru obslužné rutiny výjimek rozhraní .NET Framework. Zvažte použití jiných logiku toku řízení a snížit počet výjimky, které jsou vydány.  
  
## <a name="rule-description"></a>Popis pravidla  
 Při použití obslužné rutiny výjimek k zachycení chyb a další události, které by narušilo spuštění programu je vhodné, použijte obslužná rutina výjimky jako součást regulární logiky provádění programu může být nákladné a je nutno. Ve většině případů se použije pouze pro okolnosti, které nastanou zřídka a neočekává výjimky... Výjimky není vhodné používat k návratu hodnot v rámci toku typické programu. V mnoha případech se můžete vyhnout vyvolávání výjimek ověřování hodnoty a použitím podmíněnou logiku provádění příkazů, které způsobí potíže.  
  
 Další informace najdete v článku [správu výjimek](http://go.microsoft.com/fwlink/?LinkID=177825) části **kapitoly 5 – zlepšení výkonu spravovaný kód** v **zvýšení výkonu aplikací .NET a škálovatelnost** svazku **Microsoft Patterns and Practices** library na webu MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Dvakrát klikněte na zprávy v okně Seznam chyb navigaci na zobrazení značky. Najít sloupec, který obsahuje **výjimky CLR rozhraní .NET (@ProcessInstance)\\počet vyvolaných za sekundu** měření. Zjistěte, jestli konkrétní fáze spuštění programu kde výjimek je častější než jiné. S použitím vzorkování profilu pokuste se identifikovat příkazech throw a try/catch – bloky, které generují časté výjimky. V případě potřeby přidejte logiku pro catch – bloky, které vám pomohou pochopit, výjimek, které jsou nejčastěji ke zpracování. Kde je to možné, nahraďte často provést příkazech throw nebo bloků catch s jednoduché toku řízení logiky nebo ověření kódu.  
  
 Například pokud byste se stát, že aplikace byla zpracování časté DivideByZeroException výjimek, přidání logiky vašeho programu zkontrolujte jmenovateli s nulové hodnoty budou zlepšit výkon aplikace.