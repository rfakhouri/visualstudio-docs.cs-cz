---
title: Dialogové okno Informace o sestavení
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesAssemblyInfo
helpviewer_keywords:
- Assembly Information dialog box
ms.assetid: 8f1f6449-e03d-4a5b-9076-d3b1f84ada48
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5e6214ec04dbf45e7d6b5a973babe4c7d95b571b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55020084"
---
# <a name="assembly-information-dialog-box"></a>Dialogové okno Informace o sestavení
**Informace o sestavení** dialogové okno se používá k určení hodnoty [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] globálního sestavení atributy, které jsou uloženy v souboru AssemblyInfo automaticky vytvořené pomocí projektu. V **Průzkumníku řešení**, soubor se nachází v **Můj projekt** uzel v [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] (klikněte na tlačítko **zobrazit všechny soubory** zobrazíte jeho); je umístěn v rámci  **Vlastnosti** v [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]. Další informace o atributech sestavení naleznete v tématu [atributy](https://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205).

 Pro přístup k tomuto dialogovému oknu, vyberte uzel projektu v **Průzkumníka řešení**a potom na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **aplikace** kartu. Na **aplikace** stránky, klikněte na tlačítko **informace o sestavení** tlačítko.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Název** Určuje název pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyTitleAttribute>.

 **Popis** Určuje volitelný popis pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyDescriptionAttribute>.

 **Společnost** Určuje název společnosti pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyCompanyAttribute>.

 **Produkt** Určuje název produktu pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyProductAttribute>.

 **O autorských právech** určuje autorských právech pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyCopyrightAttribute>.

 **Ochranná známka** určuje ochranná známka pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyTrademarkAttribute>.

 **Verze sestavení** Určuje verzi sestavení. Odpovídá <xref:System.Reflection.AssemblyVersionAttribute>.

 **Verze souboru** Určuje číslo verze, který instruuje kompilátor, aby používaly určitou verzi prostředku verze souboru Win32. Odpovídá <xref:System.Reflection.AssemblyFileVersionAttribute>.

 **Identifikátor GUID** jedinečný identifikátor GUID, který identifikuje sestavení. Při vytváření projektu sady Visual Studio vytvoří identifikátor GUID pro sestavení. Odpovídá <xref:System.Guid>.

 **Neutrální jazyk** určuje jazykovou verzi sestavení podporuje. Odpovídá <xref:System.Resources.NeutralResourcesLanguageAttribute>. Výchozí hodnota je **(žádný)**.

 **Ujistěte se, sestavení viditelné modulu COM** Určuje, zda bude k dispozici do modelu COM. typy v sestavení Odpovídá <xref:System.Runtime.InteropServices.ComVisibleAttribute>.

## <a name="see-also"></a>Viz také

- [Stránka Aplikace, Návrhář projektu (Visual Basic)](../../ide/reference/application-page-project-designer-visual-basic.md)
- [Atributy](https://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)