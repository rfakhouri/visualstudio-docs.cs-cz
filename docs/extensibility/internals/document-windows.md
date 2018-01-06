---
title: Zdokumentujte Windows | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 03e61b80aaf4c5c8b0e25f5b2a4a42f13d75d305
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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