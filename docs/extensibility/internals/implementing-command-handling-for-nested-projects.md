---
title: Implementace příkaz pro zpracování vnořené projekty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f3f02752fad6932bac90597d56f27257e78b84cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 [Vnoření projektů](../../extensibility/internals/nesting-projects.md)