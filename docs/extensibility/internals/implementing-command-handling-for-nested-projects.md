---
title: "Implementace příkaz pro zpracování vnořené projekty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a71da10ee4473f3fb542e0ce0e03891d60b75d34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-command-handling-for-nested-projects"></a>Implementace příkaz zpracování pro vnořené projekty
Prostředí IDE můžete předat příkazy, které se předávají prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní, které se vnořené projekty nebo projekty nadřazené můžete filtrovat nebo přepsat příkazy.  
  
> [!NOTE]
>  Je možné filtrovat pouze příkazy normálně zpracovávat nadřazený projekt. Příkazy, jako **sestavení** a **nasadit** , jsou zpracovávány IDE nelze filtrovat.  
  
 Následující kroky popisují proces pro implementaci zpracování příkazu.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-implement-command-handling"></a>Implementace zpracování příkazu  
  
1.  Když uživatel vybere vnořený projekt nebo uzel v vnořené projektu:  
  
    1.  Volání IDE <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda.  
  
     – nebo –  
  
    1.  Pokud příkaz pochází v okně hierarchie, například příkaz z místní nabídky v Průzkumníku řešení, zavolá rozhraní IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> metodu nadřazené projektu.  
  
2.  Nadřazený projekt můžete zkontrolovat parametry mají být předány `QueryStatus`, jako například `pguidCmdGroup` a `prgCmds`určete, zda nadřazený projekt má filtrování příkazů. Pokud nadřazený projekt je implementovaný vyfiltrujete příkazy, je potřeba nastavit:  
  
    ```  
    prgCmds[0].cmdf = OLECMDF_SUPPORTED;  
    // make sure it is disabled  
    prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;  
    ```  
  
     Pak se vrátit nadřazený projekt `S_OK`.  
  
     Pokud nadřazený projekt nefiltruje příkaz, měl by být právě vrácen `S_OK`. V takovém případě IDE automaticky směruje příkaz podřízené projektu.  
  
     Příkaz směrovat do projektu podřízené nemá nadřazený projekt. Prostředí IDE provede této úlohy...  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Příkazy, nabídek a panelů nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)   
 [Vnoření projekty](../../extensibility/internals/nesting-projects.md)