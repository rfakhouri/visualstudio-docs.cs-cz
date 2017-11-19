---
title: "Přehled jazyka domény nástrojů uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.editor
helpviewer_keywords: Domain-Specific Language Tools, user interface
ms.assetid: 81ae6b35-6819-41d0-953b-6b4ed81f9227
caps.latest.revision: "25"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: d76ed4d14e7333678fcf927dfa1b2f21d8573be5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>Přehled uživatelského rozhraní Jazykových nástrojů specifických pro doménu
Když poprvé otevřete řešení jazykové nástroje specifické pro doménu (DSL Tools) v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], uživatelské rozhraní bude vypadat podobně jako na následujícím obrázku.  
  
 ![Návrhář DSL](../modeling/media/dsl_designer.png "dsl_designer")  
  
 Následující tabulka vysvětluje, jak se používají částí uživatelského rozhraní.  
  
|**Element**|**Definice**|  
|-----------------|--------------------|  
|diagram|Diagram zobrazuje modelu domény.<br /><br /> Diagram má dvě strany. Jedné strany, které definuje typy elementů ve modelech. Druhá strana definuje, jak se vaše modely zobrazí na obrazovce.|  
|Sada nástrojů|Přetáhněte nástroje z panelu nástrojů k přidání domény třídy a typy obrazců k diagramu. Přidat relace, konektory a obrazce mapy, klikněte na nástroje a potom klikněte na zdrojový uzel v diagramu a potom cílový uzel.|  
|Průzkumník modelu DSL|**Průzkumník DSL** se zobrazí, když je aktivní okno DSL definice. Zobrazuje DSL jako strom. Průzkumník DSL umožňuje upravit funkce modelu, které se nezobrazují v diagramu. Například můžete přidat položky panelu nástrojů a přepínač na proces ověření pomocí **DSL Explorer**.|  
|Okno podrobností DSL|**DSL podrobnosti** okně se zobrazí vlastnosti domény prvky modelu, které vám umožní ovládat zobrazení prvků, a jak jsou elementy zkopírovány a odstranit.<br /><br /> -Ve výchozím nastavení **DSL podrobnosti** okno se zobrazí vedle položky **seznam chyb** a **výstup** windows.|  
  
## <a name="the-domain-model-diagram"></a>Diagram modelu domény  
 Diagram modelu domény je rozdělena na dva oddíly. Jedné straně diagram znázorňuje elementů a vztahů v modelu. Druhá strana ukazuje, jak je model, který se má zobrazit a zahrnuje tvarů, které se používají k zobrazení elementy a vlastnosti diagramu modelu. Na následujícím obrázku je znázorněno na obrázku.  
  
 ![Návrhář DSL s dráha](../modeling/media/dsl_desinger.png "dsl_desinger")  
  
 Následující tabulka popisuje některé elementů diagramu modelu domény.  
  
|**Termín**|**Definice**|  
|--------------|--------------------|  
|Domény – třída|Třídy domény jsou typy elementů ve modelech.<br /><br /> Třídu domény může být více než jednou v diagramu, pokud je cílem více než jedna relace.<br /><br /> Přidání třídy domény, přetáhněte nástroj domény třídy z **sada nástrojů** k **třídy a vztahy** postranní diagramu.|  
|Relace domény|Typy odkazů mezi elementy ve modelech se vztahy domén.<br /><br /> *Vložení vztah* označuje, že je cílový element ve vlastnictví nebo obsažená v tomto elementu zdroje a zobrazí se jako plná čára. Každý element v modelu musí být cílem jeden vnoření relace, tak, aby forms stromu modelu. A *referenční vztah* označuje obecné propojení mezi prvků modelu a zobrazí se jako přerušovaná čára. Libovolný element, může mít libovolný počet referenčních odkazů.<br /><br /> Vytvoření relace klepnutím na nástroj na **sada nástrojů**, kliknutím na domény třída zdroje a pak kliknutím na cílové třídy.|  
|Konektory a obrazců|Tvary zadejte, jak mají být zobrazeny elementů modelu v diagramu DSL., konektory zadat řádky v diagramu DSL, který slouží k zobrazení relace.<br /><br /> Chcete-li vytvořit tvar nebo konektor, přetáhněte nástroj, který **elementy diagramu** postranní diagramu.|  
|Obrazce mapy|Obrazce mapy se zobrazí jako čáru v diagramu modelu domény, propojení obrazce do třídy domény, která se zobrazí, nebo konektor k relace domény, který se zobrazí.|  
  
## <a name="see-also"></a>Viz také  
 [Přehled nástroje jazyka domény](../modeling/overview-of-domain-specific-language-tools.md)   
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [Přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md)