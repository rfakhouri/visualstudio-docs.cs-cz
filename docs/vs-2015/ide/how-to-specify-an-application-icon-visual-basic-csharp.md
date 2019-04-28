---
title: 'Postupy: Určení ikony aplikace (Visual Basic, C#) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
ms.assetid: ad8e14ed-adc2-45b6-a0be-818b16d5616f
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: eaffdfa5a5caaa9a200f14230a67cac72af96df8
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435199"
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Postupy: Určení ikony aplikace (Visual Basic, C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Icon` Vlastnosti projektu určuje soubor ikony (.ico), který se zobrazí pro kompilovanou aplikaci v Průzkumníku souborů a na hlavním panelu Windows.  
  
 `Icon` Vlastnost je přístupná v **aplikace** podokně **Návrháře projektu**; obsahuje seznam ikon, které byly přidány do projektu jako prostředky nebo jako soubory obsahu.  
  
> [!NOTE]
> Jakmile nastavíte vlastnost ikona pro aplikace, může také nastavena `Icon` vlastnosti každého **okno** nebo **formuláře** v aplikaci. Informace o okně ikony pro samostatné aplikace Windows Presentation Foundation (WPF), najdete v tématu <xref:System.Windows.Window.Icon%2A> vlastnost.  
  
### <a name="to-specify-an-application-icon"></a>K určení ikony aplikace  
  
1. V **Průzkumníka řešení**, zvolte uzel projektu (ne **řešení** uzlu).  
  
2. V panelu nabídky zvolte **projektu**, **vlastnosti**.  
  
3. Když **Návrháře projektu** se zobrazí, zvolte **aplikace** kartu.  
  
4. **(Visual Basic)**  v **ikonu** , zvolte soubor ikony (ICO).  
  
     **C#** téměř **ikonu** klikněte na položku  **\<Procházet... >** tlačítko a pak přejděte do umístění souboru s ikonou, která chcete.  
  
## <a name="see-also"></a>Viz také  
 [Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Správa vlastností aplikace](../ide/application-properties.md)  
 [Postupy: Přidání nebo odebrání prostředků](http://msdn.microsoft.com/7b77bc06-3952-4799-b029-def3f8f7f88d)
