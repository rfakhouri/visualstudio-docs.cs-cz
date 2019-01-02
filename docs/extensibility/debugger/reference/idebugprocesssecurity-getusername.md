---
title: IDebugProcessSecurity::GetUserName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fd3f7133652cf048bb1b4c7a2e7d4886b1c79a2b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53931087"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
Získá uživatelské jméno od dodavatele portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrUserName`  
 [out] Řetězec obsahující uživatelské jméno.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud metoda uspěje, vrátí `S_OK`. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `GetUserName` Vrátí uživatelské jméno, které se zobrazí **uživatelské jméno** sloupec **připojit k procesu** dialogové okno. Chcete-li zobrazit **připojit k procesu** dialogové okno, klikněte na tlačítko **připojit k procesu** na **nástroje** v nabídce [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)