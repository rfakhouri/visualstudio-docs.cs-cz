---
title: Možnosti, textový editor, přípona souboru
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.File_Extension
helpviewer_keywords:
- file extensions, associating to editor
- Editing Experience
- Options dialog box
- Editing Experience, selecting
ms.assetid: 05298fc5-fc4e-4bb2-b942-1f7d2dcdff0f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 13c79a4cae482990369fc8218bf0b7226ab05942
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919061"
---
# <a name="options-text-editor-file-extension"></a>Možnosti, textový editor, přípona souboru

Tento dialog možností umožňuje určit, jak budou všechny soubory s určitými příponami v integrovaném vývojovém prostředí (IDE) sady Visual Studio zpracovány. Pro každé **rozšíření** , které zadáte, můžete vybrat prostředí pro úpravy. To umožňuje zvolit Editor nebo návrháře IDE, ve kterém se otevřou dokumenty určitého typu. Chcete-li zobrazit tyto možnosti, zvolte **Možnosti** v nabídce **nástroje** , rozbalte uzel **textový editor** a vyberte položku **Přípona souboru**.

Když vyberete možnost s kódováním, zobrazí se dialogové okno s pokaždé, když otevřete dokument tohoto typu, který umožňuje výběr schématu kódování pro daný dokument. To může být užitečné, pokud připravujete verze dokumentů projektu pro použití na různých platformách nebo v různých cílových jazycích.

## <a name="uielement-list"></a>UIElement – seznam

**Rozšíření**

Zadejte příponu souboru s možností úprav v integrovaném vývojovém prostředí (IDE), které chcete definovat.

**Editor**

Vyberte Editor IDE nebo návrháře, ve kterém se otevřou dokumenty s touto příponou souboru. Když vyberete možnost "s ncoding", zobrazí se dialogové okno při každém otevření takového dokumentu, který umožňuje výběr schématu kódování.

**Add**

Přidá položku, která zahrnuje zadané **rozšíření** a **Možnosti úprav** v seznamu rozšíření.

**odebrat**

Odstraní vybranou položku ze seznamu rozšíření.

**Seznam rozšíření**

Zobrazí seznam všech rozšíření, pro které bylo zadáno prostředí pro úpravy.

**Mapovat soubory s příponou na**

Tuto možnost vyberte, pokud chcete určit, jak bude IDE zpracovávat soubory bez přípony.

**Možnosti souboru s příponou**

Poskytuje stejný seznam jako **Editor**. Vyberte Editor IDE nebo návrháře, ve kterém se otevřou dokumenty bez přípon souborů.

## <a name="see-also"></a>Viz také:

- [Postupy: Správa režimů editoru](../../ide/how-to-manage-editor-modes.md)