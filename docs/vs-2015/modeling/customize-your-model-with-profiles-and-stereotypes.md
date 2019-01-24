---
title: Přizpůsobení modelu pomocí profilů a stereotypů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML model, profiles
- UML model, stereotypes
- UML model, customizing
ms.assetid: fd607157-0d3a-4583-a84e-427a4b2a5acb
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 85bdd48f37d8b8d60df6821934980bf46ebf29cd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763024"
---
# <a name="customize-your-model-with-profiles-and-stereotypes"></a>Přizpůsobení modelu pomocí profilů a stereotypů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V sadě Visual Studio můžete přizpůsobit standardní prvky modelu UML, jako jsou třídy a komponenty, jak je přizpůsobit pro konkrétní účely. Můžete použít *stereotyp* na prvek modelu, která může měnit prvku seznamu vlastností. Stereotypy, které jsou definovány v rámci kolekce volá *profily*.  
  
 Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [podporované verze pro nástroje architektury a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Použití stereotypu, propojte balíček k profilu. To vám umožní použít Stereotypy, které jsou definovány v profilu na prvky v balíčku. Některé profily nainstalují společně se sadou Visual Studio. Kromě toho můžete definovat vlastní profily.  
  
 V seznamu vlastnosti elementu lze nastavit stereotypy. Pro hlavní druhy obrazců v diagramu použité Stereotypy zobrazí také ve tvaru, jak je znázorněno v příkladu.  
  
 ![Třída UML se stereotypu. ](../modeling/media/uml-class-stereotype.png "UML_class_stereotype")  
  
> [!NOTE]
>  Pokud používáte profil k vytvoření modelu a pak model sdílíte s jinými uživateli, bude moci zobrazit Stereotypy, pokud máte v počítači nainstalovanou stejný profil.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Přidávání stereotypů k elementům modelu UML](../modeling/add-stereotypes-to-uml-model-elements.md)|Umístění prvku modelu v balíčku, propojení balíček do profilu a použití stereotyp na elementu.|  
|[Standardní stereotypy pro modely UML](../modeling/standard-stereotypes-for-uml-models.md)|Standardní L2 profilů UML a L3 jsou nainstalovány se sadou Visual Studio a každý model je spojen s je ve výchozím nastavení. Poskytují Stereotypy, které můžete použít k přidání poznámek ke své modely.<br /><br /> Můžete například použít stereotyp «specifikace» na třídu k označení, že je určena pouze k definování externě viditelného chování její instance|  
|[Definování profilu pro rozšíření UML](../modeling/define-a-profile-to-extend-uml.md)|Můžete definovat vlastní stereotypů a nástroje, které jsou přizpůsobené pro oblast vlastní aplikace.<br /><br /> Například pokud vyvíjíte bankovní software, můžete definovat stereotyp "Účet", který lze použít na třídy. Může pak použít diagramy tříd k popisu různých typů účtů a jejich vztahy.|  
|[Instalace profilu UML](../modeling/install-a-uml-profile.md)|Pokud někdo udělil profilu UML, můžete ho nainstalovat ve vašem počítači.|  
|[Definování vlastní položky sady nástrojů pro modelování](../modeling/define-a-custom-modeling-toolbox-item.md)|Vlastní položku sady nástrojů není nutné opakovaně nastavení stereotypu pro nové prvky.|  
|[Barva tříd UML podle stereotypu](http://code.msdn.microsoft.com/UML-Color-Classes-by-07de2b70)|Tento ukázkový kód rozšiřuje diagramy UML. Automaticky nastaví barvu tvaru UML podle stereotypu elementu.|
