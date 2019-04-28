---
title: Vytváření typů projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types, new
- projects [Visual Studio SDK], new project types
ms.assetid: bdb2d22e-d622-450c-bb2d-98152a745fcf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2c3d983da91fadbb0eb78eab6d0fa5bb02cca193
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62910004"
---
# <a name="create-project-types"></a>Vytvořit typy projektů
Můžete rozšířit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, že vytvoříte nový typ projektu. Pokud chcete vytvořit nový typ projektu, musíte porozumět několika konceptům a dokončit několik kroků. Následující témata poskytují přehled o tom, jak vytvořit typy projektů.

## <a name="in-this-section"></a>V tomto oddílu
- [Rozhodnutí o návrhu typu projektu](../../extensibility/internals/project-type-design-decisions.md)

 Tento článek popisuje položky, trvalost souborů projektu a závazku mechanik rozhodnutí, které je nutné provést před vytvořením nového typu projektu.

- [Kontrolní seznam: Vytvoření nových typů projektů](../../extensibility/internals/checklist-creating-new-project-types.md)

 Poskytuje přehled kroků, které musíte provést, chcete-li vytvořit nový typ projektu, který podporuje programovací úlohy, jako jsou úpravy kódu a kompilaci, sestavování, ladění a nasazování aplikací ve vašem projektu.

- [Vytvoření instance projektu pomocí objektů pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)

 Poskytuje informace o tom, jak zadat a použít objekt pro vytváření projektu k vytvoření instance nového projektu.

- [Registrace typu projektu](../../extensibility/internals/registering-a-project-type.md)

 Poskytuje příklady příkazů z registru, které poskytují výchozí cesty a data a tabulky, které obsahují položky z registru skriptu příkazu for each.

- [Trvalost projektu](../../extensibility/internals/project-persistence.md)

 Popisuje způsob používání `IPersistFileFormat` zachování souborů a objektů nezaložené souboru projektu.

- [Použití nástroje MSBuild](../../extensibility/internals/using-msbuild.md)

 Popisuje, jak můžete pomocí typu projektu [!INCLUDE[vstecmsbuild](../../extensibility/internals/includes/vstecmsbuild_md.md)] modul umožňuje uživatelům sestavení ze sestavení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a na příkazovém řádku.

## <a name="related-sections"></a>Související oddíly
- [Podpůrné nástroje procházení symbolů](../../extensibility/internals/supporting-symbol-browsing-tools.md)

 Popisuje architekturu kódu zobrazení nástroje, jako **prohlížeče objektů** a **zobrazení tříd** okna. Popisuje rozhraní a metody, které se používají k implementaci procházet objekty v sadě VSPackage.

- [Přidat projekt a šablony položek projektu](../../extensibility/internals/adding-project-and-project-item-templates.md)

 Tento článek popisuje význam, které projekty hrají při určování, které editor se používá při otevření položky projektu a jak lze ovládat prostředky projektu.

- [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)

 Ukazuje, jak poskytnout vašeho balíčku VSPackage svou vlastní jedinečnou identitu a postup při zabalení vaší knihovny DLL balíčku VSPackage a další informace v balíčku Instalační služby systému Windows (*. MSI* souboru) pro nasazení tak, aby vaši zákazníci.

- [Hierarchie v sadě Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)

 Popisuje, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zobrazení a adresy hierarchie.

- [Balíčky VSPackage](../../extensibility/internals/vspackages.md)

 Obsahuje základní informace o balíčku VSPackage Instalovatelné objekt modelu COM, který rozšiřuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí a popisuje, jak implementovat vlastní VSPackage.

- [Typy projektů](../../extensibility/internals/project-types.md)

 Popisuje, jak pomocí projektů Úprava kódu, kompilaci a vytváření kódu a spuštění a ladění kódu a poskytuje odkazy na témata podrobné informace o tom, jak vytvořit typy projektů.