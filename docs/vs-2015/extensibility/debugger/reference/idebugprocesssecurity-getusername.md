---
title: IDebugProcessSecurity::GetUserName | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
caps.latest.revision: 5
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 17a6ef52d7df1c60b0cb6581a7e15eeaf67e7875
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68202782"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá uživatelské jméno od dodavatele portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 `GetUserName` Vrátí uživatelské jméno, které se zobrazí **uživatelské jméno** sloupec **připojit k procesu** dialogové okno. Chcete-li zobrazit **připojit k procesu** dialogové okno, klikněte na tlačítko **připojit k procesu** na **nástroje** v nabídce [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] integrované vývojové prostředí (IDE).  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)
