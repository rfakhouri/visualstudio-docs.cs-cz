---
title: "Vytvoření projektu typy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, new
- projects [Visual Studio SDK], new project types
ms.assetid: bdb2d22e-d622-450c-bb2d-98152a745fcf
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f7c0bba9b80e4e874f222ce00834f44a2d93e3e7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-project-types"></a>Vytváření typů projektu
Můžete rozšířit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, že vytvoříte nový typ projektu. Pokud chcete vytvořit nový typ projektu, musíte pochopit několik konceptů a provést několik kroků. Následující témata poskytují přehled o tom, jak vytvořit typy projektů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Rozhodnutí o návrhu typ projektu](../../extensibility/internals/project-type-design-decisions.md)  
 Popisuje položky, trvalost souboru projektu a rozhodnutí o návrhu mechanik úsilí, které je nutné provést před vytvořením nového typu projektu.  
  
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)  
 Obsahuje přehled kroků, které musíte provést, chcete-li vytvořit nový typ projektu, který podporuje úloh programování jako úpravy kódu a kompilování, sestavování, ladění a nasazování aplikací ve vašem projektu.  
  
 [Vytváření instancí projektu pomocí objekty pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)  
 Poskytuje informace o tom, jak poskytnout a použít objekt pro vytváření projektu pro vytvoření instance nového projektu.  
  
 [Registrace typu projektu](../../extensibility/internals/registering-a-project-type.md)  
 Poskytuje ukázky kódu příkazů z registru poskytující výchozí cesty a dat a tabulku obsahující položky z registru skript pro každý příkaz.  
  
 [Trvalost projektu](../../extensibility/internals/project-persistence.md)  
 Popisuje použití `IPersistFileFormat` k zachování souborů a není určena pro soubor projektu objekty.  
  
 [Pomocí nástroje MSBuild](../../extensibility/internals/using-msbuild.md)  
 Popisuje, jak můžete použít typ vašeho projektu [!INCLUDE[vstecmsbuild](../../extensibility/internals/includes/vstecmsbuild_md.md)] sestavení modulu tak, aby uživatelé sestavit z [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a na příkazovém řádku.  
  
## <a name="related-sections"></a>Související oddíly  
 [Podpůrné nástroje procházení – Symbol](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 Popisuje architekturu kódu zobrazení nástroje, jako **Prohlížeč objektů** a **zobrazení tříd** okno. Popisuje rozhraní a metody, které se používají k implementaci objekt procházení ve VSPackage.  
  
 [Přidání projektů a šablon položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md)  
 Popisuje násobek, na který projekty přehrát při určování, které editor se používá při otevření položka projektu a jak smí uživatel manipulovat projektu prostředky.  
  
 [Instalace VSPackages pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)  
 Ukazuje, jak poskytnout vaše VSPackage vlastní jedinečnou identitu a postup při zabalení vaší knihovny DLL VSPackage a další informace v balíčku Instalační služby systému Windows (. Soubor MSI) pro nasazení do vašich zákazníků.  
  
 [Hierarchie v sadě Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)  
 Popisuje, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zobrazení a adresy hierarchií.  
  
 [VSPackages](../../extensibility/internals/vspackages.md)  
 Poskytuje přehled VSPackage instalovatelných objekt COM, který rozšiřuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí a popisuje, jak implementovat vlastní VSPackage.  
  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Popisuje, jak používat projekty k upravit kód, kompilace a sestavení kódu a spuštění a ladění kódu a poskytuje odkazy na témata podrobné informace o vytvoření typy projektů.