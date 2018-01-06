---
title: "Neodpovídá na požadavky a šíření změny | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, events
ms.assetid: fc2e9ac5-7a84-44ed-9945-94e45f89c227
caps.latest.revision: "24"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: cebfaa79e2524dcd6ba862ec55467acc9e5cd316
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="responding-to-and-propagating-changes"></a>Reagování na změny a šíření změn
Pokud element vytvořit, odstranit nebo aktualizovat, můžete napsat kód, který rozšíří změny do dalších částí modelu, nebo externím prostředkům, například soubory, databáze nebo ostatní součásti.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 Jako vodítko vezměte v úvahu tyto postupy v uvedeném pořadí:  
  
|Technika|Scénáře|Další informace|  
|---------------|---------------|--------------------------|  
|Definujte počítané vlastnosti domény.|Vlastnost domény, jehož hodnota je vypočítána od dalších vlastností v modelu. Například za cenu, která je součet cen souvisejících elementů.|[Vypočtené a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md)|  
|Definujte vlastnost úložiště vlastní domény.|Vlastnost domény uložené v dalších částí modelu nebo externě. Například může analyzovat řetězec výraz do stromu v modelu.|[Vypočtené a vlastní vlastnosti úložiště](../modeling/calculated-and-custom-storage-properties.md)|  
|Přepsání změnit obslužné rutiny, například OnValueChanging a OnDeleting|Synchronizujte různé prvky a udržovat synchronizované s modelem externí hodnoty.<br /><br /> Omezení hodnoty, které mají definovanou oblastí.<br /><br /> Volá se bezprostředně před a za hodnotu vlastnosti a jiné změny. Chcete-li ukončit změnu, lze došlo k výjimce.|[Obslužné rutiny změny hodnoty vlastnosti domény](../modeling/domain-property-value-change-handlers.md)|  
|Pravidla|Můžete definovat pravidla, které jsou zařazeny do fronty pro provedení těsně před koncem transakce, ve které došlo ke změně. Jejich nejsou u zpět nebo znovu provést. Je použijte k byly shodné s jinou jednou ze součástí sady Windows store.|[Pravidla šířící změny v modelu](../modeling/rules-propagate-changes-within-the-model.md)|  
|Uložení událostí|Modelování úložiště poskytuje oznámení o události, jako je například přidávání nebo odstraňování prvek nebo odkaz nebo změně hodnoty vlastnosti. Událost se taky spouští na zpět a znovu. Úložiště události používejte k aktualizaci hodnoty, které nejsou v úložišti.|[Obslužné rutiny události šířící změny mimo model](../modeling/event-handlers-propagate-changes-outside-the-model.md)|  
|Události rozhraní .NET|Obslužné rutiny, které reakce na kliknutí myší a dalších gesta mají obrazce. Je třeba zaregistrovat pro tyto události pro každý objekt. Registrace se obvykle provádí v přepsání InitializeInstanceResources a je třeba provést pro každý prvek.<br /><br /> Tyto události obvykle dochází mimo transakci.|[Postupy: Zachycení kliknutí na obrazec nebo dekorátor](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)|  
|Rozsah pravidla|Rozsah pravidlo se používá konkrétně Chcete-li omezit rozsah obrazce.|[Umístění a velikost obrazce omezení BoundsRules](../modeling/boundsrules-constrain-shape-location-and-size.md)|  
|Výběr pravidel|Výběr pravidel konkrétně omezit, co si uživatel může vybrat.|[Postupy: Přístup k aktuálnímu výběru a jeho omezení](../modeling/how-to-access-and-constrain-the-current-selection.md)|  
|OnAssocatedPropertyChanged|Uveďte stavy elementů modelu pomocí funkce tvarů a konektory například stínové, šipek, barvu a šířku čáry a styl.|[Aktualizace obrazců a konektorů k vyjádření modelu](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md)|  
  
## <a name="comparing-rules-and-store-events"></a>**Porovnání pravidla a události v úložišti**  
 Změna žadateli, pravidla a události se spouštějí při změnách v modelu.  
  
 Pravidla se obvykle používají v end transakce, ve které došlo k změnu a události se použijí, jakmile jsou změny v transakci potvrzeny.  
  
 Události v úložišti používejte k synchronizaci modelu s objekty mimo úložiště a pravidla pro zachování konzistentní v rámci úložiště.  
  
-   **Vytváření vlastních pravidel** vytvoření vlastního pravidla jako třída odvozená z abstraktní pravidla. Musíte také upozornit framework o vlastní pravidlo. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
-   **Přihlášení k odběru událostí** než můžete se přihlásit k události, vytvořte obslužnou rutinu události a delegáta. Potom pomocí <xref:Microsoft.VisualStudio.Modeling.Store.EventManagerDirectory%2A>vlastnost k odběru události. Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
-   **Zrušení změn** je vrátit zpět transakci, události jsou vyvolány, ale pravidla se nepoužijí. Pokud pravidlo změní hodnotu a můžete tuto změnu zrušit, hodnota je nastaven na původní hodnotu během akce vrácení zpět. Pokud událost se vyvolá, musíte ručně změnit hodnotu zpět na původní hodnotu. Další informace o transactons a vrácení zpět, najdete v části [postupy: použití transakcí k aktualizaci modelu](../modeling/how-to-use-transactions-to-update-the-model.md).  
  
-   **Předání argumentů událostí k pravidlům a události** obou události a pravidla jsou předávány `EventArgs` parametr, který obsahuje informace o tom, model změnit.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: zachycení a klikněte na tvar nebo Dekoratéra](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)   
 [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)