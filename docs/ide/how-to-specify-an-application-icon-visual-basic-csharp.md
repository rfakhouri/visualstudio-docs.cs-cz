---
title: 'Postupy: určení ikony aplikace (Visual Basic, C#) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b5e2984e9da7d3df4187c1a32b481ed0a70c876d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Postupy: Určení ikony aplikace (Visual Basic, C#)

`Icon` Pro projekt Určuje soubor ikony (.ico) se zobrazí, kompilované aplikace v Průzkumníku souborů a na hlavním panelu Windows.

`Icon` Vlastnost je přístupná v **aplikace** podokně **Návrhář projektu**; obsahuje seznam ikon, které byly přidány do projektu jako prostředky, nebo jako soubory obsahu.

> [!NOTE]
> Jakmile nastavíte vlastnost ikona pro aplikace, může také nastavena `Icon` vlastnost jednotlivých **okno** nebo **formuláře** v aplikaci. Informace o okna ikony pro samostatné aplikace Windows Presentation Foundation (WPF) najdete v tématu <xref:System.Windows.Window.Icon%2A> vlastnost.

## <a name="to-specify-an-application-icon"></a>K určení ikony aplikace

1. V **Průzkumníku řešení**, vyberte uzel projektu (ne **řešení** uzlu).

1. Na řádku nabídek zvolte **projektu** > **vlastnosti**.

1. Když **Návrhář projektu** se zobrazí, vyberte **aplikace** karta.

1. **(Visual Basic)**  &mdash;v **ikonu** seznamu, vyberte soubor ikony (.ico).

    **C#**&mdash;v blízkosti **ikonu** seznam, vyberte  **\<Procházet... >** tlačítko a vyhledejte umístění souboru ikonu, který chcete.

## <a name="see-also"></a>Viz také

[Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Stránka Aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)
