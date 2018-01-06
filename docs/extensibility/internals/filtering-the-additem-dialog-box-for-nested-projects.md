---
title: "Filtrování AddItem dialogových oken pro vnořené projekty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e1f5fc7695df028330d0e53faebefc178f499da1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>Filtrování AddItem dialogových oken pro vnořené projekty
Při zobrazení **AddItem** dialogové okno pro vnořený projekt, nadřazený projekt můžete řídit, které položky se zobrazují v dialogovém okně.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> Rozhraní umožňuje filtrovat uzly, které bude mít **AddItem** dialogové okno. Pokud projekt podřízené zobrazí **AddItem** dialogové okno, můžete implementovat nadřazené `IVsFilterAddProjectItemDlg` rozhraní a filtrování položek, které by jinak zobrazit v projektu dítěte.  
  
 Pokud projekty jsou seskupené podle funkce v rámci konkrétní nadřazené projekty, můžete implementovat `IVsFilterAddProjectItemDlg` když uživatel vybere **přidat položku projektu** v místní nabídce v vnořený projekt. Implementace `IvsFilterAddProjectItemDlg displays` projektu pouze položky nebo soubory specifické pro tuto skupinu. Položky projektu pro další skupiny jsou filtrovány mimo dialogové okno, i když jsou uložené ve stejném adresáři.  
  
 Když uživatel otevře **AddItem** dialogové okno pro podřízenou implementace nadřazený projekt `IVsFilterAddProjectItemDlg` se označuje jako rozhraní.  
  
 `IVsFilterAddProjectItemDlg` Rozhraní můžete taky implementovat pomocí filtrování podle kategorie. Další informace najdete v tématu [přidávání položek přidat novou položku dialogových oknech](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) a [registrace projektů a šablon položek](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Přidávání položek do pro přidání nové položky dialogových oken](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Vnoření projektů](../../extensibility/internals/nesting-projects.md)