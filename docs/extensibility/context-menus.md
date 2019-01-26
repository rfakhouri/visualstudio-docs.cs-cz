---
title: Kontextové nabídky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 718afb23896f59acfd7eb4e1af60ba6b474de384
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54966240"
---
# <a name="context-menus"></a>Kontextové nabídky
Kontextové nabídky se zobrazí, když uživatel klepne pravým tlačítkem myši v aktivní oblasti od klientské oblasti a zrušte zaškrtnutí, když se uvolní pravé tlačítko myši.  
  
## <a name="editor-context-menus"></a>Kontextové nabídky editoru  
 Tím, že zachytává `ECMD_SHOWCONTEXTMENU`, vaše služba jazyka můžete řídit kontextové nabídky, které se zobrazí v editoru. Vlastní místní nabídce zobrazíte zpracování tohoto příkazu je předána do vaší <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>. Pokud tento příkaz nelze zpracovat, rozhraní IDE zobrazí standardní místní nabídka editoru k dispozici. Můžete také řídit obsah v místní nabídce základ jednotlivé značky. Další informace o tom, naleznete v tématu [text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md) a [zachytit příkazy služby starší verze jazyka](../extensibility/internals/intercepting-legacy-language-service-commands.md).  
  
## <a name="see-also"></a>Viz také:  
 [Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)   
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)