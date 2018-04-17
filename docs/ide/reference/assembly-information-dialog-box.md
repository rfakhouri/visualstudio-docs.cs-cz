---
title: Dialogové okno informace o sestavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vb.ProjectPropertiesAssemblyInfo
helpviewer_keywords:
- Assembly Information dialog box
ms.assetid: 8f1f6449-e03d-4a5b-9076-d3b1f84ada48
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 07c81e392a4513ffa97a384e9aa60147c3a71290
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assembly-information-dialog-box"></a>Dialogové okno Informace o sestavení
**Informací o sestavení** dialogové okno se používá k určení hodnoty [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] globální sestavení atributy, které jsou uložené v souboru AssemblyInfo vytváří automaticky s projektu. V **Průzkumníku řešení**, soubor se nachází v **Můj projekt** uzlu v [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] (klikněte na tlačítko **zobrazit všechny soubory** k jejímu zobrazení); se nachází v  **Vlastnosti** v [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]. Další informace o atributech sestavení najdete v tématu [atributy](http://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205).  
  
 Pro přístup k tohoto dialogového okna, vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **aplikace** karta. Na **aplikace** klikněte na tlačítko **informací o sestavení** tlačítko.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Název**  
 Určuje název manifestu sestavení. Odpovídá <xref:System.Reflection.AssemblyTitleAttribute>.  
  
 **Popis**  
 Určuje volitelný popis manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyDescriptionAttribute>.  
  
 **Společnosti**  
 Určuje název společnosti pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyCompanyAttribute>.  
  
 **Produktu**  
 Určuje název produktu manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyProductAttribute>.  
  
 **Copyright**  
 Určuje autorských právech pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyCopyrightAttribute>.  
  
 **Ochranné známky**  
 Určuje ochrannou známku manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyTrademarkAttribute>.  
  
 **Verze sestavení**  
 Určuje verzi sestavení. Odpovídá <xref:System.Reflection.AssemblyVersionAttribute>.  
  
 **Verze souboru**  
 Určuje číslo verze, která dává pokyn kompilátoru použít konkrétní verzi pro prostředek verze souboru Win32. Odpovídá <xref:System.Reflection.AssemblyFileVersionAttribute>.  
  
 **GUID**  
 Jedinečný identifikátor GUID, který identifikuje sestavení. Při vytváření projektu sady Visual Studio vytvoří identifikátor GUID pro sestavení. Odpovídá <xref:System.Guid>.  
  
 **Neutrální jazyk**  
 Určuje, které jazykovou verzi sestavení podporuje. Odpovídá <xref:System.Resources.NeutralResourcesLanguageAttribute>. Výchozí hodnota je **(None)**.  
  
 **Ujistěte se, sestavení, které jsou viditelné modelu COM**  
 Určuje, zda bude k dispozici pro COM. typy v sestavení Odpovídá <xref:System.Runtime.InteropServices.ComVisibleAttribute>.  
  
## <a name="see-also"></a>Viz také  
 [Stránka aplikace, Návrhář projektu (Visual Basic)](../../ide/reference/application-page-project-designer-visual-basic.md)   
 [Atributy](http://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)