---
title: Priorita projektu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], opening items
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6d444896c305130c7805b8fd6ec1bdf020ed446d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60089442"
---
# <a name="project-priority"></a>Priorita projektu
Položka projektu je obvykle člen pouze jeden projekt v řešení. Proto integrovaného vývojového prostředí lze snadno zjistit, kterého projektu se používá k otevření položky. Ale pokud je určitá položka členem více než jeden projekt, integrovaném vývojovém prostředí používá schéma priority určit nejlepší projektu, otevřete položku.

 Následující seznam obsahuje schéma priority projektu:

- Volání rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> metodu pro každý projekt v řešení určuje, jestli dokument je členem tohoto projektu.

- Pokud je členem projektu, projektu odpoví prioritu, že se projekt přiřadí podle jeho zpracování tohoto dokumentu. Například projekt jazyka reaguje s vysokou prioritou pro jeho jazyk zdrojové soubory, ale reaguje s nižší prioritou pro typ souboru nebyl rozpoznán, která se nepoužívá jako součást procesu sestavení.

- Projekty, které poskytují vlastní, specifické pro projekt editory nebo návrháře pro dokument dostanou také s vysokou prioritou.

- <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> Výčet poskytuje dokumentu hodnoty priority.

- Projekt, který určuje nejvyšší prioritou dostane kontext, který má dokument otevřít. Pokud dva projekty návratové hodnoty stejnou prioritu, preferuje se aktivní projekt. Pokud žádný projekt v řešení odpoví, že mohou otevřít dokument, rozhraní IDE umístí dokument v ostatních souborech projektu. Další informace najdete v tématu [různé soubory projektu](../../extensibility/internals/miscellaneous-files-project.md).

## <a name="see-also"></a>Viz také
- [Projekt Ostatní soubory](../../extensibility/internals/miscellaneous-files-project.md)
- [Postupy: Otevřít editorů pro otevřené dokumenty](../../extensibility/how-to-open-editors-for-open-documents.md)
- [Přidávání šablon projektů a položek projektů](../../extensibility/internals/adding-project-and-project-item-templates.md)