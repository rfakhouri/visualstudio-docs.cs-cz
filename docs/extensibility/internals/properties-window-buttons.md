---
title: "Vlastnosti – okno tlačítka | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4cd83a8d8e72c18f8a6929e8985f7a8635a940d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="properties-window-buttons"></a>Tlačítka Vlastnosti – okno
V závislosti na vývoj jazyk a typ produktu, zobrazí se určité tlačítka na panelu nástrojů pro ve výchozím nastavení **vlastnosti** okno. Ve všech případech **Categorized**, **Alphabetized**, **vlastnosti**, a **stránky vlastností** tlačítka se zobrazí. V jazyce Visual C# a Visual Basic **události** tlačítko se zobrazí také. V některých projektech Visual C++ **VC ++ zprávy** a **přepsání VC** tlačítka se zobrazí. Může se zobrazit další tlačítka pro jiné typy projektů. Další informace o tlačítka v **vlastnosti** okně najdete v části [vlastnosti – okno](../../ide/reference/properties-window.md).  
  
## <a name="implementation-of-properties-window-buttons"></a>Implementace tlačítek vlastnosti – okno  
 Když kliknete **Categorized** tlačítko, volání Visual Studio <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> rozhraní na objekt, který má právě fokus k seřazení jeho vlastnosti podle kategorií. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>se implementuje na `IDispatch` objekt, který se zobrazí na **vlastnosti** okno.  
  
 Existují 11 předdefinované vlastnosti kategorie, které mají záporné hodnoty. Můžete definovat vlastní kategorie, ale doporučujeme vám, že je třeba je přiřadit kladné hodnoty. abychom je odlišili od předdefinovaným kategoriím.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A> Vrátí metoda hodnotu kategorie odpovídající vlastnost pro zadanou vlastnost. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A> Metoda vrátí řetězec, který obsahuje název kategorie. Můžete mít pouze kvůli zajištění podpory pro vlastní kategorie hodnoty, protože Visual Studio zná hodnoty kategorie standardní vlastností.  
  
 Když kliknete **Alphabetized** tlačítko Vlastnosti jsou zobrazeny v abecedním pořadí podle názvu. Názvy jsou načítána pro `IDispatch` podle lokalizované řazení algoritmus.  
  
 Při **vlastnosti** je otevřeno, **vlastnosti** tlačítko se automaticky zobrazí jako vybraný. V dalších částech tohoto prostředí se zobrazí tlačítko stejné, a kliknutím na Zobrazit **vlastnosti** okno.  
  
 **Stránky vlastností** tlačítko je k dispozici Pokud `ISpecifyPropertyPages` není implementována pro vybraný objekt. Vlastnosti závislá na konfiguraci zobrazení, které jsou obvykle přidružené k řešení a projekty stránek vlastností, ale můžou být také být spojené s položky projektu (například v jazyce Visual C++).  
  
> [!NOTE]
>  Nelze přidat tlačítka panelu nástrojů na **vlastnosti** okno pomocí nespravovaného kódu. Přidání tlačítka panelu nástrojů, musíte vytvořit spravovaného objektu, která je odvozena z <xref:System.Windows.Forms.Design.PropertyTab>.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření vlastnosti](../../extensibility/internals/extending-properties.md)