---
title: "Zobrazení souborů pomocí příkazu Open | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a1631632a2ceb66380d1d0c41e54b5a4244a31a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="displaying-files-by-using-the-open-with-command"></a>Zobrazení souborů pomocí příkazu Open
Projekt můžete požádat IDE pro zobrazení **otevřít v** dialogové okno. Tento požadavek vyzývá uživatele k otevření souboru, který má výběr standardní editory. Následující kroky popisují tohoto procesu.  
  
1.  Volání projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, zadáte třeba hodnotu OSE_UseOpenWithDialog pro `OSEOpenDocEditor` parametr.  
  
2.  Založené na příponě názvu souboru dokumentu, rozhraní IDE Určuje, které editory uvedený v registru můžete otevřít zadaný dokument a zobrazí tyto informace **otevřete s** dialogové okno.  
  
    > [!NOTE]
    >  Projekty, které mají vlastní editor, který musí být součástí **otevřít v** dialogové okno musí zaregistrovat objekt pro vytváření editor pro každé takové editor. Vnitřní editory fungovat pouze společně s konkrétní typ projektu, který je požadováno v provádění <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metoda. Prostředí IDE má objekt factory předdefinované editoru pro základní textovém editoru a binární editor. Prostředí IDE také vytvoří instanci objektu pro vytváření editor jménem každý registrovaný přidružení typu souboru systému Windows. Příkladem takových soubor je aplikace Microsoft Word.  
  
3.  Jakmile uživatel vybere položku z **otevřít v** otevře se dialogové okno, pak IDE dokumentu voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda. Další informace najdete v tématu [postup: otevřete standardní editory](../../extensibility/how-to-open-standard-editors.md).  
  
## <a name="see-also"></a>Viz také  
 [Otevření a uložení položky projektu](../../extensibility/internals/opening-and-saving-project-items.md)   
 [Zobrazení souborů pomocí příkaz pro otevření souboru](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)   
 [Postupy: Otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md)