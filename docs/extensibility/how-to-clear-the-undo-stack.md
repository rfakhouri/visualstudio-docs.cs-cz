---
title: 'Postupy: vymazání zásobník vrácení zpátky | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 59f8d57c0ba0e84107cd0d0290b950b335e5f2b0
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639468"
---
# <a name="how-to-clear-the-undo-stack"></a>Postupy: vymazání zásobník vrácení zpátky
Následující postup vysvětluje, jak vymazat zásobník akcí zpět.  
  
## <a name="to-clear-the-undo-stack"></a>Vymazat zásobník vrácení zpátky  
  
1.  Zrušte zaškrtnutí políčka použít zásobník akcí zpět [IOleUndoManager::DiscardFrom](http://msdn.microsoft.com/library/windows/desktop/ms693799) metody. Následuje příklad:  
  
    ```  
    HRESULT CCmdWindow::ClearUndoStack()  
    {  
      HRESULT hr = S_OK;  
  
      if (m_pUndoMgr == NULL)  
        {  
        IfFailGo(m_pTextLines->GetUndoManager(&m_pUndoMgr));  
        ASSERT(m_pUndoMgr != NULL, "",;);  
        }  
  
      IfFailGo(m_pUndoMgr->DiscardFrom(NULL));  
  
    Error:  
      return hr;  
    }  
    ```  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: implementace řízení zpět](../extensibility/how-to-implement-undo-management.md)