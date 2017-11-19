---
title: "Modelování uživatelských požadavků | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- requirements
- stories
ms.assetid: 359900f8-6d69-493d-bfdf-2c9069c74a26
caps.latest.revision: "28"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 064d2819a9a7bd3e72539ff7624299e3619f4e94
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="model-user-requirements"></a>Modelování uživatelských požadavků
Visual Studio pomáhá pochopit, popisují a komunikaci potřebám uživatelů ve kreslení diagramy o jejich aktivity a rámci systému hraje v pomoci jim dosáhli svých cílů. Model požadavky je sada tyto diagramy, z nichž každý se zaměřuje na různé aspekty potřeby uživatelů. Videoukázka, najdete v tématu: [modelování domény obchodní](http://channel9.msdn.com/posts/clinted/UML-with-VS-2010-Part-3-Modeling-the-Business-Domain/).  
  
 Informace, které verze sady Visual Studio podporovat každý typ modelu, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Požadavky na modelu vám pomůže:  
  
-   Soustřeďte se na externí chování systému odděleně od jeho vnitřní návrhu.  
  
-   Popisují uživatelů a je třeba zúčastněných stran mnohem menší nejednoznačnosti než v přirozeném jazyce.  
  
-   Definujte konzistentní Glosář termínů, které mohou být využívána uživatelů, vývojáři a testerům, sada.  
  
-   Snižuje mezery a nekonzistence v požadavcích na.  
  
-   Snižte práce potřebné reagovat na požadavky na změny.  
  
-   Naplánujte pořadí, ve kterém bude vyvinuté funkce.  
  
-   Modely použijte jako základ pro systémových testů, zrušte vztah mezi testy a požadavky na provedení. Při změně požadavky, můžete tuto relaci aktualizovat testy správně. Tím je zajištěno, že systém splňuje požadavky na nové.  
  
 Model požadavky poskytuje největší výhody, pokud ji použít k zaměření diskuze s uživatele nebo jejich zástupci a pokroku na začátku každé iteraci. Není nutné k dokončení podrobně před psaní kódu. Částečně funkční aplikaci, i v případě velmi mnohem jednodušší, obvykle je základem nejvíce podporovat diskuzi o požadavky s uživateli. Model je efektivní způsob, jak shrnout výsledky těchto diskusí. Další informace najdete v tématu [použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md).  
  
> [!NOTE]
>  V těchto tématech "systém" znamená systému nebo aplikace, které vyvíjíte. Může to být velké kolekce mnoho softwarové a hardwarové součásti; nebo jednu aplikaci; nebo softwarová součást uvnitř větší systému. V každém případě popisuje požadavky model chování, které je viditelná z mimo vašemu systému, prostřednictvím uživatelského rozhraní nebo rozhraní API.  
  
## <a name="common-tasks"></a>Obecné úlohy  
 Můžete vytvořit několik různých zobrazení požadavků uživatelů.  Každé zobrazení poskytuje konkrétní typ informací.  Když vytvoříte tato zobrazení, je nejvhodnější často přesunout z jednoho do jiného. Můžete spustit z libovolného zobrazení.  
  
|Diagram nebo dokumentu|Co je popsaný v modelu požadavky|Část|  
|-------------------------|-----------------------------------------------|-------------|  
|Diagram koncepční – třída|Glosář typů, které se používají k popisu požadavky; typy viditelné v rozhraní systému.||  
|Další dokumenty nebo pracovních položek|Výkon, zabezpečení, spolehlivost a použitelnost kritéria.|[Popisující kvality služeb požadavky](#QoSRequirements)|  
|Další dokumenty nebo pracovních položek|Omezení a pravidla, které nejsou specifické pro konkrétní případ použití|[Zobrazuje obchodní pravidla](#BusinessRules)|  
  
 Všimněte si, že většinu typů diagramu lze použít pro jiné účely. Přehled typů diagramu najdete v tématu [vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md).
  
##  <a name="BusinessRules"></a>Zobrazuje obchodní pravidla  
 Obchodní pravidlo je požadavek, který není spojen s případu konkrétní použití a má být dodržen v celém systému.  
  
 Mnoho obchodní pravidla jsou omezení vztahy mezi koncepční třídy. Můžete napsat tyto *statické**obchodní pravidla* jako komentáře přidružené k příslušné třídy v diagramu koncepční třídy. Příklad:  
  
 ![Pravidlo v připojené k třídě objednávka komentář. ] (../modeling/media/uml_reqmcd2.png "UML_ReqmCD2")  
  
 *Dynamické obchodní pravidla* omezit povolený pořadí událostí. Například pomocí diagramu pořadí nebo aktivita k zobrazení, jestli uživatel musí přihlásit před prováděním dalších operací ve vašem systému.  
  
 Však mnoho dynamická pravidla může být efektivněji a obecně uvádí nahrazením je statická pravidla. Například můžete přidat atribut typu Boolean zaznamenána v na třídu v konceptuální třídy modelu. By zaznamenána v přidat jako koncová podmínka protokolu v případě použití a přidejte jej jako předběžné podmínky pro většinu jiné případy použití. Tento přístup umožňuje nedefinujte všechny možné kombinace pořadí událostí. Je také flexibilnější při budete muset přidat nové případy použití modelu.  
  
 Všimněte si, zda volba je o tom, jak určit požadavky na a že se jedná o nezávisle na tom, jak implementovat požadavky v kódu programu.  
  
 Další informace naleznete v následujících tématech:  
  
|Další informace o|Číst|  
|--------------------|----------|  
|Jak vyvíjet kód, který dodržuje obchodní pravidla|[Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)|  
  
##  <a name="QoSRequirements"></a>Popisující kvality služeb požadavky  
 Existuje několik kategorií kvality požadavek na službu. Zahrnují následující:  
  
-   Výkon  
  
-   Zabezpečení  
  
-   Použitelnost  
  
-   Spolehlivost  
  
-   Robustnost  
  
 Jsou některé z těchto požadavků v popisech případů konkrétní použití. Další požadavky nejsou specifické pro případy použití a efektivní zapisují v samostatných dokumentu. Pokud je to možné, je užitečné řídit termínů definované ve model požadavky. V následujícím příkladu Všimněte si, že hlavní slova, která požadavek na jsou názvy třídy v předchozí obrázky, případy použití a aktéři:  
  
 Pokud restaurace odstraní položku nabídky, zatímco zákazníka je řazení jídlem, zobrazí se všechny položky pořadí, který odkazuje na danou položku nabídky červeně.  
  
 Další informace naleznete v následujících tématech:  
  
|Další informace o|Číst|  
|--------------------|----------|  
|Podrobnější informace o záznamu kvality služeb požadavky|[Pokyny pro definování kvality služeb požadavky](http://msdn.microsoft.com/en-us/9677a437-c2cb-4ac4-8c2d-4e3350005f06)|  
|Jak vyvíjet kód, který dodržuje kvality služeb požadavky|[Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)|  
  
## <a name="see-also"></a>Viz také  
 [Použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md)   
 [Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)   
