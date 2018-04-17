---
title: Zdokumentujte Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f2fd5b77bfc853da1c6098c00110e75b9d9acb75
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="document-windows"></a>Okna dokumentu
V sadě Visual Studio *okna dokumentu* je rámcová podřízeného okna, který je přidružen okno rozhraní více dokumentů (MDI). Okna dokumentu se obvykle používají pro zobrazení a úprava zdrojový kód nebo text, ale můžete také uložit jiné typy funkční. Okna dokumentu:  
  
-   Mohou být uspořádány v samostatné kartě vodorovné nebo svislé skupin v nadřazené MDI tak, aby více souborů lze zobrazit najednou.  
  
-   Lze ukotvit v libovolném pořadí v nadřazené MDI.  
  
-   Můžete volně obtékané.  
  
-   Jsou propojeny v pořadí karet do jiných MDI windows.  
  
 Příkazy pro seskupení, ukotvitelné a plovoucí můžete najít v místní nabídce karta okna dokumentu.  
  
 Další informace o chování oken v sadě Visual Studio najdete v tématu [přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md).  
  
## <a name="document-window-implementation"></a>Implementace okna dokumentu  
 Okna dokumentu jsou vytvořené pomocí implementace editoru. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> Rozhraní vytvoří dokument windows v rámci vytváření instancí editoru. Další informace najdete v tématu [starší verze rozhraní v editoru](../../extensibility/legacy-interfaces-in-the-editor.md).  
  
> [!NOTE]
>  K poskytování zpátky a předávat body navigace v okně, implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation> rozhraní. Textový editor se používá označení textu k určení bodů navigace v dokumentu.  
  
## <a name="the-running-document-table"></a>V tabulce spuštěná dokumentu  
 Rozhraní IDE používá spuštěné tabulce dokumentu (r...) sledovat stav každého okna dokumentu. R... je mechanismus, přes který dokument se windows informováni o události, například při uzavření řešení nebo soubor byl upraven. Další informace najdete v tématu [systémem dokumentu tabulky](../../extensibility/internals/running-document-table.md).  
  
## <a name="see-also"></a>Viz také  
 [Odložené načtení dokumentu](../../extensibility/internals/delayed-document-loading.md)