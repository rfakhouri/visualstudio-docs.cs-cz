---
title: Ověřování systému během vývoje | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-devops-techdebt
ms.topic: conceptual
helpviewer_keywords:
- layer diagrams
ms.assetid: c9dafb47-7b1d-4c72-9432-d43be3db1799
caps.latest.revision: 39
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8d42618569e9b3924a43c11eb8feffeea8ed705a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54753366"
---
# <a name="validate-your-system-during-development"></a>Ověřování systému během vývoje
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio vám může pomoci udržovat konzistentní s požadavky uživatelů a architektuře systému vašeho softwaru.  
  
 Které verze sady Visual Studio podporovat každé z těchto funkcí najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="key-tasks"></a>Klíčové úkoly  
 Tyto úlohy slouží k ověření vašeho softwaru.  
  
|**Úlohy**|**Související témata**|  
|---------------|---------------------------|  
|**Ujistěte se, že váš model je konzistentní vzhledem k aplikacím:**<br /><br /> V závislosti na způsobu, jakým váš projekt používá a modely může být užitečné zakáže některé kombinace prvků. Například může omezit třídy UML, tak, aby vždy [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)]-kompatibilní s názvy. Můžete definovat omezení, jako jsou tyto v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření.|-   [Ověření modelu UML](../modeling/validate-your-uml-model.md)<br />-   [Definování omezení ověření pro modely UML](../modeling/define-validation-constraints-for-uml-models.md)|  
|**Ujistěte se, že software splňuje požadavky uživatelů**:<br /><br /> Požadavky a architektury modely můžete pomoci vám organizovat testy systému a jeho součástí. Tento postup pomáhá zajistit, že testování požadavků, které jsou důležité pro uživatele a další zainteresované uživatele, a pomůže vám rychle aktualizovat testů při změně požadavků.|-   [Vývoj testů z modelu](../modeling/develop-tests-from-a-model.md)|  
|**Ujistěte se, že software zůstává konzistentní s zamýšleného návrhu systému:**<br /><br /> Diagramy vrstev popsat zamýšlené závislosti mezi komponentami vaší aplikace. Během vývoje můžete ověřit, že skutečné závislosti v kódu odpovídají zamýšleného návrhu.|-   [Vytváření diagramů vrstev z kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Ověřování kódu pomocí diagramů vrstev](../modeling/validate-code-with-layer-diagrams.md)|  
  
## <a name="external-resources"></a>Externí zdroje  
  
|**Kategorie**|**Odkazy**|  
|------------------|---------------|  
|**Videa**|![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Doug sedm: Porozumění kódu a návrhu systému sadou Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Aplikační architektura založená na aplikaci pomocí diagramu vrstev](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [řady MSDN jak: Postup ověření kódu pomocí diagramů vrstev](http://go.microsoft.com/fwlink/?LinkID=214405)|  
|**Fóra**|-   [Visual Studio Visualization & Modeling nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Visualization & Modeling SDK (DSL Tools)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**Blogy**|-   [Visual Studio ALM + Team Foundation Server Blog](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**Technické články a deníky**|[MSDN Architecture Center](http://go.microsoft.com/fwlink/?LinkId=201343)|  
  
## <a name="see-also"></a>Viz také  
 [Testování aplikace](http://msdn.microsoft.com/library/796b7d6d-ad45-4772-9719-55eaf5490dac)   
 [Rozšíření modelů a diagramů UML](../modeling/extend-uml-models-and-diagrams.md)   
 [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)   
 [Analýza a modelování architektury](../modeling/analyze-and-model-your-architecture.md)
