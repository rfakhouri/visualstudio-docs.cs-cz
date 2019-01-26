---
title: 'Postupy: Vymazat zásobník vrácení zpátky | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - clear undo stack
ms.assetid: 2200d2d4-7f58-401c-87fc-ddd32d368193
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 71c8e80fceef685b49af53fb5c369500315bbea9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55000162"
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