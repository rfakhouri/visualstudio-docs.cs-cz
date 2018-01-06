---
title: "Postupy: určení ikony aplikace (Visual Basic, C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
ms.assetid: ad8e14ed-adc2-45b6-a0be-818b16d5616f
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: ce92aef6f676cbdd35142f058312af90581900c5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Postupy: Určení ikony aplikace (Visual Basic, C#)
`Icon` Pro projekt Určuje soubor ikony (.ico) se zobrazí, kompilované aplikace v Průzkumníku souborů a na hlavním panelu Windows.  
  
 `Icon` Vlastnost je přístupná v **aplikace** podokně **Návrhář projektu**; obsahuje seznam ikon, které byly přidány do projektu jako prostředky, nebo jako soubory obsahu.  
  
> [!NOTE]
>  Jakmile nastavíte vlastnost ikona pro aplikace, může také nastavena `Icon` vlastnost jednotlivých **okno** nebo **formuláře** v aplikaci. Informace o okna ikony pro samostatné aplikace Windows Presentation Foundation (WPF) najdete v tématu <xref:System.Windows.Window.Icon%2A> vlastnost.  
  
### <a name="to-specify-an-application-icon"></a>K určení ikony aplikace  
  
1.  V **Průzkumníku řešení**, vyberte uzel projektu (ne **řešení** uzlu).  
  
2.  Na řádku nabídek zvolte **projektu**, **vlastnosti**.  
  
3.  Když **Návrhář projektu** se zobrazí, vyberte **aplikace** karta.  
  
4.  **(Visual Basic)**  v **ikonu** seznamu, vyberte soubor ikony (.ico).  
  
     **C#** v blízkosti **ikonu** seznam, vyberte  **\<Procházet... >** tlačítko a vyhledejte umístění souboru ikonu, který chcete.  
  
## <a name="see-also"></a>Viz také  
 [Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Správa vlastností aplikace](../ide/application-properties.md)  
 [Postupy: Přidání nebo odebrání prostředky](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)