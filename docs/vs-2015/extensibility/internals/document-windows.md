---
title: Zdokumentujte Windows | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fb8ce0938ae79b0fc6108f6f3cdbe80a116f5531
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54796210"
---
# <a name="document-windows"></a>Okna dokumentů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

V sadě Visual Studio *okno dokumentu* je orámované podřízeného okna, který je spojen s oknem rozhraní více dokumentů (MDI). Okna dokumentu se obvykle používají pro zobrazení a úpravy zdrojového kódu nebo textu, ale mohli hostovat i jiné typy funkční. Okna dokumentu:  
  
- Může být uspořádány do skupin samostatné vodorovné nebo svislé kartě v nadřazeném prvku MDI tak, aby více souborů lze zobrazit ve stejnou dobu.  
  
- Můžete ukotvit v libovolném pořadí, v nadřazené MDI.  
  
- Můžete volně obtékané.  
  
- Jsou propojeny v pořadí karet na ostatní okna MDI.  
  
  Příkazů pro seskupení, ukotvitelné a plovoucí můžete najít na místní nabídku pro kartu okno dokumentu.  
  
  Další informace o chování okna v sadě Visual Studio najdete v tématu [přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md).  
  
## <a name="document-window-implementation"></a>Implementace okna dokumentu  
 Okna dokumentu jsou vytvořeny pomocí implementace editoru. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> Rozhraní vytváří okna dokumentu jako součást vytváření instance editoru. Další informace najdete v tématu [starší verze rozhraní v editoru](../../extensibility/legacy-interfaces-in-the-editor.md).  
  
> [!NOTE]
>  Chcete-li poskytovat zpět a vpřed body navigace v okně, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation> rozhraní. Do textového editoru textu značky používá k identifikaci body navigace v dokumentu.  
  
## <a name="the-running-document-table"></a>Spuštěná tabulka dokumentů  
 Rozhraní IDE spuštěnou tabulku dokumentů (r...) používá ke sledování stavu každé okno dokumentu. Rámcový je mechanismus, přes který dokument windows se zobrazí oznámení událostí, jako je například při zavření řešení nebo soubor se upravil. Další informace najdete v tématu [spuštěná tabulka dokumentů](../../extensibility/internals/running-document-table.md).  
  
## <a name="see-also"></a>Viz také  
 [Odložené načtení dokumentu](../../extensibility/internals/delayed-document-loading.md)
