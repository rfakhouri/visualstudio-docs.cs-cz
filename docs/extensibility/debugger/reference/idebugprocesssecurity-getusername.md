---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 94fcc74943deb33e7f98ba24e9d7389a9d5746fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
Získá uživatelské jméno z portu dodavatele.  
  
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
 Pokud metoda bude úspěšná, vrátí `S_OK`. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `GetUserName` Vrátí uživatelské jméno, které se zobrazí v **uživatelské jméno** sloupec **připojit k procesu** dialogové okno. Chcete-li zobrazit **připojit k procesu** dialogové okno, klikněte na tlačítko **připojit k procesu** na **nástroje** v nabídce [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)