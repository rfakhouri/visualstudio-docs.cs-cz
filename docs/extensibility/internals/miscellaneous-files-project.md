---
title: Různé soubory projektu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- files, adding existing files to solutions
- Miscellaneous Files project
- Solution Items folder
- files, opening with Miscellaneous Files project
ms.assetid: 93a278a8-d4f4-400b-8945-4f1b0a2b5bac
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dd3cf792b10905d0f124266601e791dc91259ce2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349280"
---
# <a name="miscellaneous-files-project"></a>Projekt Ostatní soubory
Když uživatel otevře položky projektu, rozhraní IDE přiřadí různé soubory projektu všechny položky, které nejsou členy všechny projekty v řešení.

 Projekty přehrát významnou roli při určování, které editor se používá, když uživatel otevře položku projektu. Chcete-li otevřít určité soubory pomocí editoru specifické pro projekt nebo standardní editor nelze navrhovat projektu.

 Editor specifické pro projekt obvykle vyžaduje, aby uživatel zvláštní znalosti, nebo použít speciální rozhraní z projektu. Další informace najdete v tématu [jak: Otevření editoru pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md).

 Standardní editor můžete otevřít libovolný soubor s konkrétní příponou v každém projektu. Uživatel může upravit některé standardní editory, jako [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] textový editor pro projekty, ale stále zachovat jejich veřejné znak. Standardní editory jsou vytvářeny instalační sadou <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> metody.

 Pokud žádný projekt v řešení odpoví, že jej otevřete položku projektu, rozhraní IDE poskytuje zvláštní projekt s názvem, který otevře všechny soubory projektu různých souborů.

 Tento projekt poskytuje pro otevření souboru mimo kontext projektu. Během zpracování <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> metody ostatních souborech projektu vždy odpovídá s velmi nízkou prioritou. Různé soubory projektu proto vždy výnosy do jakéhokoli projektu s vyšší prioritou, který můžete otevřít soubory.

 Různé soubory projektu nevyžaduje, aby uživatel nemusel vytvářet pomocí **nový projekt** dialogové okno. Navíc různé soubory projektu trvale nespravuje seznam členů projektu. Volitelná funkce používá k zaznamenání seznamu naposledy použitých souborů pro každého uživatele.

## <a name="see-also"></a>Viz také
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>
- <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>
- [Postupy: Otevření editorů pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md)
- [Postupy: Otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md)
- [Přidávání šablon projektů a položek projektů](../../extensibility/internals/adding-project-and-project-item-templates.md)
- [Přidávání šablon projektů a položek projektů](../../extensibility/internals/adding-project-and-project-item-templates.md)