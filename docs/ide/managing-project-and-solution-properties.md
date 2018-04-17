---
title: Správa vlastností projektů a řešení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a68cc558a52f7c8d66f76600cd68309ad67769c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="managing-project-and-solution-properties"></a>Správa vlastností projektů a řešení

Projekty mít vlastnosti, které řídí mnoho aspektů kompilace, ladění, testování a nasazení. Některé vlastnosti jsou společné mezi všechny typy projektů a některé jsou jedinečné pro konkrétní jazyky nebo platformy. Přístup k vlastnosti projektu pravým tlačítkem myši na uzel projektu v Průzkumníku řešení a zvolením **vlastnosti**, nebo zadáním "vlastnosti" do **Snadné spuštění** vyhledávacího pole v řádku nabídek.

![Místní nabídky projektu](../ide/media/vs2015_proj_prop_menu.gif "vs2015_proj_prop_menu")

Projekty .NET také může mít vlastnosti uzlu ve stromu projektu sám sebe.

![Vlastnosti uzlu v Průzkumníku řešení stromu](../ide/media/vs2015_props_se.png "VS2015_Props_SE")

## <a name="project-properties"></a>Vlastnosti projektu

Vlastnosti projektu jsou uspořádány do skupiny, a každá skupina má svou vlastní stránky vlastností. Na stránkách můžou být různé pro různé jazyky a typy projektů.

### <a name="c-visual-basic-and-f-projects"></a>Projekty C#, Visual Basic a F #

V jazyce C#, Visual Basic a F # projekty, jsou přístupné vlastnosti **Návrhář projektu**. Následující obrázek zobrazuje stránku vlastnosti sestavení pro projekt WPF v jazyce C#:

![Návrhář projektu sady Visual Studio](../ide/media/vs2015_proppage_build.png "VS2015_PropPage_Build")

Informace o jednotlivých stránek vlastností v Návrháři projektu najdete v tématu [referenční dokumentace k vlastnostem projektu](../ide/reference/project-properties-reference.md).

> [!TIP]
> Řešení mít několik vlastností a proto projektu položky; Tyto vlastnosti jsou přístupné v [vlastnosti – okno](../ide/reference/properties-window.md), nikoli **Návrhář projektu**.

### <a name="c-and-javascript-projects"></a>Projekty C++ a JavaScript

Projekty C++ a JavaScript mít různé uživatelské rozhraní pro správu vlastnosti projektu. Tento obrázek ukazuje stránce vlastností projektu C++ (stránky JavaScript jsou podobné):

![Visual C&#43; &#43; projektu vlastnosti](../ide/media/vs2015_projprops_cpp.png "VS2015_ProjProps_cpp")

Informace o vlastnosti projektu C++ najdete v tématu [práce s vlastností projektu (C++)](/cpp/ide/working-with-project-properties). Další informace o vlastnostech JavaScript, najdete v části [stránky vlastností, JavaScript](../ide/reference/property-pages-javascript.md).

## <a name="solution-properties"></a>Vlastnosti řešení

Pro přístup k vlastnostem v řešení, klikněte pravým tlačítkem na uzel řešení v **Průzkumníku řešení** a zvolte **vlastnosti**. V dialogovém okně můžete nastavit konfigurace projektu pro ladění nebo verze sestavení, zvolte projekty, které má být projekt po spuštění, při stisknutí tlačítka F5 a nastavit možnosti analýzy kódu.

## <a name="see-also"></a>Viz také

[Řešení a projekty v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md)
