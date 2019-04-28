---
title: IDebugPortPicker::DisplayPortPicker | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8e115c4e45784b2072bf626d90ebab0d980491e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62871500"
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Zobrazí zadané dialogové okno, které umožňuje uživateli vybrat port.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT DisplayPortPicker(  
   HWND hwndParentDialog,  
   BSTR* pbstrPortId  
);  
```  
  
```csharp  
public int DisplayPortPicker(  
   int hwndParentDialog,  
   out string pbstrPortId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `hwndParentDialog`  
 [in] Popisovač pro dialogové okno nadřazené.  
  
 `pbstrPortId`  
 [out] Řetězec identifikátoru portu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrácená hodnota `S_FALSE` (nebo návratovou hodnotu `S_OK` s `BSTR` nastavena na `NULL`) označuje, že uživatel klikl na **zrušit**.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)
