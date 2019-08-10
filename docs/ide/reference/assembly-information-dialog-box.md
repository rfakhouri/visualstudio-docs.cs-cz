---
title: Dialogové okno Informace o sestavení
ms.date: 11/04/2016
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
ms.openlocfilehash: c36fbacfde97eb42b1feab3e9097a731437cce4e
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870762"
---
# <a name="assembly-information-dialog-box"></a>dialogové okno Informace o sestavení

Dialogové okno informace o sestavení slouží k určení hodnot .NET Framework atributů globálních sestavení, které jsou uloženy v souboru AssemblyInfo vytvořeném automaticky s vaším projektem. V Průzkumník řešení je soubor AssemblyInfo umístěný v uzlu **můj projekt** pro Visual Basic projekty (kliknutím na **Zobrazit všechny soubory** ho zobrazíte). Pro C# projekty se nachází v části **vlastnosti**. Další informace naleznete v tématu [atributy (C#)](/dotnet/csharp/programming-guide/concepts/attributes/index).

Chcete-li získat přístup k tomuto dialogovému oknu, vyberte uzel projektu v **Průzkumník řešení**a potom v nabídce **projekt** vyberte možnost **vlastnosti**. Na stránce **aplikace** vyberte tlačítko **informace o sestavení** .

## <a name="uielement-list"></a>UIElement – seznam

**Hlava**\
Určuje název manifestu sestavení. <xref:System.Reflection.AssemblyTitleAttribute>Odpovídá.

**Název**\
Určuje volitelný popis manifestu sestavení. <xref:System.Reflection.AssemblyDescriptionAttribute>Odpovídá.

**Podnikový**\
Určuje název společnosti pro manifest sestavení. <xref:System.Reflection.AssemblyCompanyAttribute>Odpovídá.

V registru můžete nastavit nebo změnit výchozí hodnotu pro společnost. Vyhledejte hodnotu **RegisteredOrganization** pod **Computer\HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows NT\CurrentVersion** nebo **Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion** klíč v závislosti na vaší verzi systému Windows.

**Produktu**\
Určuje název produktu pro manifest sestavení. <xref:System.Reflection.AssemblyProductAttribute>Odpovídá.

**Úprava**\
Určuje oznámení o autorských právech pro manifest sestavení. <xref:System.Reflection.AssemblyCopyrightAttribute>Odpovídá.

**Patka**\
Určuje ochrannou známku pro manifest sestavení. <xref:System.Reflection.AssemblyTrademarkAttribute>Odpovídá.

**Verze sestavení**\
Určuje verzi sestavení. <xref:System.Reflection.AssemblyVersionAttribute>Odpovídá.

**Verze souboru**\
Určuje číslo verze, které instruuje kompilátor, aby používal specifickou verzi pro prostředek verze souboru Win32. <xref:System.Reflection.AssemblyFileVersionAttribute>Odpovídá.

**HLAVNÍCH**\
Jedinečný identifikátor GUID, který identifikuje sestavení. Při vytváření projektu aplikace Visual Studio generuje identifikátor GUID pro sestavení. <xref:System.Guid>Odpovídá.

**Neutrální jazyk**\
Určuje jazykovou verzi, kterou sestavení podporuje. <xref:System.Resources.NeutralResourcesLanguageAttribute>Odpovídá. Výchozí hodnota je **(žádné)** .

**Nastavit model COM sestavení – viditelné**\
Určuje, zda typy v sestavení budou k dispozici pro model COM. <xref:System.Runtime.InteropServices.ComVisibleAttribute>Odpovídá.

## <a name="see-also"></a>Viz také:

- [Stránka Aplikace, Návrhář projektu (Visual Basic)](../../ide/reference/application-page-project-designer-visual-basic.md)
- [Atributy](https://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
