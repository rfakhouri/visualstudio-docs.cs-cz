---
title: 'Postupy: Určení ikony aplikace (Visual Basic, C#)'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- icons [Visual Studio], application
- application properties [Visual Studio], icons
- application icons [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: f2903821c0e0843de43f68d67cc64c344ab95e02
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547777"
---
# <a name="how-to-specify-an-application-icon-visual-basic-c"></a>Postupy: Určení ikony aplikace (Visual Basic, C#)

`Icon` Vlastnosti projektu určuje soubor ikony (*.ico*), který se zobrazí pro kompilovanou aplikaci v **Průzkumníka souborů** a na hlavním panelu Windows.

`Icon` Vlastnost je přístupná v **aplikace** podokně **Návrháře projektu**; obsahuje seznam ikon, které byly přidány do projektu jako prostředky nebo jako soubory obsahu.

> [!NOTE]
> Jakmile nastavíte vlastnost ikona pro aplikace, může také nastavena `Icon` vlastnosti každého **okno** nebo **formuláře** v aplikaci. Informace o okně ikony pro samostatné aplikace Windows Presentation Foundation (WPF), najdete v tématu <xref:System.Windows.Window.Icon%2A> vlastnost.

## <a name="to-specify-an-application-icon"></a>K určení ikony aplikace

1. V **Průzkumníka řešení**, zvolte uzel projektu (ne **řešení** uzlu).

1. V panelu nabídky zvolte **projektu** > **vlastnosti**.

1. Když **Návrháře projektu** se zobrazí, zvolte **aplikace** kartu.

1. **(Visual Basic)**  &mdash;v **ikonu** , zvolte ikonu (*.ico*) soubor.

    **C#**&mdash;Téměř **ikonu** klikněte na položku  **\<Procházet... >** tlačítko a pak přejděte do umístění souboru s ikonou, která chcete.

## <a name="see-also"></a>Viz také:

- [Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)