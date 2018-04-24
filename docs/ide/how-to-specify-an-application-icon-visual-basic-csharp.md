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
ms.openlocfilehash: bd8616e1f16e12ab07bd30a2d88f728bc79212f6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Postupy: určení ikony aplikace (Visual Basic, C#)

`Icon` Pro projekt Určuje soubor ikony (*.ico, který*), zobrazí se pro kompilované aplikace **Průzkumníka souborů** a na hlavním panelu Windows.

`Icon` Vlastnost je přístupná v **aplikace** podokně **Návrhář projektu**; obsahuje seznam ikon, které byly přidány do projektu jako prostředky, nebo jako soubory obsahu.

> [!NOTE]
> Jakmile nastavíte vlastnost ikona pro aplikace, může také nastavena `Icon` vlastnost jednotlivých **okno** nebo **formuláře** v aplikaci. Informace o okna ikony pro samostatné aplikace Windows Presentation Foundation (WPF) najdete v tématu <xref:System.Windows.Window.Icon%2A> vlastnost.

## <a name="to-specify-an-application-icon"></a>K určení ikony aplikace

1. V **Průzkumníku řešení**, vyberte uzel projektu (ne **řešení** uzlu).

1. Na řádku nabídek zvolte **projektu** > **vlastnosti**.

1. Když **Návrhář projektu** se zobrazí, vyberte **aplikace** karta.

1. **(Visual Basic)**  &mdash;v **ikonu** vyberte ikonu (*.ico, který*) souboru.

    **C#**&mdash;v blízkosti **ikonu** seznam, vyberte  **\<Procházet... >** tlačítko a vyhledejte umístění souboru ikonu, který chcete.

## <a name="see-also"></a>Viz také

[Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)
