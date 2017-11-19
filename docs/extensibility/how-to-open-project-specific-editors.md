---
title: "Postupy: otevření editory specifické pro projekt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, opening a project-specific editor
- editors [Visual Studio SDK], opening project-specific editors
- projects [Visual Studio SDK], opening folders
ms.assetid: 83e56d39-c97b-4c6b-86d6-3ffbec97e8d1
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bb60f482edeea1271c0f864fd5b907138e83d103
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-open-project-specific-editors"></a>Postupy: otevření projektu konkrétní editory
Pokud soubor položky se otevřít projekt vnitřně vázán na konkrétní editor pro tento projekt, musíte projektu otevřete soubor v editoru specifické pro projekt. Soubor není možné delegovat na rozhraní IDE mechanismus pro výběr editoru. Například místo pomocí editoru standardní rastrový obrázek, můžete použít tuto možnost editoru pro konkrétní projekt zadejte konkrétní bitové mapy editor, který rozpoznává informace v souboru, které jsou jedinečné pro váš projekt.  
  
 Volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.OpenItem%2A> metoda při určování, zda soubor musí být otevřen konkrétní projekt. Další informace najdete v tématu [zobrazení souborů pomocí příkazu otevřete soubor](../extensibility/internals/displaying-files-by-using-the-open-file-command.md). Použijte následující pokyny k implementaci `OpenItem` metoda tak, aby měl projektu otevřete soubor projektu konkrétní editoru.  
  
### <a name="to-implement-the-openitem-method-with-a-project-specific-editor"></a>Implementovat metodu OpenItem v editoru specifické pro projekt  
  
1.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> – metoda (RDT_EditLock) k určení, zda soubor (dokument datový objekt) je již otevřen.  
  
    > [!NOTE]
    >  Další informace o dokumentu data a objekty zobrazení dokumentu najdete v tématu [Data dokumentu a zobrazení dokumentu v vlastní editory](../extensibility/document-data-and-document-view-in-custom-editors.md).  
  
2.  Pokud soubor je již spuštěna, resurface soubor voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> metoda a zadáte třeba hodnotu IDO_ActivateIfOpen pro `grfIDO` parametr.  
  
     Pokud je soubor otevřený a dokumentu je vlastníkem projektu než volajícím projektu, zobrazí se upozornění uživateli, který je editor otevíráte z jiného projektu. Okno souboru je pak prezentované.  
  
3.  Pokud vaše textovou vyrovnávací paměť (dokument datový objekt) je již otevřeno a chcete přiřadit jiné zobrazení, jste zodpovědní za zapojování tohoto zobrazení. Doporučeným přístupem k vytváření instancí zobrazení (objekt zobrazení dokumentu) z projektu, vypadá takto:  
  
    1.  Volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SLocalRegistry> službu a získat ukazatel <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> rozhraní.  
  
    2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> metodu pro vytvoření instance třídy zobrazení dokumentu.  
  
4.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.CreateDocumentWindow%2A> metoda, zadání objektu zobrazení dokumentu.  
  
     Tato metoda lokality objekt zobrazení dokumentu v okně dokumentu.  
  
5.  Provést odpovídající volání buď <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.InitNew%2A> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> metody.  
  
     V tomto okamžiku zobrazení by měl být plně inicializována a připravena k otevření.  
  
6.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> metodu pro zobrazení a otevřete zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Otevření a uložení položky projektu](../extensibility/internals/opening-and-saving-project-items.md)   
 [Postupy: otevření standardní editory](../extensibility/how-to-open-standard-editors.md)   
 [Postupy: otevření editory pro otevřené dokumenty](../extensibility/how-to-open-editors-for-open-documents.md)