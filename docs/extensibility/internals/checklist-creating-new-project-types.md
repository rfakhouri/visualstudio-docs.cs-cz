---
title: "Kontrolní seznam: Vytvoření nové typy projektů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 06b6dc2fab4158f36126b6509909dd0db6fd7125
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="checklist-creating-new-project-types"></a>Kontrolní seznam: Vytvoření nové typy projektu
Je třeba provést několik úloh k vytvoření nového typu projektu. Následující kontrolní seznam poskytuje návod, jak tyto úlohy.  
  
1.  Návrh funkce pro nový typ projektu. Další informace najdete v tématu [rozhodnutí o návrhu projektu typu](../../extensibility/internals/project-type-design-decisions.md).  
  
2.  Určuje, které editory používané pro kódu a další elementy projektu. Můžete použít na základní nebo standardní editory, nebo můžete vytvořit a umožňuje pomocí editorů specifické pro projekt. Další informace najdete v tématu [vytváření vlastní editory a návrhářů,](../../extensibility/creating-custom-editors-and-designers.md) a [postup: Otevřete projekt konkrétní editory](../../extensibility/how-to-open-project-specific-editors.md).  
  
3.  Určete úroveň účasti ve bude mít vaše položky projektu **zobrazení tříd** a **Prohlížeč objektů**. Další informace najdete v tématu [procházení podpora Symbol nástroje](../../extensibility/internals/supporting-symbol-browsing-tools.md).  
  
4.  Odvození nové třídy založené na rozhodnutí o návrhu, které jste provedli dříve projektů a položek projektu.  
  
5.  Napsání kódu pro následující součásti typ projektu:  
  
    -   Objekt factory projektu, ke správě vytváření nových projektů a otevření stávajících projektů. Další informace najdete v tématu [vytváření instancí podle pomocí projektu objekty pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md).  
  
    -   Hierarchie projektu a zpracování příkazu. Další informace najdete v tématu [není v sestavení: pomocí HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346), [elementů modelu projektu](../../extensibility/internals/elements-of-a-project-model.md), [projektu modelu základní součásti](../../extensibility/internals/project-model-core-components.md)a [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md).  
  
    -   Správa položek projektu, včetně přidání projektu pro **nový projekt** dialogové okno. Další informace najdete v tématu [přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md) a [registrace projektů a šablon položek](../../extensibility/internals/registering-project-and-item-templates.md).  
  
    -   Trvalost stavu projektu a jednotlivé položky. Další informace najdete v tématu [otevírání a ukládání položky projektu](../../extensibility/internals/opening-and-saving-project-items.md). Trvalost informace o řešení, najdete v části [řešení](../../extensibility/internals/solutions.md).  
  
    -   Nezávislé vlastnosti konfigurace k zobrazení v okně Vlastnosti. Další informace najdete v tématu [rozšíření vlastnosti](../../extensibility/internals/extending-properties.md).  
  
    -   Vlastnosti konfigurace projektu, jak jsou implementované ve stránky vlastností zobrazíte vlastnosti závislá na konfiguraci. Další informace najdete v tématu [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md).  
  
    -   Vytváření výčtu výstupy pro nasazení. Další informace najdete v tématu [konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md).  
  
    -   Projekt po spuštění služby. Další informace najdete v tématu [elementů modelu projektu](../../extensibility/internals/elements-of-a-project-model.md) a [základní součásti služby projektu modelu](../../extensibility/internals/project-model-core-components.md).  
  
    -   Objekty a třídy odvozené od třídy `IDispatch`, k dispozici pro automatizaci.  
  
    -   Soubory XML příkaz tabulky (.vsct). Další informace najdete v tématu [tabulky příkaz Visual Studio (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
6.  Testování, ladění a spustit typ vašeho projektu.  
  
7.  Projekt v zobrazení **projektu** kartě **přidat odkaz na** dialogové okno nastavením `VARIANT_TRUE` hodnotu `VSHPROPID_ShowProjInSolutionPage`. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>.  
  
8.  Vytvořte soubor Microsoft Installer (MSI) pro instalaci vaší VSPackages. Další informace najdete v tématu [instalaci VSPackages pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md), [registrace typu projektu](../../extensibility/internals/registering-a-project-type.md), a [VSPackages](../../extensibility/internals/vspackages.md).  
  
## <a name="see-also"></a>Viz také  
 [Hierarchie v sadě Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [Kdy vytvořit typy projektů](../../extensibility/internals/when-to-create-project-types.md)   
 [Vytváření typů projektu](../../extensibility/internals/creating-project-types.md)