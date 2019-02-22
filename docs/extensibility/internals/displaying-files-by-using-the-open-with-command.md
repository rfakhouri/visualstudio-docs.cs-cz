---
title: Zobrazení souborů pomocí příkazu Otevřít | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types, supporting Open With command
- Open With command
- persistence, supporting Open With command
ms.assetid: 53794bc3-1b73-4d40-954e-cfade1abddcf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b82be9d7f376c1fbc0bc5b24534298a917d07b2e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624344"
---
# <a name="display-files-by-using-the-open-with-command"></a>Pomocí příkazu Otevřít v zobrazení souborů
Projekt můžete požádat o integrované vývojové prostředí pro zobrazení **otevřít v** dialogové okno. Tento požadavek se zobrazí výzva k otevření souboru, který má výběr standardních editorů. Tento proces je popsán následující kroky:

1.  Volání projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, a zadat hodnotu `OSE_UseOpenWithDialog` pro `OSEOpenDocEditor` parametru.

2.  Neřiďte příponou názvu souboru dokumentu, rozhraní IDE určí, editory, které uvedený v registru můžete otevřít zadaný dokument a zobrazí tyto informace **otevřít v programu** dialogové okno.

    > [!NOTE]
    >  Projekty, které mají vnitřní editor, který musí být součástí **otevřít v** dialogovému oknu musíte zaregistrovat objekt pro vytváření editoru pro každý takový editor. Vnitřní editory pracovat pouze spolu s konkrétní typ projektu, který se prosazuje provádění <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> metody. Rozhraní IDE má objekt factory integrovaného editoru pro základní editor textového a binárního editoru. Integrované vývojové prostředí také vytvoří instanci objektu pro vytváření editoru jménem každý registrovaný přidružení souboru Windows. Příkladem takových souborů je Microsoft Word.

3.  Poté, co uživatel vybere položku ze **otevřít v** dokumentu voláním otevře se dialogové okno, pak IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metoda. Další informace najdete v tématu [jak: Otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md).

## <a name="see-also"></a>Viz také:
- [Otevření a uložení položek projektu](../../extensibility/internals/opening-and-saving-project-items.md)
- [Zobrazení souborů pomocí příkazu Otevřít soubor](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)
- [Postupy: Otevřít standardních editorů](../../extensibility/how-to-open-standard-editors.md)
