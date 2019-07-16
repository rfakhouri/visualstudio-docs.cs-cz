---
title: IDebugArrayField::GetRank | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5d0396718482c9ce90527155a3612160612f66d3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198735"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá pořadí nebo počet rozměrů pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwRank`  
 [out] Vrátí počet rozměrů.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Rozměr pole odpovídá počet rozměrů. V jazyce C++ a C# vícerozměrná pole jsou ve skutečnosti pole polí a může proto považovat jenom jednorozměrná pole (a `GetRank` metoda vždy vrátí hodnotu 1). V [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], na druhé straně vícerozměrná pole jsou zpracovány jinak a pořadí těchto pole odpovídá počet rozměrů (a `GetRank` metoda vždy vrátí počet dimenzí).  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)
