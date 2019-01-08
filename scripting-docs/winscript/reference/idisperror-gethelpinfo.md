---
title: IDispError::GetHelpInfo | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetHelpInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetHelpInfo
ms.assetid: a146df13-eda4-4e56-8bf0-cf9886a2150f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c2c8ae3a3cff2485c50901bb94ced83098e6000
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087487"
---
# <a name="idisperrorgethelpinfo"></a>IDispError::GetHelpInfo
Vrátí cestu k souboru nápovědy a ID kontextu témat, která popisuje chybu, pokud je to možné.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetHelpInfo(  
   BSTR*  pbstrFileName,  
   DWORD*  pdwContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrFileName`  
 [out] Řetězec, který obsahuje plně kvalifikovanou cestu souboru nápovědy. Pokud není dostupný žádný soubor nápovědy nebo dojde k chybě, vrácená hodnota je NULL.  
  
 `pdwContext`  
 [out] ID kontextové nápovědy k chybě. Pokud není dostupný žádný soubor nápovědy (Pokud `pbstrFileName` má hodnotu NULL), tento parametr nemá žádný význam.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Došlo k chybě specifické pro zprostředkovatele.|  
|`E_INVALIDARG`|`pbstrFileName` nebo `pdwContext` byla NULL.|  
|`E_OUTOFMEMORY`|Zprostředkovatel nemohl přidělit paměť ke vrácení cesta k souboru nápovědy.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí cestu k souboru nápovědy a ID kontextu témat, která popisuje chybu, pokud je to možné.  
  
> [!NOTE]
>  Tato metoda není implementována.  
  
## <a name="see-also"></a>Viz také  
 [IDispError – rozhraní](../../winscript/reference/idisperror-interface.md)