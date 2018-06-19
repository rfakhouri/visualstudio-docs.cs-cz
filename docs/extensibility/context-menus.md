---
title: Kontextové nabídky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - context menus
ms.assetid: 44fd9e6a-6d42-4aba-80ba-f37fa0070f1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fa957e949127663eca7d4e619919edcc07c7a29b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108557"
---
# <a name="context-menus"></a>Kontextové nabídky
Kontextové nabídky se zobrazují, když uživatel klikne pravým tlačítkem myši v oblast active klientské oblasti a zrušte při vydání pravým tlačítkem myši.  
  
## <a name="editor-context-menus"></a>Kontextové nabídky editoru  
 Tím, že zachytává `ECMD_SHOWCONTEXTMENU`, jazykové služby můžete řídit kontextové nabídky, které se zobrazí v editoru. Zobrazíte vlastní kontextovou nabídku zpracovat tento příkaz, když je předána do vaší <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> voláním <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowContextMenu%2A>. Pokud není zpracovat tento příkaz, rozhraní IDE zobrazí standardní místní nabídka, zadaný pro editor. Můžete také ovládat obsah v místní nabídce na základě za značky. Další informace o tom najdete v tématu [pomocí značek textu s rozhraním API pro starší verze](../extensibility/using-text-markers-with-the-legacy-api.md) a [brání starší verze jazyka služby příkazy](../extensibility/internals/intercepting-legacy-language-service-commands.md).  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby jazyk starší verze](../extensibility/internals/developing-a-legacy-language-service.md)   
 [Rozšiřování nabídek a příkazů](../extensibility/extending-menus-and-commands.md)