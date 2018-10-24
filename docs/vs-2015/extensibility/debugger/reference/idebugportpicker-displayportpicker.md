---
title: IDebugPortPicker::DisplayPortPicker | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73565bb0d191e3aa70c319c290972883df4f1d3f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49814367"
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

