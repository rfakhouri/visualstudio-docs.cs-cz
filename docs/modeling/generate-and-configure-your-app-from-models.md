---
title: "Generování a konfigurace aplikace z modelů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 51760d1bcd2673ac391ea96ba3b715470ff64c66
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="generate-and-configure-your-app-from-models"></a>Generování a konfigurace aplikace z modelů
Můžete vygenerovat nebo konfigurovat částí aplikace z modelu.
  
 Model reprezentuje požadavky přímo než kód. Odvozením chování aplikace přímo z modelu můžete reagovat na změněné požadavky mnohem rychleji a spolehlivě než při aktualizaci kód. I když některé počáteční pracovní je potřeba nastavit odvození, tyto investice je vrácena, pokud očekáváte, změny v požadavcích, nebo pokud plánujete nastavit několik variant produktu.  
  
## <a name="generating-the-code-of-your-application-from-a-model"></a>Generování kódu vaší aplikace z modelu  
 Nejjednodušší způsob, jak generovat kód je pomocí textových šablon. Mohou generovat kód ve stejné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, ve kterém můžete zachovat modelu. Další informace naleznete v tématu:  
  
-   [Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
-   [Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 Tato metoda je snadno použitelná postupně. Začněte s aplikaci, která se dá použít jenom pro konkrétní případ a zvolte několik části, které chcete z modelu se liší. Přejmenujte zdrojové soubory z těchto částí tak, že budou textové šablony (.tt) soubory. V tomto okamžiku zdrojové soubory .cs automaticky vygeneruje ze šablony souborů, aplikace bude fungovat jako předtím.  
  
 Potom může trvat jednu část kód a nahraďte ji metodou výraz šablony text, který čte modelu a generuje část zdrojového souboru. Nejméně jedna hodnota modelu by měl generovat původního zdroje, takže můžete znovu spustit aplikaci a funguje jako předtím. Po dokončení testu hodnoty jiného modelu, můžete přesunout Vložit šablonu výrazy do jiné části kódu.  
  
 Tato metoda přírůstkové znamená, že generování kódu je obvykle přístup, nízkým rizikem. Výsledná aplikace se obvykle provádí téměř a také ručně psané verze.  
  
 Však pokud spustíte s existující aplikace, je možné, že mnoho Refaktoring je potřeba oddělit různé chování, které se řídí modelu, takže může být nejrůznější nezávisle. Doporučujeme posoudit tento aspekt aplikace, když odhadnout náklady na projektu.  
  
## <a name="configuring-your-application-from-a-model"></a>Konfigurace vaší aplikace z modelu  
 Pokud chcete měnit chování vaší aplikace za běhu, nemůžete použít generování kódu, který generuje zdrojového kódu, než je kompilované aplikace. Místo toho můžete navrhnout vaše aplikace ke čtení modelu a jeho chování se liší podle toho. Další informace naleznete v tématu:  
  
-   [Postupy: Otevření modelu ze souboru v kódu programu](../modeling/how-to-open-a-model-from-file-in-program-code.md)  
  
 Tuto metodu lze použít také postupně, ale existuje další práci na začátku. Budete muset psát kód, který bude číst modelu a nastavit rozhraní, které umožňuje jeho hodnoty přístupné části proměnné. Vytváření proměnných částí obecný je větší než generování kódu.  
  
 Obecná aplikace obvykle provádí menší také než jeho konkrétní svými protějšky. Pokud výkon je velmi důležitý, by měla obsahovat plánu projektu hodnocení toto riziko.  
  
## <a name="developing-a-derived-application"></a>Vývoj aplikace s odvozené  
 Mohou být užitečné následující obecné pokyny.  
  
-   **Spusťte konkrétní a generalize.** Nejprve napište konkrétní verzi vaší aplikace. Tato verze by měla fungovat v jedné sadě podmínek. Jakmile budete spokojeni to funguje správně, můžete provést některé je odvozena z modelu. Rozšiřte části odvozené postupně.  
  
     Například Navrhněte webová stránka, která má specifickou sadu webových stránek dříve, než vytvoříte webovou aplikaci, která uvede stránek, které jsou definované v modelu.  
  
-   **Model variant aspekty.** Identifikujte aspekty, které se liší, buď mezi jedno nasazení a druhý, nebo v čase jako požadavky změnit. Jedná se o aspekty, které by měl být odvozen z modelu.  
  
     Například pokud sadu webové stránky a odkazů mezi jejich změny, ale styl a formát stránky je vždy stejný, pak modelu měli popisují odkazy, ale nemá k popisu formátu stránek.  
  
-   **Samostatné otázky.** Pokud proměnná aspekty je možné rozdělit do samostatné oblasti, použijte samostatné modely pro každou oblast. Pomocí ModelBus, můžete definovat operace, které ovlivňují modely a omezení mezi nimi.  
  
     Jeden model. můžete například použijte k definování navigace mezi zadat rozložení stránek webové stránky a jiného modelu.
  
-   **Model požadavek, není řešení.** Model návrhu tak, aby popisuje požadavky na uživatele. Naopak není návrh notace podle proměnné aspekty implementace.  
  
     Například model webové navigace by měl představovat webových stránek a hypertextové odkazy mezi nimi. Model webových navigační nesmí představují fragmenty kódu HTML nebo tříd ve vaší aplikaci.  
  
-   **Vytvořit nebo interpretovat?** Pokud se změní zřídka požadavky pro konkrétní nasazení, generovat kód pro program z modelu. Pokud požadavky na může často mění, nebo může být současně existovat ve více než jeden typ variant v jednom nasazení, zapište aplikaci, aby mohli číst a interpretovat modelu.  
  
     Například pokud používáte model vašeho webu k vývoji řadu různých a samostatně instalovaný weby, potom můžete měl generovat kód lokality z modelu. Ale ji použijete modelu k řízení lokality, která každý den, se změní, pak je lepší pro zápis webový server, který čte modelu a odpovídajícím způsobem uvede webu.  
  
-   **UML nebo DSL?** Zvažte vytvoření vaší modelování zápis pomocí Stereotypy pro rozšíření UML. Definujte DSL, pokud není k dispozici žádný diagram UML, která odpovídá účel. Ale li se vyhnout narušení standardní sémantika UML.  
  
     Například diagramu tříd UML je kolekce polí a šipek; Pomocí této zápis můžete teoreticky definovat nic. Ale nedoporučujeme použít diagramu tříd s výjimkou případů, kde jsou ve skutečnosti popisující sadu typů. Například může přizpůsobit diagramů tříd k popisu různých typů webových stránek.  
  
## <a name="see-also"></a>Viz také  
 [Generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md)   
 [Postupy: otevření modelu ze souboru v programovém kódu](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)