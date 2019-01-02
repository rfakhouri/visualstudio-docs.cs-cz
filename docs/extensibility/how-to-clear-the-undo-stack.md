---
title: 'Postupy: Vymazat zásobník vrácení zpátky | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 14cf2af71f492dc4a82f6d8d9cf05fadcb0dcda2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53827544"
---
# <a name="how-to-clear-the-undo-stack"></a>Postupy: Vymazat zásobník vrácení zpátky
Následující postup vysvětluje, jak vymazat zásobník akcí zpět.  
  
## <a name="to-clear-the-undo-stack"></a>Vymazat zásobník vrácení zpátky  
  
1.  Zrušte zaškrtnutí políčka použít zásobník akcí zpět [IOleUndoManager::DiscardFrom](/windows/desktop/api/ocidl/nf-ocidl-ioleundomanager-discardfrom) metody. Následuje příklad:  
  
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
 [Postupy: Implementace správy zpět](../extensibility/how-to-implement-undo-management.md)