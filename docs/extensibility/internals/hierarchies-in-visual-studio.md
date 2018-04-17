---
title: Hierarchie v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- hierarchies, Visual Studio IDE
- IDE, hierarchies
ms.assetid: 0a029a7c-79fd-4b54-bd63-bd0f21aa8d30
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8d1f018b9cc48d059761a26721c808024f60bb3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="hierarchies-in-visual-studio"></a>Hierarchie v sadě Visual Studio
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) zobrazí projektu jako *hierarchie*. V prostředí IDE je hierarchii stromu uzlů, kde každý uzel má sadu přidružených vlastností. A *projektu hierarchie* je kontejner, který obsahuje položky projektu, položky vztahy a přidružených vlastností položky a příkazy.  
  
 V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], spravovat hierarchií projektu pomocí rozhraní hierarchie <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Rozhraní přesměruje příkazy vyvolat z položek projektu do okna příslušné hierarchii místo standardní obslužná rutina.  
  
## <a name="project-hierarchies"></a>Hierarchie projektu  
 Každá hierarchie projekt obsahuje položky, které můžete zobrazit a upravit. Tyto položky se liší v závislosti na typu projektu. Projekt databáze může například obsahovat uložené procedury, zobrazení databáze a tabulky databáze. Programovací jazyk projektu, na druhé straně, bude pravděpodobně obsahovat zdrojové soubory a soubory prostředků u polí s bitovými mapami a dialogové okno. Mohou být vnořené hierarchií, které poskytuje některé přidané flexibilitu při vytváření hierarchie projektu.  
  
 Když vytvoříte nový typ projektu, určuje typ projektu kompletní sadu položek, které lze upravit v ní. Projekty však může obsahovat položky, pro které nemají úpravy podpory. Projekty Visual C++ může například obsahovat soubory HTML, i když Visual C++ neposkytuje žádné vlastní editor pro daný typ souboru HTML.  
  
 Hierarchie spravovat trvalost položky, které obsahují. Implementace v hierarchii musí řídit žádné speciální vlastnosti, které ovlivňují trvalost položky v rámci hierarchie. Například pokud položky představují objekty v úložišti místo soubory, implementace hierarchie řídit trvalost těchto objektů. Prostředí IDE, samotné přesměruje hierarchie, které chcete uložit položky v souladu s vstup uživatele, ale IDE neřídí všechny akce nezbytné k ukládání těchto položek. Místo toho je projekt v ovládacím prvku.  
  
 Když uživatel otevře v editoru položku, hierarchie, která určuje, že položka je vybraná a že bude aktivní hierarchie. Vybrané hierarchie určuje sadu příkazů, které jsou k dispozici tak, aby fungoval na položce. Sledování fokus uživatele tímto způsobem umožňuje hierarchii tak, aby odrážela aktuální kontext uživatele.  
  
## <a name="see-also"></a>Viz také  
 [Typy projektů](../../extensibility/internals/project-types.md)   
 [Výběr a měny v prostředí IDE](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [Ukázky VSSDK](http://aka.ms/vs2015sdksamples)