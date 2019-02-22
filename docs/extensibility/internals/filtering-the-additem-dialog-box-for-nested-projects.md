---
title: Filtrování dialogového okna pro vnořené projekty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 38b56753bfc56a1143d8c5423ddf7714f0b2f21e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56606027"
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