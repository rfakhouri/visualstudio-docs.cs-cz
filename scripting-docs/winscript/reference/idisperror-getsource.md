---
title: IDispError::GetSource | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetSource
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetSource
ms.assetid: 20def54c-a67c-4102-babf-6f0704e5fc5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8a84640f020a1ff255b8c7e5dd753752e0d310a7
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446879"
---
# <a name="idisperrorgetsource"></a>IDispError::GetSource
Vrátí závislá na jazyku programový identifikátor pro třídu nebo aplikace, která vyvolala chybu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSource(  
   BSTR*  pbstrSource  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrSource`  
 [out] Řetězec obsahující programový identifikátor, ve formuláři `progname.objectname`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se používá k určení třídy nebo aplikace, ve kterém k výjimce došlo. Programový identifikátor, mohou být vráceny v jazyce určeném zadat při vyvolání identifikátor národního prostředí (LCID).  
  
> [!NOTE]
> Tato metoda není implementována.  
  
## <a name="see-also"></a>Viz také  
 [IDispError – rozhraní](../../winscript/reference/idisperror-interface.md)