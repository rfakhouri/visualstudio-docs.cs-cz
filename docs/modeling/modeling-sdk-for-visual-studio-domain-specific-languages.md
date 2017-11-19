---
title: "Modelování SDK pro Visual Studio – specifické pro doménu jazyky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language Tools
- Domain-Specific Language
ms.assetid: 17a531e2-1964-4a9d-84fd-6fb1b4aee662
caps.latest.revision: "77"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 48cb7e5a274092a3ed82d2e41137633d12c3be01
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="modeling-sdk-for-visual-studio---domain-specific-languages"></a>Sada Modeling SDK pro sadu Visual Studio – jazyky domény
Pomocí sady SDK modelování pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], můžete vytvořit výkonné založené na modelu vývojové nástroje, které můžete integrovat do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Stejným způsobem můžete vytvořit jednu nebo několik definic modelu a integrovat je do sady nástrojů.  
  
 V centru MSDK je definice modelu, který je vytvořen, aby představoval pojmy v oblasti vašeho podnikání. Model s celou řadu nástrojů, jako je například graficky zobrazení, můžete obklopit možnost pro generování kódu a další artefakty příkazy pro transformaci v modelu a umožňuje interakci s kódem a jiných objektů nástroje [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Při vývoji lze model kombinovat s dalšími modely a nástroji, jež tvoří výkonnou sadu nástrojů, které jsou zaměřeny na vývoj.  
  
 MSDK umožňuje rychlý vývoj modelu ve formě jazyka specifického pro doménu (DSL). Začínáte se speciálním editorem, kterým definujete schéma nebo abstraktní syntaxi a grafickou notaci. Z této definice vygeneruje VMSDK následující položky:  
  
-   Model implementace s rozhraním API silného typu, který je spuštěn v obchodě založeném na transakcích.  
  
-   Průzkumník založený na stromové architektuře.  
  
-   Grafický editor, ve kterém uživatelé mohou zobrazit model nebo jeho části, které definujete.  
  
-   Metody serializace, které uloží modely ve formátu XML pro čtení.  
  
-   Zařízení pro generování programového kódu a jiných artefaktů pomocí šablonování textu.  
  
 Můžete přizpůsobit a rozšířit všechny tyto funkce. Vaše rozšíření jsou integrována tak, že můžete i nadále aktualizovat definici DSL a znovu generovat funkce bez ztráty rozšíření.  
  
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
 [Příspěvky blogu související](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
  
 Pokyny k rozšířené postupy a řešení potíží, najdete v článku [Visual Studio DSL & modelování rozšíření nástrojů fórum](http://go.microsoft.com/fwlink/?LinkID=186074).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme s jazyky specifické pro doménu](../modeling/getting-started-with-domain-specific-languages.md)  
  
 [Principy modely, třídy a vztahy](../modeling/understanding-models-classes-and-relationships.md)  
  
 [Jak definovat jazyka domény](../modeling/how-to-define-a-domain-specific-language.md)  
  
 [Přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md)  
  
 [Ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md)  
  
 [Psaní kódu sestavit si jazyka domény](../modeling/writing-code-to-customise-a-domain-specific-language.md)  
  
 [Generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 [Pochopení kódu DSL](../modeling/understanding-the-dsl-code.md)  
  
 [Přizpůsobení souboru úložiště a serializace XML](../modeling/customizing-file-storage-and-xml-serialization.md)  
  
 [Nasazení řešení jazyka domény](../modeling/deploying-domain-specific-language-solutions.md)  
  
 [Vytváření jazyk specifické pro doménu formulářů Windows](../modeling/creating-a-windows-forms-based-domain-specific-language.md)  
  
 [Vytváření specifické pro doménu jazyk grafického subsystému WPF](../modeling/creating-a-wpf-based-domain-specific-language.md)  
  
 [Postupy: rozšíření návrháře jazyka domény](../modeling/how-to-extend-the-domain-specific-language-designer.md)  
  
 [Podporované edice sady Visual Studio pro vizualizace a modelování SDK](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)  
  
 [Postupy: migrace na novou verzi jazyka domény](../modeling/how-to-migrate-a-domain-specific-language-to-a-new-version.md)  
  
 [Referenční dokumentace rozhraní API pro modelování SDK pro Visual Studio](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
