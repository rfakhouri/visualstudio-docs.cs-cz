---
title: Filtrování dialogového okna pro vnořené projekty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bc3ff1f85e8c8c71bf8ef16e6fe0c89bf3613f4d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66328952"
---
# <a name="filter-the-additem-dialog-box-for-nested-projects"></a>Filtrovat AddItem dialogových oken pro vnořené projekty
Při zobrazení **AddItem** dialogové okno pro vnořený projekt nadřazený projekt můžete řídit, které položky se zobrazí v dialogovém okně.

 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> Rozhraní umožňuje filtrovat uzly, které bude mít **AddItem** dialogové okno. Pokud podřízený projekt zobrazí **AddItem** dialogovém okně můžete implementovat nadřazené `IVsFilterAddProjectItemDlg` rozhraní a filtrování položek, které by jinak zobrazeného v prvku projektu.

 Pokud projekty jsou seskupeny podle funkce v rámci určité nadřazené projektů, můžete implementovat `IVsFilterAddProjectItemDlg` když uživatel vybere **přidat položku projektu** v místní nabídce v vnořený projekt. Implementace `IvsFilterAddProjectItemDlg displays` projektu pouze položky, nebo soubory specifické pro tuto skupinu. Položky projektu pro jiné skupiny, jsou odfiltrovány z dialogu, i v případě, že jsou uložené ve stejném adresáři.

 Když uživatel otevře **AddItem** dialogové okno pro podřízený, nadřazené projektu provádění `IVsFilterAddProjectItemDlg` je názvem rozhraní.

 `IVsFilterAddProjectItemDlg` Rozhraní můžete taky implementovat pomocí filtrování podle kategorie. Další informace najdete v tématu [přidání položek do dialogových oken přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) a [registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md).

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>
- [Přidání položek do dialogových oken přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)
- [Vnoření projektů](../../extensibility/internals/nesting-projects.md)