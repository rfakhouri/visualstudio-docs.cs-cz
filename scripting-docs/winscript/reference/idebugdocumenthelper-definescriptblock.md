---
title: IDebugDocumentHelper::DefineScriptBlock | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.DefineScriptBlock
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::DefineScriptBlock
ms.assetid: e4120377-f04f-44b1-950b-2beba06c9c12
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a320e4e43a983ace4decbaa68de0b1a7df7d457
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62783021"
---
# <a name="idebugdocumenthelperdefinescriptblock"></a>IDebugDocumentHelper::DefineScriptBlock
Signalizuje možnost do pomocné rutiny určitého rozsahu znaků blok skriptu, který zařizuje služba dané skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT DefineScriptBlock(  
   ULONG           ulCharOffset,  
   ULONG           cChars,  
   IActiveScript*  pas,  
   BOOL            fScriptlet,  
   DWORD_PTR*      pdwSourceContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ulCharOffset`  
 [in] Umístění začátku bloku skriptu.  
  
 `cChars`  
 [in] Počet znaků v bloku skriptu.  
  
 `pas`  
 [in] Skriptovací stroj pro daný blok skriptu.  
  
 `fScriptlet`  
 [in] Příznak, který určuje, zda je blok skriptu skriptletu.  
  
 `pdwSourceContext`  
 [out] Místní zdroje v bloku skriptu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Inteligentního hostitele lze tuto metodu použijte, když svoje dokumenty obsahují bloků vloženého skriptu. Tuto metodu můžete použít modul jazyka, když jeho kód obsahuje vložené skripty pro jiné jazyky.  
  
 Skriptovací stroj je zodpovědná za všechny syntaxe barevné zvýrazňování a kód místní vyhledávání v bloku skriptu.  
  
 `DefineScriptBlock` Metoda by měla být volána po přidání text (například pomocí `IDebugDocumentHelper::AddDBCSText` metoda), ale před skript má být blok (například pomocí `IActiveScriptParse ::ParseScriptText` – metoda).  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHelper Interface](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)