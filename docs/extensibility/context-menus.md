---
title: "Kontextové nabídky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 69048a35514ac35556e04ed5266ff58b21b31e0d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="context-menus"></a>Kontextové nabídky
Kontextové nabídky se zobrazují, když uživatel klikne pravým tlačítkem myši v oblast active klientské oblasti a zrušte při vydání pravým tlačítkem myši.  
  
## <a name="editor-context-menus"></a>Kontextové nabídky editoru  
 Tím, že zachytává `ECMD_SHOWCONTEXTMENU`, jazykové služby můžete řídit kontextové nabídky, které se zobrazí v editoru. Zobrazíte vlastní kontextovou nabídku zpracovat tento příkaz, když je předána do vaší <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>. Pokud není zpracovat tento příkaz, rozhraní IDE zobrazí standardní místní nabídka, zadaný pro editor. Můžete také ovládat obsah v místní nabídce na základě za značky. Další informace o tom najdete v tématu [pomocí značek textu s rozhraním API pro starší verze](../extensibility/using-text-markers-with-the-legacy-api.md) a [brání starší verze jazyka služby příkazy](../extensibility/internals/intercepting-legacy-language-service-commands.md).  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby jazyk starší verze](../extensibility/internals/developing-a-legacy-language-service.md)   
 [Rozšiřování nabídek a příkazů](../extensibility/extending-menus-and-commands.md)