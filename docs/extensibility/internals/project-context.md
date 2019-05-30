---
title: Kontext projektu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], opening items
ms.assetid: d1803f4a-24eb-44b0-b5d2-cb40c15534be
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 175ee37628b1794377a6b4e9e94cef52466cd291
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66328357"
---
# <a name="project-context"></a>Kontext projektu
Když uživatel přidá nebo funguje s projekty a položky projektu, rozhraní IDE pojem kontext projektu používá k určení, jak různé operace by měl provádět.

 Obvykle jsou soubory, které uživatel explicitně vytvoří tak, že vyberete objekty standardní projekt **nový projekt** příkaz nebo přináší tak, že vyberete **otevřít projekt** příkaz  **Soubor** nabídky. V těchto případech se soubory jsou vytvořeny a otevřen v kontextu projektu a typu projektu definuje kontext pro úpravy dokumentu.

 Některé projekty poskytují velmi velké množství kontextu. Například projekt spravuje oboru názvů s rozsahem projektu, prostřednictvím kódu programu nebo připojení k databázi s rozsahem projektu pro vytváření datových vazeb. Uživatel může často otevřít soubory nebo připojení k databázi přímo pomocí objektu určitého projektu, například položky projektu zobrazí v Průzkumníku řešení.

 V jinou dobu kontext projektu položky nebyl explicitně zadán. Kontext položky například není k dispozici, když uživatel otevře soubor tak, že vyberete **otevřít existující soubor** příkaz **souboru** nabídky, když ladicí program pracuje na souboru nebo když uživatel klikne **Najít v souborech** v příkaz **najít a nahradit** dialogové okno. Pro zpracování těchto situacích volání IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument> spravovat proces hledání nejlepší projekt otevřený nějaký dokument.

## <a name="see-also"></a>Viz také
- [Priorita projektu](../../extensibility/internals/project-priority.md)
- [Přidávání šablon projektů a položek projektů](../../extensibility/internals/adding-project-and-project-item-templates.md)